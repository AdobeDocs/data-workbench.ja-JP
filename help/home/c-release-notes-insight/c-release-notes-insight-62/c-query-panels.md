---
description: Data Workbench のファインダーパネルを使用して、指標、ディメンションおよびフィルターを選択できます。これらのパネルは、検索をサポートしており、並べ替えオプションとドラッグ＆ドロップ機能を備えています。
title: ファインダー
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 96%

---


# ファインダー{#finders}

Data Workbench のファインダーパネルを使用して、指標、ディメンションおよびフィルターを選択できます。これらのパネルは、検索をサポートしており、並べ替えオプションとドラッグ＆ドロップ機能を備えています。

ファインダーパネルは、左側のサイドバーまたはワークスペース内で開くことができます。

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディメンションファインダー </th> 
   <th colname="col2" class="entry"> 指標ファインダー </th> 
   <th colname="col3" class="entry"> フィルターファインダー </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>クエリーモデル内のすべてのディメンションのリスト。 </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>クエリーモデル内のすべての指標のリスト。 </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>組織で作成されたすべてのフィルターのリスト。 </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**ファインダーを開くには：**

* ワークスペース内で右クリックし、**[!UICONTROL Tools]** > **[!UICONTROL Finder]**&#x200B;を選択します。

   「指標」、「ディメンション」および「フィルター」のタブを含むファインダーペインがワークスペース内に開きます。

* 左側のサイドバーを右クリックし、**[!UICONTROL Add]** > **[!UICONTROL Finder]**&#x200B;を選択します。

   ファインダーペインが左側のパネルに開きます。

**ファインダー**&#x200B;には、次の機能が含まれています。

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファインダーの機能 </th> 
   <th colname="col2" class="entry"> 詳細 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>ドラッグ＆ドロップ</b> </td> 
   <td colname="col2"> <p> ディメンションまたは指標をパネルからワークスペースのビジュアライゼーションにドラッグ＆ドロップして、ディメンションを変更したり、新しい指標を追加したりできます。 </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44"><span class="uicontrol">Ctrl</span> + <span class="uicontrol">Alt</span> キーを押しながらファインダーパネルからディメンションまたは指標を選択します。 </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">ペインから新しいディメンションをドラッグし、ビジュアライゼーションにドロップして、ディメンションを変更または追加します。 </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">指標を追加するには、ペインから新しい指標をドラッグし、選択したビジュアライゼーションの指標ヘッダーにドロップします。 </li> 
    </ol> <p>この方法は、テーブル、訪問者クラスター、相関行列、散布グラフおよび 2D 棒グラフ（軸による）など、すべての関連ビジュアライゼーションで使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>検索</b> </td> 
   <td colname="col2">ファインダーパネルの「<span class="uicontrol">検索</span>」ボックスでは、ディメンション、指標およびフィルターの名前をフィルターできます。 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>パターン一致（単純なグローバル検索）。「検索」フィールドに目的のディメンション、指標またはフィルターエンティティの名前を入力すると、一致する文字列を含む名前だけがフィルターされ、ファインダーペインに表示されます。 </p> <p>例えば、次のように入力します。 </p> <code><b>Search:</b>click</code> <p>ディメンションファインダーでは、次のような結果を得ることができます。 </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>標準のパターン一致では、「.」（ドット）、「?」、「*」（スター）などのワイルドカード文字を使用することができます。 </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>正規表現. 追加された検索機能では、より複雑な正規表現もサポートされています。検索語句の前にプレフィックス「re:」を（スペースなしで）追加すると、正規表現として解釈されます。 </p> <p>例えば、次のように入力します。 </p> <code><b>Search:</b>re.*ip</code> <p>ディメンションファインダーでは、次のような結果を得ることができます。 </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>検索について詳しくは、<a href="https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external">正規表現</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>ディメンションタイプ</b> </td> 
   <td colname="col2">「ディメンション」タブでは、タブの見出しを右クリックして、ディメンションのタイプで並べ替えることができます。 <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">属性：訪問者、製品、地域、時間、ビデオなどの属性の特徴に基づいて構築されたディメンション。 </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">クラスター：クラスタービルダー内で構築されたディメンション。 </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">スコア：傾向スコアリング内で構築されたディメンション。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>ラベル</b> </td> 
   <td colname="col2">各タブでは、右クリックし、「<span class="uicontrol">ラベル</span>」を選択して、ファインダーペインの名前を変更できます。 <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>デフォルトのディメンション、指標およびフィルターのラベルを組織の規則に従ったタブ名に変更することができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>項目の追加</b> </td> 
   <td colname="col2">各タブでは、右クリックし、「<span class="uicontrol">項目の追加</span>」を選択して、テーブルを開き、ディメンション、指標およびフィルターを手動で追加できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>ファインダーバー</b> </td> 
   <td colname="col2">左側のサイドバーにある<span class="uicontrol">ファインダー</span>バーを右クリックすると、追加機能のメニューが開きます。 <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>閉じる</b> </td> 
   <td colname="col2"><span class="uicontrol">ファインダー</span>バーを右クリックし、「<span class="uicontrol">閉じる</span>」を選択すると、ファインダーペインが閉じます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>保存</b> </td> 
   <td colname="col2">リストをローカルに保存するには、ヘッダーバーを右クリックし、「<span class="uicontrol">保存</span>」オプションを選択します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>エクスポート</b> </td> 
   <td colname="col2">ファインダーパネルから選択したディメンション、指標またはフィルターのリストをエクスポートするには、ファインダーバーを右クリックし、メニューから「<span class="uicontrol">エクスポート</span>」を選択します。 <p> 名前を追加し、Microsoft Excel にエクスポートします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Copy</b> </td> 
   <td colname="col2"> ディメンション、指標またはフィルターのリストをコピーします。ファイルとしてコピーすることや、暗い背景、明るい背景またはモノクロのグラフィックとしてコピーすることができます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>最小化</b> </td> 
   <td colname="col2"> ファインダーペインを最小化します。ファインダーバーのみが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>枠なし</b> </td> 
   <td colname="col2"> ワークスペース内でファインダーのペインを境界線なしで表示します（ただし、左側のサイドバーでは境界線なしで表示されません）。 </td> 
  </tr> 
 </tbody> 
</table>

