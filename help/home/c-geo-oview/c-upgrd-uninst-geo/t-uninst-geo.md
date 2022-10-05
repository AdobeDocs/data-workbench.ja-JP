---
description: Data WorkbenchGeography をアンインストールする手順です。
title: Data Workbench Geography のアンインストール
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 8%

---

# Data Workbench Geography のアンインストール{#uninstalling-data-workbench-geography}

{{eol}}

Data WorkbenchGeography をアンインストールする手順です。

>[!NOTE]
>
>Data Workbench を使用しているプロファイルの場合 [!DNL Geography] が data workbench サーバークラスターで実行されている場合は、 [!DNL Geography] クラスター内のマスター data workbench サーバーからのプロファイル。

1. 次の手順を使用して、 [!DNL profile.cfg] data workbench を使用している各プロファイルのファイル [!DNL Geography].

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックします。 [!DNL profile.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. この [!DNL profile.cfg] ウィンドウが表示されます。

   1. 内 [!DNL profile.cfg] ウィンドウで、 [!DNL Geography] プロファイルエントリ [!DNL Directories] ベクトル。

   1. データサービスを使用している場合、 [!DNL IP Geo-intelligence] または [!DNL IP Geo-location] プロファイルエントリ [!DNL Directories] ベクトル。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Profile Manager]、次のチェックマークを右クリック： [!DNL profile.cfg] 内 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Data Workbench サーバーのインストールディレクトリにある Profiles フォルダーから Geography フォルダーを削除します。
1. データサービスを使用している場合は、Data Workbench サーバーのインストールディレクトリにある Profiles フォルダーから IP Geo-Intelligence フォルダーまたは IP Geo-location フォルダーを削除します。
1. Data Workbench サーバーのインストールディレクトリにある Lookups フォルダーから Geography フォルダーを削除します。
1. データサービスを使用している場合は、Data Workbench サーバーのインストールディレクトリにある Lookups フォルダーから IP Geo-intelligence フォルダーまたは IP Geo-location フォルダーを削除します。
1. 新しい地形画像を作成した場合は、 [!DNL Terrain Images.cfg] ファイルを data workbench サーバーのインストールディレクトリにある Components フォルダーから取得します。
