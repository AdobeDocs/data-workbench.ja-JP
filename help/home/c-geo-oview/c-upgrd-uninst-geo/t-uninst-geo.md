---
description: data workbenchGeographyをアンインストールする手順です。
solution: Analytics
title: Data Workbench地域のアンインストール
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench地域のアンインストール{#uninstalling-data-workbench-geography}

data workbenchGeographyをアンインストールする手順です。

>[!NOTE]
>
>Data Workbenchを使用しているプロファイルがData Workbenchサーバークラスター上で実 [!DNL Geography] 行されている場合は、クラスター内のマスターData Workbenchサーバー [!DNL Geography] からプロファイルをアンインストールします。

1. 次の手順を使用して、Data Workbenchを使 [!DNL profile.cfg] 用していた各プロファイルのファイルを更新しま [!DNL Geography]す。

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックし、をク [!DNL profile.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL from the workbench]**&#x200B;す。 The [!DNL profile.cfg] window appears.

   1. ウィンドウ [!DNL profile.cfg] で、ベクトルからプロ [!DNL Geography] ファイルエントリを削除 [!DNL Directories] します。

   1. データサービスを使用している場合は、ベクトルから [!DNL IP Geo-intelligence] またはプ [!DNL IP Geo-location] ロファイルエントリを削除 [!DNL Directories] します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Profile Manager]のチェックマークを右クリ [!DNL profile.cfg] ックし [!DNL User] 、/ **[!UICONTROL Save to]** &lt; *>をクリック&#x200B;**[!UICONTROL profile name]**します*。

1. Data WorkbenchサーバーのインストールディレクトリにあるProfilesフォルダーからGeographyフォルダーを削除します。
1. データサービスを使用している場合は、Data WorkbenchサーバーのインストールディレクトリにあるProfilesフォルダーからIP Geo-IntelligenceフォルダーまたはIP Geo-Locationフォルダーを削除します。
1. Data WorkbenchサーバーのインストールディレクトリにあるLookupsフォルダーからGeographyフォルダーを削除します。
1. データサービスを使用している場合は、Data WorkbenchサーバーのインストールディレクトリにあるLookupsフォルダーからIP Geo-IntelligenceフォルダーまたはIP Geo-Locationフォルダーを削除します。
1. 新しい地形画像を作成した場合は、Data Workbenchサーバーのイ [!DNL Terrain Images.cfg] ンストールディレクトリにあるComponentsフォルダーからファイルを削除します。
