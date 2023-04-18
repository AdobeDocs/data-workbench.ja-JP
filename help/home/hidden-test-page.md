---
title: 非表示のテストページ
description: このページは、検索や目次には表示されません
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
source-git-commit: c08189cf57f08fc5be4bc24ec06d9b9a865a53c8
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 2%

---

# 非表示のテストページ

## バッジ

バッジは、コンテンツインジケーターとして使用される色付きのラベルです。 例えば、バッジを追加して記事を「 _ベータ版_ またはセクションを _プレミアム_. バッジの色を変更し、URL とツールチップを関連付けることができます。

[!BADGE バッジの例]

バッジには 2 種類あり、それぞれ異なる構文を持ちます。

* **メタデータ**  — ページの上部付近にバッジを表示します
* **インライン**  — 構文が存在するバッジを表示します

### メタデータバッジ

メタデータにバッジ構文を追加すると、記事のページタイトル (H1) の上にバッジが配置されます。

バッジに名前を付けるには、例えば、 _badge1_ または _badge2_. または、名前がで始まる限り、よりクリエイティブにすることもできます。 _バッジ_) をクリックします。

メタデータの例：

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** 次の例では、Premium バッジに URL とツールヒントが表示されます。

* **badgeExam:** 次の使用例は、ダークバッジと試験 ID 番号を表示します。

#### インラインバッジ

バッジ情報を独自の行に指定するか、見出し、表、または他のページ要素に指定します。

ベータラベル、青色、URL およびツールチップを含むインラインバッジの構文を次に示します。

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### 使用可能なバッジの色

バッジは、「Adobeスペクトル」で定義された色を使用します。

| タイプ | バッジ |
|---|---|
| 情報（デフォルト） | [!BADGE ベータ]{type=Informative url="https://www.example.com"} |
| 肯定的 | [!BADGE 新機能]{type=Positive url="https://www.example.com" tooltip="example.com に移動"} |
| 否定的 | [!BADGE 廃止]{type=negative tooltip="この機能は現在提供終了です"} |
| 中立的 | [!BADGE 多分]{type=Neutral tooltip="乗り手が馬から落ちた…"} |
| 注意 | [!BADGE 注意]{type=Caution tooltip="黄色のステータス"} |

構文の例

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### バッジの要件

* メタデータで使用できるバッジは 2 つだけです。 このルールは設定可能なので、例外が必要な場合はお知らせください。
* バッジラベルのみが必要です。 この `type`, `url`、および `tooltip` パラメーターはオプションです。 この `type` パラメータは色を決定します。 この `url` パラメーターを使用すると、ユーザーはバッジをクリックして記事またはページを開くことができます。 この `tooltip` パラメータは、マウスオーバー時にツールチップテキストを表示します。
* へのバッジの追加 `TOC.md` ファイルには、ガイド内のすべての記事にバッジが表示されます。 バッジから記事にジャンプするための URL を指定する場合は、ルートリンク ( 例： `/help/guide/article.md`) は相対リンクではありません ( 例： `article.md`) を使用して、異なるフォルダー内の記事を処理できます。
* バッジの追加先 `metadata-new.md` リポジトリ内の各記事のバッジを表示します。
* メタデータバッジの場合は、すべての値が引用符で囲まれていることを確認します。 インラインバッジの場合は、 `url` および `tooltip` は引用符で囲まれます。
* 有効なタイプの値は次のとおりです。 *情報* （デフォルト、青）、 *肯定的* （緑）、 *ネガティブ* （赤）、 *中立* （ダークグレー） *注意* （黄色）。
* バッジラベルはローカライズされています。
* 複数のメタデータバッジを指定した場合、バッジは、バッジ名に基づいてアルファベット順に表示されます ( 例： `badge1:` または `badgeWeb`.
* URL を新しいタブで開く場合は、次の構文を使用します。

   ```
   [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
   ```

   レンダリング:

   [!BADGE 新しいタブで開く]{type=Negative url="https://www.adobe.com newtab=true" tooltip="新しいタブで adobe.com を開く"}

## テキストのハイライト

Workfrontチームは、黄色のハイライトを使用して、今後の機能のプレビューを示すように求めました。 次に、その仕組みを示します。

例 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

レンダリング:

この段落全体をハイライト表示しないでください。 <span class="preview"> この単語は **太字** 強調表示された文の中に</span> これが最後の文です

例 2:

```
Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

>[!NOTE]
>
>This is a note.
>
>I have a request to highlight the note's background.

![image](/help/quicksilver/administration-and-setup/add-users/create-and-manage-users/assets/add-admin-1.png)

Last highlighted item.

</div>

Not highlighted
```

レンダリング:

この段落の後にハイライト表示を開始する必要があります。

<div class="preview">

DIV の開始。

>[!NOTE]
>
>これはメモです。
>
>メモの背景を強調するリクエストがあります。

![image](/help/home/assets/analytics-icon-24.png)

最後にハイライトされた項目。

</div>

強調表示されていません

## コードブロックの構文の強調表示

Experience Leagueは、コードブロックの構文のハイライト表示をサポートしています。 必ず `java` バッククォートの開始後に、構文が正しくハイライト表示されていることを確認します。 有効な言語の一覧については、 [https://prismjs.com](https://prismjs.com/#supported-languages). 言語が不足している場合は、jira チケットをログに記録してください。

### コードブロック内の行番号

追加 `{line-numbers="true"}` 行番号を有効にする言語の後に配置します。

行番号 (&grave;&grave;&grave;) を使用する例`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**行_で番号付けを開始**

追加 `start-number="n"` 行番号の構文の後に、1 以外の数値で番号付けを開始します。

新しい開始ライン (&grave;&grave;&grave;) を使用する例`html {line-numbers="true" start-line="7"}`):

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### コードブロック内の行のハイライト

追加 `highlight="n"` 行番号構文の後で、コードブロック内の行をハイライト表示します。 指定 `11-13, 16` は、11～13 と 16 の行をハイライトします。

例 — 線のハイライト (&grave;&grave;&grave;)`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```
