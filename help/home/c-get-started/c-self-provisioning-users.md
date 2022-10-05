---
description: ワークステーションを使用して、Data Workbench・ユーザーを管理します。
title: ユーザーのセルフプロビジョニング
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# ユーザーのセルフプロビジョニング{#self-provisioning-of-users}

{{eol}}

ワークステーションを使用して、Data Workbench・ユーザーを管理します。

ワークステーションを使用して、Data Workbenchから必要な証明書を設定し、Adobeに接続できます。 この証明書は、SSL 通信と認証の両方で、ライセンスされたリソースおよび機能を使用する際に役立ちます。 証明書ベースの認証では、複数のコンピューターでワークステーションを使用するために、複数の証明書を取得して設定する必要があります。 また、ユーザーのプロビジョニングと使用権限はAdobeが管理します。新しい証明書または証明書の失効については、Adobeに問い合わせる必要があります。

DWB 6.7 以降、ワークステーションはユーザー名とパスワードによるユーザー認証をサポートします。

証明書ベースの認証/承認は、設定で引き続き機能しますが、新しい資格情報ベースの認証に移行することを強くお勧めします。 新しいアプローチでは、ワークステーションユーザーは、AdobeIdentity Management System(IMS) を通じて自身を認証します。 ワークステーションを使用する前に、 [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=ja) 組織の管理者によって。

新しい認証およびユーザープロビジョニングモデルは、次の点で役立ちます。

* Admin Consoleを通じたユーザーおよびグループのセルフプロビジョニング。 ユーザーのライセンス権限を追加、削除、または変更する場合に、Adobeに問い合わせる必要はありません。
* 認証情報を使用してログインし、設定状態を失うことなく、複数のマシンから Workstation にアクセス。 ログアウト時にローカルキャッシュが削除され、現在のプロファイルが閉じられ、設定プロファイルがアクティブになります。

## はじめに

開始する前に、Adobeに連絡して組織をAdmin Consoleに追加してください。 購入したサービスに応じて、Adobeが組織をプロビジョニングします。 例えば、組織は、Attribution サービスかベータ版ビルド、またはその両方にアクセスできます。 組織を設定したら、組織管理者はユーザーとグループを追加できます。 詳しくは、 [Experience Cloudユーザーと製品を管理する](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) (Experience Cloud) を参照してください。 組織の管理者は、役割に応じて、様々なユーザーの使用制限を設定することもできます。 例えば、リリース前以外のユーザーは、ベータ版ビルドにアクセスする必要はありません。

Admin Consoleを通じてこの組織に追加された、プロビジョニングされた各Data Workbenchは、このユーザーを使用できます。 サブサービスは、製品へのアクセスに応じて、各ユーザーに対してのみ有効または無効にできます。 ユーザーが証明書から IMS にアップグレードされると、すべてのローカルデータが新しい IMS ユーザーディレクトリにコピーされます。

>[!NOTE]
>
>アクセストークンが更新されない限り、セッションはサーバー上で 6 時間、クライアント上で 23 時間続きます。 トークンが更新されると、再度ログインしなくてもクライアントを使用できます。

ユーザーにアクセス権を付与する前に、管理者がAdmin Consoleで 1 つ以上の製品レベル設定を作成する必要があります。

ブール値のフラグ **IMS を使用** は [!DNL Insight.cfg] 証明書モードにフォールバックします。 IMS ユーザーのアクセス制御の設定について詳しくは、 [アクセス制御ファイルの更新](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## 競合の解決

ユーザーが同じプロファイルで同じ IMS アカウントを持つ複数のマシンにログオンし、いずれかのマシンがオフラインモードの場合、 `.conflict` が作成され、ポップアップウィンドウが表示されます。 これは、 の両方のマシンで同期済み [!DNL User\Profile\] （サーバーおよびクライアント上） バックアップは `.conflict` ファイルに含まれているデータは失われません。 のブール値フラグ [!DNL Insight.cfg] には、この競合のポップアップを無効にする機能があります。

フラグ：競合の通知

これは、ワークスペース、指標、ディメンションなどに適用されます。 を選択します。
