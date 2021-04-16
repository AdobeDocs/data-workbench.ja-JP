---
description: data workbenchGeographyをアンインストールする手順です。
title: Data Workbench Geography のアンインストール
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 8%

---

# Data Workbench Geography のアンインストール{#uninstalling-data-workbench-geography}

data workbenchGeographyをアンインストールする手順です。

>[!NOTE]
>
>Data Workbench [!DNL Geography]を使用しているプロファイルーがData Workbenchサーバークラスター上で実行されている場合は、クラスター内のマスターData Workbenchサーバーから[!DNL Geography]プロファイルーをアンインストールします。

1. 次の手順を使用して、data workbench [!DNL Geography]を使用していた各プロファイルの[!DNL profile.cfg]ファイルを更新します。

   1.  [!DNL Profile Manager].
   1. [!DNL profile.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL from the workbench]**&#x200B;をクリックします。 [!DNL profile.cfg]ウィンドウが表示されます。

   1. [!DNL profile.cfg]ウィンドウで、[!DNL Directories]ベクトルから[!DNL Geography]プロファイルエントリを削除します。

   1. データサービスを使用している場合は、[!DNL Directories]ベクトルから[!DNL IP Geo-intelligence]または[!DNL IP Geo-location]プロファイルエントリを削除します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Profile Manager]で、[!DNL User]列の[!DNL profile.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL profile name]**>*&#x200B;をクリックします。

1. Data WorkbenchサーバーのインストールディレクトリにあるプロファイルフォルダーからGeographyフォルダーを削除します。
1. Data Serviceを使用している場合は、Data WorkbenchサーバーのインストールディレクトリにあるプロファイルフォルダーからIP Geo-IntelligenceフォルダーまたはIP Geo-locationフォルダーを削除します。
1. Data WorkbenchサーバーのインストールディレクトリにあるLookupsフォルダーからGeographyフォルダーを削除します。
1. データサービスを使用している場合は、Data WorkbenchサーバーのインストールディレクトリにあるLookupsフォルダーからIP Geo-IntelligenceフォルダーまたはIP Geo-locationフォルダーを削除します。
1. 新しい地形画像を作成した場合は、Data Workbenchサーバーのインストールディレクトリ内のComponentsフォルダーから[!DNL Terrain Images.cfg]ファイルを削除します。
