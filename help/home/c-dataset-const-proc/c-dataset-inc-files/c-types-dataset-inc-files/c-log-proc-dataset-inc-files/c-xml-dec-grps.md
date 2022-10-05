---
description: XML ファイルからデータを抽出するデコーダーを定義するログソースとしての XML ファイルの処理。
title: XML デコーダーグループ
uuid: 8fc9ab80-9a71-4fe2-a646-e830ffeb67b9
exl-id: 0b0534b7-8596-4528-a643-8a9b41dcaa33
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 74%

---

# XML デコーダーグループ{#xml-decoder-groups}

{{eol}}

XML ファイルからデータを抽出するデコーダーを定義するログソースとしての XML ファイルの処理。

>[!NOTE]
>
>XML ログソースに対して XML デコーダーグループを定義するには、XML ファイルの構造と内容、抽出するデータ、およびそのデータが格納されるフィールドに関する知識が必要です。 この節では、デコーダー用に指定できるパラメーターについて簡単に説明します。デコーダーの使用方法は、目的のソースデータが格納されている XML ファイルによって異なります。

XML ログソースの形式の要件について詳しくは、 [ログソース](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea). XML デコーダーの定義に関して不明な点がありましたらアドビにお問い合わせください。

XML デコーダーの最上位の要素はデコーダーグループ（XMLDecoderGroup）です。特定の形式の XML ファイルからデータを抽出するための一連のデコーダーテーブルが、デコーダーグループにまとめられています。異なる複数の形式の XML ファイルがある場合は、その形式ごとにデコーダーグループを定義する必要があります。各デコーダーグループは、少なくとも 1 つのデコーダーテーブルから成ります。

次の表に、XML デコーダーグループを定義するために指定する必要がある Tables パラメーターとすべてのサブパラメーターを示します。

