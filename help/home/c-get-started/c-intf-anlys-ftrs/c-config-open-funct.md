---
description: 「開く」機能を使用すると、ドキュメントや URI などの項目をテキストエディターや Web ブラウザーなどの外部アプリケーションで開けます。
title: 「開く」機能の設定
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 47%

---

# 「開く」機能の設定{#configure-open-functionality}

{{eol}}

「開く」機能を使用すると、ドキュメントや URI などの項目をテキストエディターや Web ブラウザーなどの外部アプリケーションで開けます。

「開く」機能は、現在 [!DNL Site] アプリケーションで、URI を開くためにのみ設定されています。この節では、[!DNL Site] 用の「URI を開く」機能の設定について説明します。別のアプリケーション用または他の項目を開くための「開く」機能の設定については、Adobe Consulting Services にお問い合わせください。

[!DNL Site] では、ページオーバーレイまたはテーブルから URI を右クリックすると、フォーマット対象のアプリケーションでその URI が表示されます。例えば、URI テーブルのビジュアライゼーションから URI をクリックすると、Web ブラウザーに Web ページが表示されます。

ビジュアライゼーションから URI を開くには、まず [!DNL Open URI.cfg] ファイルを使用して、Data Workbenchが URI を開く際に使用する場所と命名規則を識別します。 URI をネイティブ形式 (HTMLなど ) で表示するには、Data Workbenchが参照先の場所と、その項目を開くのに必要なアプリケーションにアクセスできる必要があります。 例えば、Web ページを表示するには、Data Workbenchがインターネットにアクセスでき、Web ブラウザーがインストールされている必要があります。

**Open URI.vw を編集するには**

1. 内 [!DNL Profile Manager]をクリックし、 **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. URI フォルダーで、 [!DNL Open URI.vw]ファイルを開き、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL in Insight]** ファイルが [!DNL .cfg] ファイルまたは **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** もしそれが [!DNL .vw] ファイル。
1. クリック **[!UICONTROL Command]**&#x200B;を、 **[!UICONTROL Parameters]** をクリックして、ファイルのコンテンツを表示します。
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
   <td colname="col2"> <p>Data Workbenchが URI を探して開くために使用する必要があるパラメーター。 </p> <p>例： <span class="filepath"> https://%Site%%URI%</span> </p> <p>この例のデフォルトのテンプレートは、Data Workbenchに対し、Web ブラウザーを開いて、 <span class="wintitle"> サイト</span> パラメーターを使用して、開こうとしている URI ディメンション要素を見つけます。 </p> </td>
  </tr>
 </tbody>
</table>

1. ファイルを保存します。
1. この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、 [!DNL .vw] ファイルを [!DNL User] 列とクリック **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
