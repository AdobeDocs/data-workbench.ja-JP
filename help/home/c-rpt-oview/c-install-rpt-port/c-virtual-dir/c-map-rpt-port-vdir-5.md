---
description: 仮想ディレクトリ (IIS 5.0) に Report Portal をマッピングする手順です。
title: 仮想ディレクトリ（IIS 5.0）への Report Portal のマッピング
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
exl-id: 20d8e9ea-c5b6-4a1b-9b15-557cc71ad5d9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# 仮想ディレクトリ（IIS 5.0）への Report Portal のマッピング{#mapping-report-portal-to-a-virtual-directory-iis}

{{eol}}

仮想ディレクトリ (IIS 5.0) に Report Portal をマッピングする手順です。

1. 次のマシンで [!DNL Report Portal] がインストールされている場合は、次のいずれかを使用して IIS Manager を起動します。 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** または **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 右クリック **[!UICONTROL Default Web Site]** を選択し、 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. 次の場合に [!DNL Virtual Directory Wizard] 開く、クリック **[!UICONTROL Next]**.

1. 次の手順を実行して、のルート仮想ディレクトリを定義します。 [!DNL Report Portal]:

   1. エイリアスの入力を求められたら、 [!DNL Report Portal]を選択し、「 **[!UICONTROL Next]**. 例えば、「Portal」を [!DNL Report Portal]で、仮想ディレクトリにエイリアス「Portal」を割り当てます。 終了したら「**[!UICONTROL Next]**」をクリックします。

   1. 物理パスの入力を求められたら、を参照し、 *&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]** ディレクトリに移動し、 **[!UICONTROL Next]**.

      例：[!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. 権限の入力を求められたら、次のオプションが有効になっていることを確認します。

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. 「**[!UICONTROL Next]**」、「**[!UICONTROL Finish]**」の順にクリックします。作成した仮想ディレクトリは、次の例に示すように、[ 既定の Web サイト ] の下に表示されます。

   ![](assets/RptPort_scrn_VirDirManual.png)

1. 作成した仮想ディレクトリを右クリックし、「 」を選択します。 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. 以下を使用： [!DNL Virtual Directory] ウィザードを使用して、次の各物理ディレクトリのエイリアスを作成します。 これにより、これらの物理リソースごとに適切な名前の仮想ディレクトリが作成されます。

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> このエイリアスを作成します。.. </th> 
   <th colname="col2" class="entry"> この物理リソースの場合。.. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> コア </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 画像 </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 出力 </td> 
   <td colname="col2"> <p>ディレクトリの物理的な場所 <span class="keyword"> レポートサーバー</span> レポートセットの出力を保存します。 出力フォルダは任意の場所に配置し、任意の名前を付けることができ、各レポートセットのサブフォルダを含めます。 </p> <p>これは、 <span class="filepath"> Report.cfg</span> ファイルに含める必要があります。 詳しくは、 <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Report.cfg ファイルの設定</a>. </p> <p>デフォルトの場所は\<i>PortalName</i>\PortalFiles\Output. </p> <p>例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>この <i>PortalName</i>\PortalFiles\Output ディレクトリには <span class="filepath"> profiles.xml</span> ファイル。このエイリアスに指定した出力ディレクトリに移動する必要があります。 </p> <p>これは非常に重要です <span class="wintitle"> パス</span> 属性が正しく設定されている。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 完了したら、IIS に 6 つの新しい仮想ディレクトリが表示されることを確認します。 ディレクトリ構造に、以下に示すように、1 つの親フォルダー（ポータルと同じ名前）と 5 つのサブフォルダーがあることを確認します。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 終了したら、に移動します。 [セッション構成ファイルの編集](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) をクリックして、インストールプロセスを続行します。
