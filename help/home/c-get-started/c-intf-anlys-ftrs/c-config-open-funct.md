---
description: 「開く」機能を使用すると、ドキュメントや URI などの項目をテキストエディターや Web ブラウザーなどの外部アプリケーションで開けます。
solution: Analytics
title: 開く機能の設定
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 開く機能の設定{#configure-open-functionality}

「開く」機能を使用すると、ドキュメントや URI などの項目をテキストエディターや Web ブラウザーなどの外部アプリケーションで開けます。

「開く」機能は、現在 [!DNL Site] アプリケーションで、URI を開くためにのみ設定されています。この節では、[!DNL Site] 用の「URI を開く」機能の設定について説明します。別のアプリケーション用または他の項目を開くための「開く」機能の設定については、Adobe Consulting Services にお問い合わせください。

[!DNL Site] では、ページオーバーレイまたはテーブルから URI を右クリックすると、フォーマット対象のアプリケーションでその URI が表示されます。例えば、URI テーブルのビジュアライゼーションから URI をクリックすると、Web ブラウザーに Web ページが表示されます。

To open a URI from a visualization, you first must edit the [!DNL Open URI.cfg] file for the URI dimension to identify the location and naming conventions that Data Workbench uses to open the URI. URIをネイティブ形式（HTMLなど）で表示するには、Data Workbenchが参照先の場所と、その項目を開くのに必要なアプリケーションにアクセスできる必要があります。 例えば、Webページを表示するには、Data Workbenchがインターネットにアクセスでき、Webブラウザーがインストールされている必要があります。

**Open URI.vw を編集するには**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. In the URI folder, right-click the check mark next to the [!DNL Open URI.vw]file and click **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、ファイルがファ **[!UICONTROL Open]** イルの場合は/を、ファイルの場合は//をクリックします。ファイルの場合は//（ファイルの場合は/）をクリックします。/（ファイルの場合は/）をクリ **[!UICONTROL in Insight]** ックし [!DNL .cfg]**[!UICONTROL Open]****[!UICONTROL in Notepad]**[!DNL .vw] てください。
1. Click **[!UICONTROL Command]**, then **[!UICONTROL Parameters]** to view the contents of the file.
1. 必要に応じて、[!DNL Site] パラメーターと Template パラメーターを変更します。

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 入力する情報 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Site </p> </td> 
   <td colname="col2"> <p>開く URI の場所。 </p> <p>例：mysite.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>テンプレート </p> </td> 
   <td colname="col2"> <p>Data WorkbenchがURIを検索して開くために使用する必要があるパラメーター。 </p> <p>例：<span class="filepath">http://%Site%%URI%</span> </p> <p>The default template shown in the example tells Data Workbench to open a web browser, look for the location defined in the <span class="wintitle"> Site</span> parameter, then locate the URI dimension element you are attempting to open. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. ファイルを保存します。
1. To make this change available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.

