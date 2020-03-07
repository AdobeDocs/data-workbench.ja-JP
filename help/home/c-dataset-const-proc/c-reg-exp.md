---
description: 正規表現は、クエリーエンティティパネルを含め、data workbench のすべての検索フィールドで使用されます。
solution: Analytics
title: 正規表現
topic: Data workbench
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 正規表現{#regular-expressions}

正規表現は、クエリーエンティティパネルを含め、Data Workbench のあらゆる検索フィールドで使用されます。

* [正規表現について](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [正規表現の用語](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [リテラルマッチングについて](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [メタ文字の使用](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [パターン抽出](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## 正規表現について {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

正規表現は、パターンを検出したりテキストからサブ文字列を抽出したりするための、英数字や特殊文字（メタ文字）の組み合わせから成るテキストパターンです。正規表現は、コンピュータープログラミングにおいて広く使用されており、Perl をはじめとする各種言語において不可欠な存在となっています。

Data Workbench サーバーでは、いくつかの変換および条件の中で、複雑な文字列パターンを特定して抽出するために正規表現が使用されます。以降、正規表現について簡単に説明します。

この付録は、正規表現について詳細に解説したものではありません。詳しい解説については、オライリー・ジャパン発行の『*詳説 正規表現 第 2 版*』（Jeffrey E. F. Friedl 著）をお勧めします。

## 正規表現の用語 {#section-80b0d54f731e448391532ab3eb3c525c}

| 用語 | 定義 |
|---|---|
| リテラル | リテラルは、特定の文字の並びを探すために正規表現の中で使用する文字です。例えば、[!DNL shop/products.html] から product を検索する場合、product という文字列がリテラルです。つまり、文字列からの検索対象となる見たままの文字をいいます。 |
| メタ文字 | メタ文字は、正規表現のコンテキストの中で独特の解釈を持つ特殊文字です。例えば、ピリオド（.）は、任意の文字と一致するメタ文字です。 |
| エスケープシーケンス | エスケープシーケンスは単純に、特定のメタ文字をリテラルとして使用したい、という意図を正規表現エンジンに対して伝える手段です。Escape sequences always start with the backslash character (`\`). メタ文字の前にバックスラッシュ（バックスラッシュもメタ文字）が置かれている場合、正規表現エンジンは、そのエスケープされたメタ文字をリテラルとして解釈します。For example, if you want to match the metacharacter period (`.`), you need to use an escape sequence. However, to match one of the periods in the string 168.196.0.11, you could use the regular expression consisting of a backslash and a period (`\.`). |
| パターン | 正規表現の別称です。基本的に正規表現は、ターゲット文字列と突き合わせようとするパターンであるといえます。 |
| ターゲット文字列 | 目的のパターンの検索先となる文字列をいいます。 |

## リテラルマッチングについて {#section-ec4497e3160c47ba9b828d939761b3e0}

エスケープ文字を一切含まないリテラル文字列を受け取って、それと一致する部分がターゲット文字列内に存在するかどうかを調べるのがリテラルマッチングです。

次の例で、リテラルマッチングの動作を説明します。Web サイトトラフィックから収集したデータがあって、cs(referrer) フィールドに次の値が含まれているとします。

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

リファラーが、いずれかの広告をクリックした人であるかどうかを判別するには、リファラーに ad という文字列が含まれているかどうかを調べる必要があります。サイトへのトラフィックのルーティングに広告が寄与したかどうかは、単純にリテラル文字列である ad をターゲット文字列から探すことで判断することもできます。この場合、確かにターゲット文字列に一致しますが、一致箇所が 2 つあって曖昧なために、誤判定につながるおそれがあります。

次の URL には、ad という文字列が 2 箇所に出現しています。

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

そのため、特定の広告キャンペーンの結果として開始されたセッションを特定しようとする場合、リテラル ad を正規表現に使用しただけでは明らかに不十分です。この場合、リテラルを「ad=」に変更すると、曖昧さがなくなって、一致箇所が 1 つに絞り込まれます。しかしそれでも、広告キャンペーンが寄与したリファラーのみを確実に検出するうえでは十分とはいえません。次のようなリファラーがあるとします。

`http://www.xyz.com/hello.html?pad=something`

他人がサイトへのリンクを作成する際にどのような URL を使用するかをコントロールすることはできません。広告キャンペーンの結果として開始されたセッションを特定する手段として、リテラルマッチングは決して高度なメカニズムとはいえません。次の節では、より柔軟で強力なマッチングをメタ文字を使用して実現する方法について説明します。

## メタ文字の使用 {#section-e29a804336304ea1ba33d40d60139aa2}

メタ文字は、プログラムまたはデータフィールドの中で、他の文字に関する情報を与える特殊文字です。

| メタ文字 | 説明 |
|---|---|
| . （ドット） | 1 文字に一致します。例えば、`re:x.z` は「xyz」や「xxz」に一致します。 |
| *（星印） | Matches one or more characters, for example: `re:Z*` matches &quot;ZZZ&quot;. |
| ? （ワイルドカード） | 直前の式と最小のマッチングで 0 回または 1 回一致します。例えば、`xy?z` は「xy」と「xyz」に一致します。 |

広く使用されている正規表現は他にもあり、それらを駆使してもっと複雑な検索文字列を指定することもできます。

**リスト、範囲、論理和**

リテラルマッチングで検索できるのが単一の文字列であるのに対し、ブラケット、ダッシュ、パイプを使用すると、ターゲット文字列内から検索する一連の文字を定義できます。

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用するメタ文字 </th> 
   <th colname="col2" class="entry"> 正規表現プロセッサーが行う処理 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ブラケット（[ ]） </td> 
   <td colname="col2"> 特定の文字位置でブラケット内の任意の文字と一致します。例えば、[AB] はアルファベットの A または B と、[0123456789] は 0 ～ 9 の範囲の任意の 1 文字と一致します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ダッシュ（-） </td> 
   <td colname="col2"> <p>文字の範囲と一致します。つまり、[0123456789] は、よりシンプルに [0-9] と記述することもできます。 </p> <p> 文字の範囲や、その複数の範囲の組み合わせを 1 組のブラケットで指定することができます。例えば、[0-9A-C] は、0 ～ 9 および A ～ C の文字と一致します。 </p> <p> <p>注意：ダッシュ（-）をリテラルとして検索するには、ブラケット内の先頭か末尾に記述する必要があります。例えば、[-0-9] とした場合、- および 0 ～ 9 が検索されます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> パイプ（|） </td> 
   <td colname="col2"> 2 つの選択肢のうち一方を特定のターゲット文字列と突き合わせます。例えば、b|nat は、bat または nat と一致します。 </td> 
  </tr> 
 </tbody> 
</table>

次の例をご覧ください。

| パターン | 文字列 | 一致 |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| レッスン`[A-Z]` | Lesson a | 大文字の A ～ Z の範囲には小文字の a が含まれないので、一致は検出されません。 |

**否定**

否定は、指定された文字を除く任意の文字と一致させたいときに使用します。The negation metacharacter, the circumflex or caret (`^`), is used as the first character inside brackets to say that you would like the match to be anything but the remaining characters in the brackets. For example, to match any character but a semicolon (`;`), you would write

[`^;`]

この場合、セミコロンを除く任意の文字と一致します。

**位置**

ターゲット文字列の先頭または末尾と一致させるには、2 つのメタ文字のいずれかを使用します。

| 使用するメタ文字 | 正規表現プロセッサーが行う処理 |
|---|---|
| Circumflex or Caret (`^`) | 文字列の先頭と一致します。For example, ^`[Tt]`he would match the target string &quot;The Beginning&quot; but would not match &quot;This is the beginning.&quot; |
| ドル記号 (`$`) | 文字列の末尾と一致します。For example, `[Ee]`nd$ would match &quot;This is the end&quot; but would not match &quot;The end is a special time.&quot; |

>[!NOTE]
>
>正規表現の先頭に^を、末尾に$を含む場合、ターゲット文字列全体が正規表現と一致する必要があります。

**任意の文字との一致**

ピリオド（.）は、ターゲット文字列内の任意の文字と一致する特殊なメタ文字です。For example, the regular expression `^…$` matches any target string that is exactly three characters long. 正規表現「…」は、3 文字以上の任意のターゲット文字列と一致します。

**繰り返しのパターン**

特定のパターンが複数回出現している箇所は、繰り返しを表すメタ文字で検出することができます。

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用するメタ文字 </th> 
   <th colname="col2" class="entry"> 正規表現プロセッサーが行う処理 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 疑問符（?） </td> 
   <td colname="col2"> メタ文字（?）の直前の文字が 0 回または 1 回出現している箇所と一致します。例えば、rea?d というパターンは、red や read と一致します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アスタリスク（*） </td> 
   <td colname="col2"> メタ文字（*）の直前の文字の 0 回以上の繰り返しと一致します。例えば、[0-9]* というパターンは、0 ～ 9（任意の整数）の任意の数の文字と一致します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プラス記号（+） </td> 
   <td colname="col2"> 直前の文字または範囲の 1 回以上の繰り返しと一致します。例えば、thre+ というパターンは、three とは一致しますが、through とは一致しません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>直前の文字または範囲の、ちょうど n 回の繰り返しと一致します。米国の電話番号は、[0-9]{3}-[0-9]{3}-[0-9]{4} というパターンと一致します。 </p> <p> 最適なパターンではありませんが、ターゲット文字列が適切な形式になっているかどうかは、これで判別できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> 直前の文字の n 回以上、m 回以下の繰り返しと一致します。例えば、fo{1,2}d は、fod や food とは一致しますが、foood とは一致しません。 </td> 
  </tr> 
 </tbody> 
</table>

## パターン抽出 {#section-4389779653b64f6cb7c47615b25c1a79}

パターンマッチングは、正規表現が備えている機能の一面に過ぎません。正規表現には、ターゲット文字列から重要な要素を抽出するメカニズムも備わっています。抽出には、開始丸括弧と終了丸括弧が使用されます。抽出結果は通常、別の処理への入力として渡し、*%position%* を使用してアクセスします（position は 1 組の丸括弧の個数を表す整数）。

パターン抽出の例を次に示します。

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パターン </th> 
   <th colname="col2" class="entry"> 文字列 </th> 
   <th colname="col3" class="entry"> 一致 </th> 
   <th colname="col4" class="entry"> 抽出 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Win(9[58]) </td> 
   <td colname="col2"> OS=Win95 </td> 
   <td colname="col3"> Win95 </td> 
   <td colname="col4"> %1% = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3.03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lesson([A-Z]) </td> 
   <td colname="col2"> Lesson a </td> 
   <td colname="col3"> 大文字の A ～ Z の範囲には小文字の a が含まれないので、一致は検出されません。 </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

