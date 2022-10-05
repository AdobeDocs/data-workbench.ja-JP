---
description: 仮想ディレクトリ (IIS 6.0) に Report Portal をマッピングする手順です。
title: 仮想ディレクトリ（IIS 6.0）への Report Portal のマッピング
uuid: e09d23d7-09de-4180-8260-60527f47aa98
exl-id: 39335705-7391-49af-a63d-c0fe4ca3f8f0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 3%

---

# 仮想ディレクトリ（IIS 6.0）への Report Portal のマッピング{#mapping-report-portal-to-a-virtual-directory-iis}

{{eol}}

仮想ディレクトリ (IIS 6.0) に Report Portal をマッピングする手順です。

マッピング [!DNL Report Portal] IIS 6.0 上の仮想ディレクトリには、次の 3 つのタスクが含まれます。

1. [設定ファイルを編集します](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [設定ファイルの IIS への読み込み](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [IIS での Active Server Pages (ASP) の有効化](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

3 つの作業をすべて完了する必要があります。

## 設定ファイルを編集するには {#section-eaf1c58935074cfa840dac33e1286520}

1. 次のマシンで [!DNL Report Portal] がインストールされている場合は、メモ帳などのテキストエディターで\*PortalName*\ReportPortalSetup.xml を開きます。

1. エディターの検索と置換機能を使用して、文字列「VSVirtualPortalName」をポータル名でグローバルに置換（すべて置換）します。 例えば、「VisualReportPortal」を [!DNL Report Portal]「VSVirtualPortalName」を検索し、「VisualReportPortal」に置き換えます。
1. このファイル内で次の要素を見つけます。

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. この要素の [!DNL Path] ディレクトリの物理的な場所の属性 [!DNL Report Server] レポートセットの出力を保存します。

   出力フォルダは任意の場所に配置し、任意の名前を付けることができ、各レポートセットのサブフォルダを含めます。

   >[!NOTE]
   >
   >これは、 [!DNL Report.cfg] ファイルに含める必要があります。 詳しくは、 [Report.cfg ファイルの設定](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d).

   次のコードサンプルは、 [!DNL Path] 属性 [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >これは非常に重要です [!DNL Path] 属性が正しく設定されている。

1. デフォルトの [!DNL Path] の [!DNL Output] 要素、移動 [!DNL profiles.xml] ファイルを *\PortalName*\PortalFiles\Output フォルダを手順 4 で指定した出力ディレクトリに移動します。 上記の例では、 [!DNL profiles.xml] から [!DNL E:\VSReport\ReportOutput].

1. を確認します。 [!DNL Path] その他すべての [!DNL IIsWebVirtualDir] 要素は、 [!DNL C:\Inetpub\wwwroot] をクリックし、それぞれを正しいパスに置き換えます。

1. ファイルを保存します。元のファイルを保持する場合は、新しい名前で設定ファイルを保存できます。

## 設定ファイルを IIS に読み込むには {#section-9d61f6bfa93846dcb96973fec5573b19}

1. 次のマシンで [!DNL Report Portal] がインストールされている場合は、次を使用して IIS Manager を起動します。 **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. Select **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 右クリック **[!UICONTROL Default Web Site]** を選択し、 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** （ファイルから）。

1. を選択します。 **[!UICONTROL ReportPortalSetup.xml]** ファイルを開き、 **[!UICONTROL Read File]**.

1. 6 つの仮想ディレクトリが [!DNL Report Portal] を次の例に示します。

   ![](assets/rptPort_dia_VirDirs.png)

   6 つの仮想ディレクトリが表示されない場合や、エラーメッセージが表示された場合は、 **[!UICONTROL Cancel]** 設定ファイルでエラーがないかを調べます。

1. リスト内の最初の仮想ディレクトリ（他の 5 つのディレクトリの親ディレクトリ）を選択し、 **[!UICONTROL OK]**. IIS はマッピングをインポートし、仮想ディレクトリをデフォルト Web サイトに追加します。

   結果のディレクトリ構造に、1 つの親フォルダー（ポータルと同じ名前）と 5 つのサブディレクトリ（次の例に示すように）が含まれていることを確認します。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 各仮想ディレクトリをクリックして、IIS が表す物理ディレクトリを特定できるようにします。 IIS でエラーが表示される場合は、仮想ディレクトリ名を右クリックし、 [!DNL Local Path] フィールドが正しい物理ディレクトリを指している。

## IIS で Active Server Pages (ASP) を有効にするには {#section-a7725ec2afc64ffc854c5bd8c5c31802}

使用する [!DNL Report Portal]、ASP は IIS で有効にする必要があります。 （IIS 6.0 がインストールされている場合、ASP はデフォルトで無効になっています。） 次の手順を実行して、IIS で ASP が有効になっていることを確認します。

1. IIS マネージャーウィンドウで、「 **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**.
1. を確認します。 [!DNL Active Server Pages] 拡張機能はに設定されています。 [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. ステータスが「禁止」の場合は、 **[!UICONTROL Active Server Pages]** をクリックし、 **[!UICONTROL Allow]**.
1. IIS Manager を閉じます。
