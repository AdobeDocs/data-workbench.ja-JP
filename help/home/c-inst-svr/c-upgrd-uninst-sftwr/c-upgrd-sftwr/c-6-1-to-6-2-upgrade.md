---
description: Data Workbench 6.2および6.2.2用のサーバーコンポーネントのアップグレード
title: DWB Server 6.1から6.2へのアップグレード
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# DWBサーバーのアップグレード：6.1 ～ 6.2{#dwb-server-upgrade-to}

Data Workbench 6.2および6.2.2用のサーバーコンポーネントのアップグレード

## 6.2のアップグレードの問題 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* アトリビューションプロファイルは、Analytics（SC／Insight）のデータフィードを利用する Adobe SC プロファイルを実装しているユーザー用に設定されています。デフォルトでは、ルールに基づくモデルで評価されたデフォルトのインタラクションとしてマーケティングイベントとコンバージョンイベントが使用されます。詳しくは、[アトリビューションプロファイルのデプロイ](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html)を参照してください。
* For users of the Adobe SC profile upgrading to Data Workbench 6.2, if you are not using the default configurations, verify that the [!DNL x-bot_id] value in the [!DNL SC Fields.cfg] file is being decoded properly and that the [!DNL x-bot_id] field is listed properly in the [!DNL Decoding Instructions.cfg] and the [!DNL Exclude Hit.cfg] files. これは、設定ファイルをデフォルトの設定から変更している場合にのみ問題となります。
* Adobe SC プロファイルの [!DNL Dataset > Log Processing > SC Fields.cfg] ファイル内の未使用のフィールドを削除した場合は、アトリビューションプロファイルに使用している更新されたフィールド値に対応するように更新する必要があります（[アトリビューションプロファイルのデプロイ](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html)を参照してください）。

## 6.2.2のアップグレードの問題 {#section-8704a9ac358246cd81233dd0982d534f}

* および **[!UICONTROL Browsers]** 参照フ **[!UICONTROL Operating Systems]** ァイルは、従来のプロファイル（例えば、） **[!UICONTROL Traffic]** 内では更新されませ [!DNL Lookups\Traffic\Browsers.txt)]ん。 Instead, configuration of the **[!UICONTROL Traffic]** profile will utilize the DeviceAtlas bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) to provide this configuration information.
* Data Workbench 6.2.1は、32-bit クライアントアプリケーションのダウンロードを提供する最後のリリースになります。将来のすべてのクライアントアプリケーションのダウンロードは 64-bit となり、引き続き Windows 7 またはそれ以降が必要となります。6.1 リリースから開始される 64-bit アプリケーションの導入により、32-bit アプリケーションのメモリの制限に対処します。

>[!NOTE]
>
>32ビット版のData Workbenchクライアントアプリケーションでは、クラスタリングおよびスコアリング機能を使用して予測モデルを実行すると、メモリの制限に関連する潜在的な問題が発生する場合があります。

