---
description: レポートポータルを仮想ディレクトリ(IIS 6.0)にマップする手順です。
solution: Analytics
title: 仮想ディレクトリ(IIS 6.0)へのレポートポータルのマッピング
topic: Data workbench
uuid: e09d23d7-09de-4180-8260-60527f47aa98
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 仮想ディレクトリ(IIS 6.0)へのレポートポータルのマッピング{#mapping-report-portal-to-a-virtual-directory-iis}

レポートポータルを仮想ディレクトリ(IIS 6.0)にマップする手順です。

IIS 6.0上の仮 [!DNL Report Portal] 想ディレクトリにをマッピングするには、次の3つのタスクが必要です。

1. [設定ファイルの編集](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [IISへの構成ファイルの読み込み](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [IISでActive Server Pages (ASP)を有効にする](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

3つのタスクをすべて完了する必要があります。

## To Edit the Configuration File {#section-eaf1c58935074cfa840dac33e1286520}

1. がインストールされ [!DNL Report Portal] ているマシンで、\*PortalName*\ReportPortalSetup.xmlをメモ帳などのテキストエディターで開きます。

1. エディターの検索と置換機能を使用して、「VSVirtualPortalName」という文字列をポータル名でグローバルに置換（すべて置換）します。 例えば、「VisualReportPortal」をの名前として使用する場合は、「VSVirtualPortalName」を検索し [!DNL Report Portal]て「VisualReportPortal」に置き換えます。
1. このファイル内で次の要素を探します。

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. この要素の属性を、レポ [!DNL Path] ートセットの出力を保存するディレクトリの [!DNL Report Server] 物理的な場所に設定します。

   出力フォルダーは任意の場所に配置でき、任意の名前を付けることができ、各レポートセットのサブフォルダーを含めることができます。

   >[!NOTE]
   >
   >このディレクトリは、レポートセットのファイル内のOutput Rootパラメーターで指定したのと同じデ [!DNL Report.cfg] ィレクトリである必要があります。 詳しくは、Report.cfgファイル [の設定を参照してください](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d)。

   次のコードの例は、レポートをに保存した場合に [!DNL Path] 属性を設定する方法を示していま [!DNL E:\VSReport\ReportOutput]す。

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >属性が適切に設定されてい [!DNL Path] ることが重要です。

1. 要素のデフォルトを変 [!DNL Path] 更した [!DNL Output] 場合は、ファイル [!DNL profiles.xml] を\PortalName *\PortalFiles\Output folder to the output directory that you specified in Step 4ディレクトリから*&#x200B;移動します。 上の例では、に移動し [!DNL profiles.xml] ます [!DNL E:\VSReport\ReportOutput]。

1. 他のすべての要素 [!DNL Path] の属性が正しい場所にマッピ [!DNL IIsWebVirtualDir] ングされていることを確認します。すべてのインスタンスを検索し、それぞ [!DNL C:\Inetpub\wwwroot] れを正しいパスに置き換えます。

1. ファイルを保存します。元のファイルを保持する場合は、新しい名前を使用して設定ファイルを保存できます。

## 構成ファイルをIISにインポートするには {#section-9d61f6bfa93846dcb96973fec5573b19}

1. がインストールされて [!DNL Report Portal] いるコンピューターで、>を使用してIISマネー **[!UICONTROL Start]** ジャーを起 **[!UICONTROL Administrative Tools]** 動しま **[!UICONTROL Internet Information Systems (IIS) Manager]**&#x200B;す。

1. Select **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 右クリックし、 **[!UICONTROL Default Web Site]** /(ファ **[!UICONTROL New]** イルから) **[!UICONTROL Virtual Directory]** を選択します。

1. ファイルを選択 **[!UICONTROL ReportPortalSetup.xml]** し、をクリックしま **[!UICONTROL Read File]**&#x200B;す。

1. 次の例に示すように、6つの仮想ディレクトリがユーザーに対し [!DNL Report Portal] て表示されていることを確認します。

   ![](assets/rptPort_dia_VirDirs.png)

   6つの仮想ディレクトリが表示されない場合や、エラーメッセージが表示された場合は、をクリックして、 **[!UICONTROL Cancel]** 設定ファイルのエラーを確認します。

1. リスト内の最初の仮想ディレクトリ（他の5つの親ディレクトリ）を選択し、をクリックします **[!UICONTROL OK]**。 IISはマッピングをインポートし、仮想ディレクトリを既定のWebサイトに追加します。

   結果のディレクトリ構造に、（ポータルと同じ名前の）1つの親フォルダーと、次の例に示す5つのサブディレクトリが含まれていることを確認します。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 各仮想ディレクトリをクリックして、IISがその仮想ディレクトリが表す物理ディレクトリを見つけられることを確認します。 IISでエラーが表示された場合は、仮想ディレクトリ名を右クリックし、フィールドが正しい物理ディレク [!DNL Local Path] トリを指していることを確認します。

## IISでActive Server Pages (ASP)を有効にするには {#section-a7725ec2afc64ffc854c5bd8c5c31802}

を使用するに [!DNL Report Portal]は、IISでASPを有効にする必要があります。 （既定では、IIS 6.0がインストールされている場合、ASPは無効になっています）。IISでASPが有効になっていることを確認するには、次の手順を実行します。

1. IISマネージャウィンドウで、/を選 **[!UICONTROL (local computer)]** 択しま **[!UICONTROL Web Service Extensions]**&#x200B;す。
1. 拡張がに設定され [!DNL Active Server Pages] ていることを確認しま [!DNL Allowed]す。

   ![](assets/report_aspenable.png)

1. ステータスが「禁止」の場合は、を選択し **[!UICONTROL Active Server Pages]** てをクリックしま **[!UICONTROL Allow]**&#x200B;す。
1. IISマネージャを閉じます。

