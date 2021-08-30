---
description: ワークステーションを使用して、Data Workbench・ユーザーを管理します。
title: ユーザーのセルフプロビジョニング
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# ユーザーのセルフプロビジョニング{#self-provisioning-of-users}

ワークステーションを使用して、Data Workbench・ユーザーを管理します。

ワークステーションを使用して、Data Workbenchから必要な証明書を設定し、Adobeに接続できます。 この証明書は、SSL通信と認証の両方で、ライセンスされたリソースおよび機能を使用する際に役立ちます。 証明書ベースの認証では、複数のマシンでワークステーションを使用するために、複数の証明書を取得して設定する必要があります。 また、ユーザーのプロビジョニングと使用権限はAdobeが管理します。新しい証明書または証明書の失効については、Adobeに問い合わせる必要があります。

DWB 6.7以降、ワークステーションはユーザー名とパスワードによるユーザー認証をサポートします。

証明書ベースの認証/承認は引き続きセットアップで機能しますが、新しい資格情報ベースの認証に移行することを強くお勧めします。 新しいアプローチでは、ワークステーションユーザーは、Identity ManagementAdobe(IMS)を使用して自分自身を認証します。 ワークステーションを使用する前に、組織の管理者から[Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=ja)を通じて機能にアクセスできるようにする必要があります。

新しい認証およびユーザープロビジョニングモデルは、次の点で役立ちます。

* ユーザーを通じたユーザーおよびグループの自己Admin Console。 ユーザーのライセンス権限を追加、削除、または変更する場合、Adobeに問い合わせる必要はありません。
* 資格情報を使用してログインし、構成状態を失わずに、複数のマシンからワークステーションにアクセス。 ログアウト時にローカルキャッシュが削除され、現在のプロファイルが閉じられ、設定プロファイルがアクティブになります。

## はじめに

開始する前に、Adobeに連絡して、組織をAdmin Consoleに追加します。 購入したサービスに応じて、Adobeが組織をプロビジョニングします。 例えば、組織は、Attributionサービスまたはベータ版ビルド、あるいはその両方にアクセスできます。 組織を設定したら、組織管理者はユーザーとグループを追加できます。 詳しくは、Experience Cloudの[Experience Cloudユーザーと製品の管理](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)を参照してください。 組織の管理者は、役割に応じて、様々なユーザーの使用制限を設定することもできます。 例えば、リリース前以外のユーザーは、ベータ版ビルドにアクセスする必要はありません。

Admin Consoleを通じてこの組織に追加された、プロビジョニング済みの各Data Workbenchは、ユーザーを使用できます。 サブサービスは、各ユーザーの製品アクセスに応じてのみ有効または無効にできます。 ユーザーが証明書からIMSにアップグレードされると、すべてのローカルデータが新しいIMSユーザーディレクトリにコピーされます。

>[!NOTE]
>
>アクセストークンが更新されない限り、セッションはサーバー上で6時間、クライアント上で23時間続きます。 トークンが更新されると、再度ログインすることなくクライアントを使用できます。

ユーザーにアクセス権を付与する前に、管理者がAdmin Consoleで少なくとも1つの製品レベル設定を作成する必要があります。

ブール型フラグ&#x200B;**Use IMS**&#x200B;を[!DNL Insight.cfg]に追加して、証明書モードにフォールバックできます。 IMSユーザーのアクセス制御の設定については、[アクセス制御ファイルの更新](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html)を参照してください。

## 競合の解決

ユーザーが同じプロファイルで同じIMSアカウントを持つ複数のマシンにログオンし、いずれかのマシンがオフラインモードの場合、`.conflict`が生成され、ポップアップウィンドウが表示されます。 これは、 サーバーとクライアントの両方のマシンで [!DNL User\Profile\] 同期。 `.conflict`ファイルにバックアップが作成され、データは失われません。 [!DNL Insight.cfg]のブール型フラグを使用すると、この競合ポップアップを無効にできます。

フラグ：競合の通知

これは、ワークスペース、指標、ディメンションなどに適用されます。 」と入力します。
