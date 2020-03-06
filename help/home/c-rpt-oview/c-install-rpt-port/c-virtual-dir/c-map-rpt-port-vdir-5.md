---
description: レポートポータルを仮想ディレクトリ(IIS 5.0)にマップする手順です。
solution: Analytics
title: 仮想ディレクトリ(IIS 5.0)へのレポートポータルのマッピング
topic: Data workbench
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 仮想ディレクトリ(IIS 5.0)へのレポートポータルのマッピング{#mapping-report-portal-to-a-virtual-directory-iis}

レポートポータルを仮想ディレクトリ(IIS 5.0)にマップする手順です。

1. がインストールされているマシンで、> > > >または> > [!DNL Report Portal] > **[!UICONTROL Start]** >を使用してIISマネージャ **[!UICONTROL Control Panel]** を起 **[!UICONTROL Administrative Tools]****[!UICONTROL Internet Information Services]****[!UICONTROL Start]****[!UICONTROL Administrative Tools]****[!UICONTROL Internet Information Services]**&#x200B;動します。

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 右クリックし、「/」 **[!UICONTROL Default Web Site]** を選択 **[!UICONTROL New]** します **[!UICONTROL Virtual Directory]**。

1. が開いたら、 [!DNL Virtual Directory Wizard] をクリックしま **[!UICONTROL Next]**&#x200B;す。

1. 次の手順を実行して、のルート仮想ディレクトリを定義しま [!DNL Report Portal]す。

   1. エイリアスの入力を求められたら、の名前を入力し、を [!DNL Report Portal]クリックしま **[!UICONTROL Next]**&#x200B;す。 例えば、「Portal」を自分の名前として使用する場合は、エイリアス「Portal」 [!DNL Report Portal]を仮想ディレクトリに割り当てます。 終了したら「**[!UICONTROL Next]**」をクリックします。

   1. 物理パスの入力を求められたら、 *&lt;>ディレクトリを参照し&#x200B;**[!UICONTROL PortalName]**て選択し* 、をク **[!UICONTROL \PortalASP]** リックしま **[!UICONTROL Next]**&#x200B;す。

      例：[!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. 権限の入力を求められたら、次のオプションが有効になっていることを確認します。

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Click **[!UICONTROL Next]**, then click **[!UICONTROL Finish]**. 作成した仮想ディレクトリが、次の例に示すように[既定のWebサイト]の下に表示されます。
   ![](assets/RptPort_scrn_VirDirManual.png)

1. 作成した仮想ディレクトリを右クリックし、/を選 **[!UICONTROL New]** 択します **[!UICONTROL Virtual Directory]**。

1. ウィザードを使 [!DNL Virtual Directory] 用して、次の物理ディレクトリのそれぞれにエイリアスを作成します。 これを行うと、これらの物理リソースのそれぞれに対して適切な名前の仮想ディレクトリが作成されます。

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
   <td colname="col2"> <p>Report Serverがレポートセットの出力を <span class="keyword"> 保存する</span> ディレクトリの物理的な場所。 出力フォルダーは任意の場所に配置でき、任意の名前を付けることができ、各レポートセットのサブフォルダーを含めることができます。 </p> <p>これは、レポートセットのReport.cfgファイルのOutput Rootパラメーターで指定したのと同じディレクトリである <span class="filepath"> 必要があります</span> 。 詳しくは、Report.cfgファイル <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> の設定を参照してください</a>。 </p> <p>デフォルトの場所は\<i>PortalName</i>\PortalFiles\Outputです。 </p> <p>例： <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p><i>PortalName</i>\PortalFiles\Output directory contains the profiles <span class="filepath"></span> .xmlファイル。このファイルは、このエイリアスに指定する出力ディレクトリに移動する必要があります。 </p> <p>[パス]属性が正しく設定さ <span class="wintitle"> れている</span> ことが重要です。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 完了したら、IISに6つの新しい仮想ディレクトリが表示されることを確認します。 ディレクトリ構造に、（ポータルと同じ名前の）1つの親フォルダーと、次に示す5つのサブフォルダーが含まれていることを確認します。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 完了したら、 [Edit the Session Configuration File](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) （セッション設定ファイルの編集）に移動し、インストールプロセスを続行します。

