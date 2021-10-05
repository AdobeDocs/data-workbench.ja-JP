---
description: 「開く」機能を使用すると、ドキュメントや URI などの項目をテキストエディターや Web ブラウザーなどの外部アプリケーションで開けます。
title: 「開く」機能の設定
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 47%

---

# 「開く」機能の設定{#configure-open-functionality}

「開く」機能を使用すると、ドキュメントや URI などの項目をテキストエディターや Web ブラウザーなどの外部アプリケーションで開けます。

「開く」機能は、現在 [!DNL Site] アプリケーションで、URI を開くためにのみ設定されています。この節では、[!DNL Site] 用の「URI を開く」機能の設定について説明します。別のアプリケーション用または他の項目を開くための「開く」機能の設定については、Adobe Consulting Services にお問い合わせください。

[!DNL Site] では、ページオーバーレイまたはテーブルから URI を右クリックすると、フォーマット対象のアプリケーションでその URI が表示されます。例えば、URI テーブルのビジュアライゼーションから URI をクリックすると、Web ブラウザーに Web ページが表示されます。

ビジュアライゼーションから URI を開くには、まず URI ディメンションの [!DNL Open URI.cfg] ファイルを編集し、Data Workbenchが URI を開く際に使用する場所と命名規則を特定する必要があります。 URI をネイティブ形式 (HTMLなど ) で表示するには、参照先の場所と、その項目を開くために必要なアプリケーションにData Workbenchがアクセスできる必要があります。 例えば、Web ページを表示するには、Data Workbenchがインターネットにアクセスし、Web ブラウザーをインストールする必要があります。

**Open URI.vw を編集するには**

1. [!DNL Profile Manager] で、**[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]** をクリックします。
1. URI フォルダーで、[!DNL Open URI.vw] ファイルの横のチェックマークを右クリックし、**[!UICONTROL Make Local]** をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** > **[!UICONTROL in Insight]** ファイルが [!DNL .cfg] ファイルの場合は **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** をクリックします。[!DNL .vw] ファイルの場合は  をクリックします。
1. **[!UICONTROL Command]**、**[!UICONTROL Parameters]** の順にクリックして、ファイルの内容を表示します。
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
   <td colname="col2"> <p>Data Workbenchが URI を検索して開くために使用する必要があるパラメーター。 </p> <p>例：<span class="filepath"> https://%Site%%URI%</span> </p> <p>この例のデフォルトのテンプレートは、Web ブラウザーを開き、<span class="wintitle"> Site</span> パラメーターで定義された場所を探し、開こうとしている URI ディメンション要素を探します。 </p> </td>
  </tr>
 </tbody>
</table>

1. ファイルを保存します。
1. この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、[!DNL User] 列の [!DNL .vw] ファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / **[!UICONTROL working profile name]** をクリックします。
