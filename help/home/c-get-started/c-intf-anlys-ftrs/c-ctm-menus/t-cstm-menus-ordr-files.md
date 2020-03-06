---
description: メニューに関連付けられた order.txt ファイルを編集して、メニューの外観をカスタマイズできます。
solution: Analytics
title: order.txtファイルを使用したメニューのカスタマイズ
topic: Data workbench
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# order.txtファイルを使用したメニューのカスタマイズ{#customize-a-menu-using-order-txt-files}

メニューに関連付けられた order.txt ファイルを編集して、メニューの外観をカスタマイズできます。

この節の手順は、あらゆる種類のメニューで利用できます。

**order.txt ファイルを編集してメニューをカスタマイズするには**

1. In the [!DNL Profile Manager], in the *profile name* column, right-click the check mark for the [!DNL order.txt] file and click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the [!DNL order.txt] file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL order.txt] file displays.

   ![ステップ情報](assets/cfg_ordertxt.png)

1. (Optional) Add or change the [Inclusive] or [Exclusive] setting at the top of the file if desired. This setting controls whether items not listed in the [!DNL order.txt] file but present in the [!DNL Profile Manager] is listed on the menu. 次のオプションがあります。

   * **[包括的]:**これがデフォルト設定です。 この設定では、[!DNL order.txt]ファイルに指定されていないメニュー項目が、メニューの下部にアルファベット順に表示されます。For example, if the[!DNL Profile Manager]contained a Profile item in addition the those listed in the[!DNL order.txt]above, Profile would display below Data.

   * **[排他]:**この設定により、ファイルで指定されていないメニュー項目がメ[!DNL order.txt]ニューから除外されます。 For example, if the[!DNL Profile Manager]contained a Profile item in addition the those listed in the[!DNL order.txt]above, Profile would not be displayed anywhere on the menu.

   * **空白：** ファイルの [先頭に] 「両端を含む」と「 [排他的」のどちらも表示されない場合、Data Workbenchは設定が「両端を含む」であるかのようにメニュー項目を表示] します []。

