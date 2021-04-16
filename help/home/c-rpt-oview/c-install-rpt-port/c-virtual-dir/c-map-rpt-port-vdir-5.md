---
description: レポートポータルを仮想ディレクトリ(IIS 5.0)にマップする手順です。
title: 仮想ディレクトリ（IIS 5.0）への Report Portal のマッピング
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
exl-id: 20d8e9ea-c5b6-4a1b-9b15-557cc71ad5d9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# 仮想ディレクトリ（IIS 5.0）への Report Portal のマッピング{#mapping-report-portal-to-a-virtual-directory-iis}

レポートポータルを仮想ディレクトリ(IIS 5.0)にマップする手順です。

1. [!DNL Report Portal]がインストールされているマシンで、**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**&#x200B;または&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**&#x200B;を使用してIISマネージャを開始します。

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. **[!UICONTROL Default Web Site]**&#x200B;を右クリックし、**[!UICONTROL New]**/**[!UICONTROL Virtual Directory]**&#x200B;を選択します。

1. [!DNL Virtual Directory Wizard]が開いたら、**[!UICONTROL Next]**&#x200B;をクリックします。

1. 次の手順を実行して、[!DNL Report Portal]のルート仮想ディレクトリを定義します。

   1. エイリアスの入力を求められたら、[!DNL Report Portal]の名前を入力し、**[!UICONTROL Next]**&#x200B;をクリックします。 例えば、[!DNL Report Portal]の名前に「Portal」を使用する場合は、エイリアス「Portal」を仮想ディレクトリに割り当てます。 終了したら「**[!UICONTROL Next]**」をクリックします。

   1. 物理パスの入力を求められたら、*&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]**&#x200B;ディレクトリを参照して選択し、**[!UICONTROL Next]**&#x200B;をクリックします。

      例：[!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. 権限の入力を求められたら、次のオプションが有効になっていることを確認します。

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. 「**[!UICONTROL Next]**」、「**[!UICONTROL Finish]**」の順にクリックします。作成した仮想ディレクトリは、次の例に示すように、既定のWebサイトの下に表示されます。

   ![](assets/RptPort_scrn_VirDirManual.png)

1. 作成した仮想ディレクトリを右クリックし、**[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**&#x200B;を選択します。

1. [!DNL Virtual Directory]ウィザードを使用して、次の物理ディレクトリのそれぞれにエイリアスを作成します。 これを行うと、これらの物理リソースのそれぞれに対して適切な名前の仮想ディレクトリが作成されます。

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> このエイリアスを作成します。.. </th> 
   <th colname="col2" class="entry"> この物理リソースに対して。.. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Core </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 画像 </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 出力 </td> 
   <td colname="col2"> <p><span class="keyword">レポートサーバー</span>がレポートセットの出力を保存するディレクトリの物理的な場所。 出力フォルダーは任意の場所に配置でき、任意の名前を付けることができ、各レポートセットのサブフォルダーを含めることができます。 </p> <p>これは、レポートセットの<span class="filepath"> Report.cfg</span>ファイルのOutput Rootパラメーターに指定するのと同じディレクトリにする必要があります。 詳しくは、<a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Report.cfgファイルの設定</a>を参照してください。 </p> <p>デフォルトの場所は\<i>PortalName</i>\PortalFiles\Outputです。 </p> <p>例：<span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p><i>PortalName</i>\PortalFiles\Output directory contains the <span class="filepath">プロファイル.xml</span>ファイル。このファイルは、このエイリアスに指定する出力ディレクトリに移動する必要があります。 </p> <p><span class="wintitle">パス</span>属性を正しく設定することが重要です。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 完了したら、IISに6つの新しい仮想ディレクトリが表示されることを確認します。 ディレクトリ構造に、（ポータルと同じ名前の）1つの親フォルダーと、次に示す5つのサブフォルダーがあることを確認します。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 終了したら、[Edit the Session Configuration File](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)に移動し、インストールプロセスを続行します。
