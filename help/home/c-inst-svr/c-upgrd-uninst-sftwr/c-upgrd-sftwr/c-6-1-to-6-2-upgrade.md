---
description: Data Workbench6.2および6.2.2用のサーバーコンポーネントのアップグレード
title: DWBサーバーの6.1から6.2へのアップグレード
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 51%

---

# DWB サーバーのアップグレード：6.1 から 6.2 へ{#dwb-server-upgrade-to}

Data Workbench6.2および6.2.2用のサーバーコンポーネントのアップグレード

## 6.2のアップグレードの問題 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* アトリビューションプロファイルは、Analytics（SC／Insight）のデータフィードを利用する Adobe SC プロファイルを実装しているユーザー用に設定されています。デフォルトでは、ルールに基づくモデルで評価されたデフォルトのインタラクションとしてマーケティングイベントとコンバージョンイベントが使用されます。詳しくは、[アトリビューションプロファイルのデプロイ](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)を参照してください。
* Data Workbench6.2にアップグレードするAdobeSCプロファイルのユーザーがデフォルト設定を使用していない場合は、[!DNL SC Fields.cfg]ファイルの[!DNL x-bot_id]値が正しくデコードされ、[!DNL Decoding Instructions.cfg]および[!DNL Exclude Hit.cfg]ファイルに[!DNL x-bot_id]フィールドが正しくリストされていることを確認します。 これは、設定ファイルをデフォルトの設定から変更している場合にのみ問題となります。
* Adobe SC プロファイルの [!DNL Dataset > Log Processing > SC Fields.cfg] ファイル内の未使用のフィールドを削除した場合は、アトリビューションプロファイルに使用している更新されたフィールド値に対応するように更新する必要があります（[アトリビューションプロファイルのデプロイ](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)を参照してください）。

## 6.2.2のアップグレードの問題 {#section-8704a9ac358246cd81233dd0982d534f}

* **[!UICONTROL Browsers]**&#x200B;および&#x200B;**[!UICONTROL Operating Systems]**&#x200B;参照ファイルは、従来の&#x200B;**[!UICONTROL Traffic]**&#x200B;プロファイル（例：[!DNL Lookups\Traffic\Browsers.txt)]）内では更新されません。 代わりに、**[!UICONTROL Traffic]**&#x200B;プロファイルの設定ではDeviceAtlasバンドル([!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle])を使用してこの設定情報を提供します。
* Data Workbench 6.2.1は、32-bit クライアントアプリケーションのダウンロードを提供する最後のリリースになります。将来のすべてのクライアントアプリケーションのダウンロードは 64-bit となり、引き続き Windows 7 またはそれ以降が必要となります。6.1 リリースから開始される 64-bit アプリケーションの導入により、32-bit アプリケーションのメモリの制限に対処します。

>[!NOTE]
>
>32ビット版のData Workbenchクライアントアプリケーションでは、クラスタリングおよびスコアリング機能を使用して予測モデルを実行する際に、メモリの制限に関する潜在的な問題が発生する場合があります。