<table id="table_06C40C5149E94548A1B0C2ED4397624B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> テーブル </td> 
   <td colname="col2"> <p>デコーダーグループ内の各テーブルは、XML ファイルから抽出する 1 階層分のデータを表します。例えば、訪問者に関するデータを抽出したい場合、それぞれの訪問者について抽出する情報から成るデコーダーテーブルを作成します。デコーダーテーブル内にデコーダーテーブルを作成することもできます（「Children」を参照）。 </p> <p> <b>デコーダーグループにテーブルを追加するには</b> 
     <ul id="ul_C73CAD77440B4465B9FCE08BF4FA0749"> 
      <li id="li_C4B8CC5A85D942898F1EB76778105818"> <span class="uicontrol">Tables</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">XMLDecoderTable</span> をクリックします。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fields </td> 
   <td colname="col2"> <p>データが格納される拡張フィールド（x-trackingid、x-email など）。フィールドに格納されるデータは、サブフィールドである Path と Operation（両方またはそのどちらか一方）によって決まります。 </p> <p> Path は、構造化 XML ファイル内のフィールドの階層です。フィールドのパスは、それが定義されているテーブルのパスに対して相対的に指定します（例：<span class="filepath">tag.tag.tag</span>、<span class="filepath">tag.tag.tag.@attribute</span>）。パスの大文字と小文字が区別されることに注意してください。 </p> <p> 指定したパスのそれぞれの行に Operation が適用されて、出力結果が生成されます。次の演算を適用できます。 
     <ul id="ul_B264A411D7E3446288E7E69D62150B8B"> 
      <li id="li_5936E81C0EEF46AFB780E451A04A88E4"><b>LAST：</b>XML ファイル内で最後に出現するパスの値がフィールドに格納されます。 </li> 
      <li id="li_7BC4F24F2CA84C2EB64B06FE09B4CAF6"><b>RANDOM：</b>フィールドにランダム値を割り当てます。x-trackingid フィールドなど、一意の ID を生成する必要がある場合に利用できます。 </li> 
      <li id="li_C1D34EA11BFB4859A25A275A9B63FB56"><b>INHERIT：</b>定義されているフィールドの値は、親テーブルの対応するフィールドから継承されます。 </li> 
      <li id="li_F62FB8CD962E4E1495D9A2D5B7A78E2A"><b>"<i>constant </i>"：</b>定数は引用符で囲む必要があります。定数演算を使用すると、特定のパスの存在をチェックできます。パスが存在する場合、対象のフィールドに定数の値が割り当てられます。 </li> 
     </ul> </p> <p> <b>デコーダーテーブルにフィールドを追加するには</b> </p> <p> 
     <ul id="ul_91D104D927424DEA9E788E43B2F6FEA9"> 
      <li id="li_5448B01EE82349569BBFC99C9604D7B8"> <span class="uicontrol">Fields</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">XMLDecoderField</span> をクリックします。必要に応じて Field、Operation、Path を定義します。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> パス </td> 
   <td colname="col2"> <p>デコーダーテーブルに格納される情報の、構造化 XML ファイル内における階層。子の XML デコーダーテーブルの場合、親テーブルのパスに対して相対的に指定します。パスの大文字と小文字が区別されることに注意してください。 </p> <p> 例えば、XML ファイルが次のような構造になっているとします。 </p> 

    &amp;lt;visitor&amp;gt;
    
    &amp;nbsp;
    
    ...
    
    &amp;nbsp;
    
    &amp;lt;/visitor&amp;gt;
    
    &amp;lt;/logdata&amp;gt;&amp;nbsp; &lt;/code> &lt;p> 次に、パスは logdata.visitor&lt;span class=&quot;filepath&quot;>になりま&lt;/span>す。 &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col1"> テーブル </td> 
   <td colname="col2"> <p>このパラメーターの値は常に「Log Entry」にする必要があります。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Children </td> 
   <td colname="col2"> <p>（オプション）。埋め込みのデコーダーテーブル（複数可）。それぞれの子に、前述した Fields、Path、Table の各パラメーターが存在します。 </p> <p> <b>デコーダーテーブルに子を追加するには</b> </p> <p> 
     <ul id="ul_902AC6CA5D66457D84CBA3194FF49BBE"> 
      <li id="li_07B4D60E7E2E4630B4878691E575936A"> <span class="uicontrol">Children</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">XMLDecoderTable</span> をクリックします。必要に応じて Field、Operation、Path を定義します。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

データセットのログソースとして XML ファイルを使用するには、データセットへと加工される情報を抽出する XML デコーダーグループと XML デコーダーテーブルを定義する必要があります。以降、Web データセットのサンプル XML ログソースを例に、デコーダーグループとデコーダーテーブルを定義する方法を紹介します。

次の XML ファイルには、Experience CloudID、電子メールアドレス、物理アドレス、訪問者のページビューに関する情報など、Web サイトの訪問者に関する情報が含まれています。

![](assets/xmlFile_LogSource.png)

この例では、XML ファイルが 1 つなので、必要なデコーダーグループは 1 つだけです。このデコーダーグループの名前は「Sample XML Format」とします。ファイルの形式が同じであれば、他の XML ファイルにも、このデコーダーグループを適用できます。このデコーダーグループ内に XML デコーダーテーブルを作成するにはまず、抽出する情報とそのデータの格納先となるフィールドを決める必要があります。

この例では、訪問者とそのページビューに関する情報を抽出することにします。そこで、訪問者に関する情報を格納する最上位（親）の XML デコーダーテーブルと、その訪問者のページビューに関する情報を格納する埋め込み（子）の XML デコーダーテーブルを作成します。

**親（訪問者）テーブルの情報は次のとおりです。**

