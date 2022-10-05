---
description: Data Workbench6.2 および 6.2.2 用のサーバーコンポーネントのアップグレード。
title: DWB サーバーの 6.1 から 6.2 へのアップグレード
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 51%

---

# DWB サーバーのアップグレード：6.1 から 6.2 へ{#dwb-server-upgrade-to}

{{eol}}

Data Workbench6.2 および 6.2.2 用のサーバーコンポーネントのアップグレード。

## 6.2 のアップグレードの問題 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* アトリビューションプロファイルは、Analytics（SC／Insight）のデータフィードを利用する Adobe SC プロファイルを実装しているユーザー用に設定されています。デフォルトでは、ルールに基づくモデルで評価されたデフォルトのインタラクションとしてマーケティングイベントとコンバージョンイベントが使用されます。詳しくは、[アトリビューションプロファイルのデプロイ](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)を参照してください。
* AdobeSC プロファイルをData Workbench6.2 にアップグレードする場合、デフォルトの設定を使用しない場合は、 [!DNL x-bot_id] 値を [!DNL SC Fields.cfg] ファイルが正しくデコードされ、 [!DNL x-bot_id] フィールドが [!DNL Decoding Instructions.cfg] そして [!DNL Exclude Hit.cfg] ファイル。 これは、設定ファイルをデフォルトの設定から変更している場合にのみ問題となります。
* Adobe SC プロファイルの [!DNL Dataset > Log Processing > SC Fields.cfg] ファイル内の未使用のフィールドを削除した場合は、アトリビューションプロファイルに使用している更新されたフィールド値に対応するように更新する必要があります（[アトリビューションプロファイルのデプロイ](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)を参照してください）。

## 6.2.2 のアップグレードの問題 {#section-8704a9ac358246cd81233dd0982d534f}

* この **[!UICONTROL Browsers]** および **[!UICONTROL Operating Systems]** 参照ファイルは、従来の **[!UICONTROL Traffic]** プロファイル ( 例： [!DNL Lookups\Traffic\Browsers.txt)]. 代わりに、 **[!UICONTROL Traffic]** プロファイルは DeviceAtlas バンドル ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) をクリックして、この設定情報を指定します。
* Data Workbench 6.2.1は、32-bit クライアントアプリケーションのダウンロードを提供する最後のリリースになります。将来のすべてのクライアントアプリケーションのダウンロードは 64-bit となり、引き続き Windows 7 またはそれ以降が必要となります。6.1 リリースから開始される 64-bit アプリケーションの導入により、32-bit アプリケーションのメモリの制限に対処します。

>[!NOTE]
>
>32 ビット版のData Workbenchクライアントアプリケーションでは、クラスタリングおよびスコアリング機能を使用して予測モデルを実行する際に、メモリ制限に関連する潜在的な問題が発生する場合があります。