1. 次の手順を実行します。

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 実行する作業... </th> 
    <th colname="col2" class="entry"> 手順... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>メニュー項目の並べ替え </p> </td> 
    <td colname="col2"> <p>Data Workbenchに表示する順序で項目名を入力します。 </p> <p>例えば、各メニュー項目名が対応するファイルまたはフォルダーの名前と一致すれば、次のように指定すると「<b>テーブル</b>」が最初に、「<b>ビジュアライゼーション</b>」、「<b>凡例</b>」、「<b>注意</b>」が最後に表示されます。 </p> <p><b>テーブル</b> </p> <p><b>ビジュアライゼーション </b> </p> <p><b>凡例 </b> </p> <p><b>注意</b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>メニュー項目の名前の変更 </p> </td> 
    <td colname="col2"> <p>対応するファイルまたはフォルダーの名前を<span class="wintitle">プロファイルマネージャー</span>で変更して、<span class="filepath">order.txt</span> ファイルで項目名を変更します。 </p> <p>例えば、「注意」を「新規注意」に変更するには、<span class="wintitle">プロファイルマネージャー</span>で「注意」フォルダーの名前を「新規注意」に変更して、<span class="filepath">order.txt</span> ファイルで「注意」項目の名前を「新規注意」に変更します。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>メニュー項目の非表示 </p> </td> 
    <td colname="col2"> <p>メニュー項目を削除せずに非表示にするには、名前の先頭にマイナス記号（-）を入力します。 </p> <p>例えば、次のように指定すると、メニューに「<span class="wintitle">注意</span>」が表示されなくなります。 </p> <p>凡例 </p> <p>-注意 </p> <p>To again show the hidden menu item, simply remove the minus sign (-) or use the Unhide All parameter in the <span class="filepath"> Insight.cfg</span> file, see <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight Configuration Parameters</a>. </p> <p>次の方法でメニュー項目を非表示にすることもできます。 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p><span class="filepath">.filter</span>、<span class="filepath">.metric</span> または <span class="filepath">.dim</span> ファイルの Show パラメーターを使用すると、フィルター、派生指標と派生ディメンションおよび拡張ディメンションを各メニューから非表示にできます。このオプションを使用すると、項目はメニューに表示されませんが、プロファイルには存在するので、引き続き使用できます。 </p> <p>このパラメーターを使用して、フィルター、派生指標および派生ディメンションを非表示にするには、<span class="filepath">.metric</span>、<span class="filepath">.dim</span> または <span class="filepath">.filter</span> ファイルの末尾に次の行を追加します。 </p> <p><span class="filepath"> show = bool: false</span> </p> <p>このパラメーターを使用して拡張ディメンションを非表示にするには、『<i>データセット設定ガイド</i>』の第 10 章で手順を参照してください。 </p> <p><span class="filepath">Insight.cfg</span> ファイルで Unhide All パラメーターを設定して、この方法で非表示にした項目を一時的に表示できます。このパラメーターについて詳しくは、 <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight設定パラメーターを参照してください</a>。 </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA"><span class="filepath">Transformation.cfg</span> ファイルまたはいずれかのデータセットインクルードファイルの Hidden パラメーターを使用すると、ディメンションメニューから拡張ディメンションを非表示にできます。このオプションを使用すると、項目はメニューに表示されませんが、プロファイルには存在するので、引き続き使用できます。 <p> <p>注意：この方法を使用して拡張ディメンションを非表示にする場合は、非表示にするディメンションのデータセットを再変換する必要があります。 </p> </p> <p><span class="filepath">Insight.cfg</span> ファイルで Unhide All パラメーターを設定して、この方法で非表示にした項目を一時的に表示できます。このパラメーターについて詳しくは、 <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight設定パラメーターを参照してください</a>。 </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>0 バイトのファイルを使用すると、任意のメニューの任意の種類の項目を非表示にできます。このオプションを使用すると、空の（0 バイトの）ファイルによって、データを含む同じ名前のファイルが非表示になります。Data Workbenchは、0バイトのファイルを存在しないかのように扱います。 詳しくは、空の（0バイト）フ <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> ァイルを使用してファイルを非表示にするを参照してください</a>。 </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>メニュー項目の削除 </p> </td> 
    <td colname="col2"> <p>このファイルが [Exclusive] オプションを使用するように設定されている場合は、このファイルからメニュー項目を削除します。項目自体は引き続きプロファイルに存在しますが、メニューには表示されなくなります。 </p> <p>このファイルが [Inclusive] オプションを使用するように設定されている場合にメニューから項目を削除するには、このファイルからメニュー項目名を削除したうえで、対応するファイルを削除するか、または 0 バイトにする必要があります。 </p> <p>ファイルの削除の詳細については、「<a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b">作業プロファイルからのファイルの削除</a>」を参照してください。0バイトファイルについて詳しくは、空の（0バイト）フ <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> ァイルを使用してファイルを非表示にするを参照してください</a>。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>グループヘッダーの追加 </p> </td> 
    <td colname="col2"> <p>表示する見出しのテキストの前と後に、3 つハイフンを入力します。 </p> <p>例えば、次のように指定すると、一連の関連するメニュー項目に「管理」グループヘッダーを追加できます。 </p> <p>---管理--- </p> <p>プロファイル </p> <p>データセット </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>メニューのセクションを分離するラインの追加 </p> </td> 
    <td colname="col2"> <p>ラインを表示する場所に 3 つのハイフンを入力します。 </p> <p>例えば、次のように指定すると、「注意」と「カスタム」を分離するラインが表示されます。 </p> <p>注意 </p> <p>--- </p> <p>カスタム </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. ファイルを保存して閉じます。
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for the [!DNL order.txt] file in the [!DNL User] column and click **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
