---
description: 仮想ディレクトリ(IIS 6.0)にReport Portalをマッピングする手順です。
title: 仮想ディレクトリ（IIS 6.0）への Report Portal のマッピング
uuid: e09d23d7-09de-4180-8260-60527f47aa98
exl-id: 39335705-7391-49af-a63d-c0fe4ca3f8f0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 3%

---

# 仮想ディレクトリ（IIS 6.0）への Report Portal のマッピング{#mapping-report-portal-to-a-virtual-directory-iis}

仮想ディレクトリ(IIS 6.0)にReport Portalをマッピングする手順です。

[!DNL Report Portal]をIIS 6.0上の仮想ディレクトリにマッピングするには、次の3つのタスクが必要です。

1. [設定ファイルの編集](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [設定ファイルのIISへの読み込み](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [IISでのActive Server Pages (ASP)の有効化](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

3つの作業をすべて完了する必要があります。

## 設定ファイル{#section-eaf1c58935074cfa840dac33e1286520}を編集するには

1. [!DNL Report Portal]がインストールされているマシン上で、\*PortalName*\ReportPortalSetup.xmlをメモ帳などのテキストエディターで開きます。

1. エディターの検索と置換機能を使用して、「VSVirtualPortalName」という文字列をポータル名にグローバルに置き換えます（「すべて置換」）。 例えば、「VisualReportPortal」を[!DNL Report Portal]の名前として使用する場合は、「VSVirtualPortalName」を検索して「VisualReportPortal」に置き換えます。
1. このファイル内で次の要素を探します。

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. この要素の[!DNL Path]属性を、[!DNL Report Server]がレポートセットの出力を保存するディレクトリの物理的な場所に設定します。

   出力フォルダーは、任意の場所に配置し、任意の名前を付けて、各レポートセットのサブフォルダーを含めることができます。

   >[!NOTE]
   >
   >これは、レポートセット用の[!DNL Report.cfg]ファイルの出力ルートパラメーターで指定するディレクトリと同じである必要があります。 詳しくは、[Report.cfgファイルの設定](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d)を参照してください。

   次のコード例は、レポートが[!DNL E:\VSReport\ReportOutput]に保存された場合に[!DNL Path]属性を設定する方法を示しています。

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >[!DNL Path]属性が正しく設定されていることが重要です。

1. [!DNL Output]要素のデフォルトの[!DNL Path]を変更した場合は、*\PortalName*\PortalFiles\Output folder to the output directory that you specified in Step 4ディレクトリから[!DNL profiles.xml]ファイルを移動します。 上記の例では、[!DNL profiles.xml]を[!DNL E:\VSReport\ReportOutput]に移動します。

1. 他のすべての[!DNL IIsWebVirtualDir]要素の[!DNL Path]属性が正しい場所にマッピングされていることを確認します。そのためには、[!DNL C:\Inetpub\wwwroot]のすべてのインスタンスを検索し、それぞれを正しいパスに置き換えます。

1. ファイルを保存します。元のファイルを保持する場合は、新しい名前で設定ファイルを保存できます。

## 構成ファイルをIISに読み込むには{#section-9d61f6bfa93846dcb96973fec5573b19}

1. [!DNL Report Portal]がインストールされているマシンで、**[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**&#x200B;を使用してIISマネージャーを起動します。

1. Select **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. **[!UICONTROL Default Web Site]**&#x200B;を右クリックし、**[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**（ファイルから）を選択します。

1. **[!UICONTROL ReportPortalSetup.xml]**&#x200B;ファイルを選択し、「**[!UICONTROL Read File]**」をクリックします。

1. 次の例に示すように、[!DNL Report Portal]に対して6つの仮想ディレクトリがリストされていることを確認します。

   ![](assets/rptPort_dia_VirDirs.png)

   6つの仮想ディレクトリが表示されない場合や、エラーメッセージが表示された場合は、**[!UICONTROL Cancel]**&#x200B;をクリックし、設定ファイルでエラーがないか確認します。

1. リスト内の最初の仮想ディレクトリ（他の5つの親ディレクトリ）を選択し、**[!UICONTROL OK]**&#x200B;をクリックします。 IISはマッピングをインポートし、仮想ディレクトリを既定のWebサイトに追加します。

   結果のディレクトリ構造に、1つの親フォルダー（ポータルと同じ名前）と5つのサブディレクトリ（以下の例に示すように）が含まれていることを確認します。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 各仮想ディレクトリをクリックして、IISがそのディレクトリが表す物理ディレクトリを特定できるようにします。 IISでエラーが表示される場合は、仮想ディレクトリ名を右クリックし、[!DNL Local Path]フィールドが正しい物理ディレクトリを指していることを確認します。

## IISのActive Server Pages (ASP)を有効にするには{#section-a7725ec2afc64ffc854c5bd8c5c31802}

[!DNL Report Portal]を使用するには、IISでASPを有効にする必要があります。 （デフォルトでは、IIS 6.0がインストールされている場合、ASPは無効になっています）。 IISでASPが有効になっていることを確認するには、次の手順を実行します。

1. IISマネージャーウィンドウで、**[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**&#x200B;を選択します。
1. [!DNL Active Server Pages]拡張が[!DNL Allowed]に設定されていることを確認します。

   ![](assets/report_aspenable.png)

1. 「ステータス」が「禁止」の場合は、「**[!UICONTROL Active Server Pages]**」を選択し、「**[!UICONTROL Allow]**」をクリックします。
1. IISマネージャーを閉じます。