* XML ファイルの各データ行のデータタイプ識別子。ページビューに関連したデータ行ではなく、訪問者に関連したデータ行であることがすぐにわかるよう、ここでは「VISITOR」を識別子として使用します。この値は x-rowtype フィールドに格納することができます。
* 訪問者の ID。この ID は x-trackingid フィールドに格納します。
* 訪問者の電子メールアドレス（contact.email）。x-email フィールドに格納します。
* 訪問者の登録ステータス。訪問者が登録ユーザーである場合、x-is-registered フィールドに値「1」を格納します。
* パスの値は、 [!DNL logdata.visitor]の場合、Table の値は [!DNL Log Entry]. これらのパラメーターについて詳しくは、上の表（「XMLDecoderGroup」）を参照してください。

**子（ページビュー）テーブルの情報は次のとおりです。**

* XML ファイルの各データ行のデータタイプ識別子。訪問者のみに関連したデータ行ではなく、訪問者のページビューに関連したデータ行であることがすぐにわかるよう、ここでは「PAGEVIEW」を識別子として使用します。この値は x-rowtype フィールドに格納します。
* 訪問者の ID。この値は親テーブルから継承し、x-trackingid フィールドに格納します。
* 各ページビューのタイムスタンプ。x-event-time フィールドに格納します。
* 各ページビューの URI。cs-uri-stem フィールドに格納します。
* Path の値は pageview で、Table の値は「Log Entry」。これらのパラメーターについて詳しくは、上の表（「XMLDecoderGroup」）を参照してください。

次の画面キャプチャは、 [!DNL Log Processing Dataset Include] ファイルの親と子の XML デコーダーテーブルの構造に基づいて、サンプル XML ファイル用に生成された XML デコーダーグループを作成します。

![](assets/cft_LogProc_xmldecodergroup_top.png)

![](assets/cfg_LogProcessingInclude_XMLDecoderGroup_bottom.png)

サンプル XML ファイルに対してこのデコーダーを適用した場合の出力結果は、次のようなテーブルになります。

| x-rowtype | cs--uri-stem | x-email | x-is-registered | x-event-time | x-tracking-id |
|---|---|---|---|---|---|
| VISITOR |  | foo@bar.com | 1 |  | 1 |
| PAGEVIEW | /index.html |  |  | 2006-01-01 08:00:00 | 1 |
| PAGEVIEW | / |  |  | 2006-01-01 08:00:30 | 1 |

同様のテーブルは、Data Workbench でフィールドビューアのインターフェイスを使用して作成できます。フィールドビューアのインターフェイスについて詳しくは、 [データセット設定ツール](../../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

## XML 要素で#valueを使用して属性値を読み取る {#section-88758428afb94f0baa5a986604d53bc1}

これで、 **[!DNL #value]** タグを XML パスに追加し、XML 要素の値を取得します。

例えば、以前に **`<Hit><Page name="Home Page" index="20">home.html</Page></Hit>`** を読み取れなくなりました `<Page>` タグを使用します。 の値を読み取るには `<Page>` タグとその属性は、 [!DNL Hit.Page.@name] および [!DNL Hit.Page.@index] それぞれ また、タグの値を **`Hit.Page.#value`** 式。

例えば、タグの値を読み取ることができます `<varValue>` デコーダーに次のフィールドを追加する。

```
7 = XMLDecoderField: 
Field = string: x-varvalue-name-added 
Operation = string: LAST 
Path = string:  
<b>#value</b> 
Path = string: varValue 
Table = string: Log Entry
```

同様に、タグの値を読み取ることができます `<Rep>` デコーダーに次のフィールドを追加する。

```
7 = XMLDecoderField: 
Field = string: x-rep-name-added 
Operation = string: LAST 
Path = string: Rep.# 
<b>value</b> 
Path = string: Reps 
Table = string: Log Entry
```

これに対し、属性のない要素タグの値を読み取るには、 `<text>` タグを `<line>` タグとその値は、 [!DNL text]」をクリックします。 [!DNL line.text]（デコーダーの構築方法に応じて）。

```
2 = XMLDecoderField: 
Field = string: x-chat-text 
Operation = string: LAST 
Path = string:  
<b>text</b> 
Path = string:  
<b>line</b> 
Table = string: Log Entry
```
