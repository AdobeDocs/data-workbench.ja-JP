---
description: テストを導入した後、テストが適切に動作していることを検証する必要があります。
solution: Insight,Analytics
title: 実験の検証
topic: Data workbench
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 実験の検証{#validating-the-experiment}

テストを導入した後、テストが適切に動作していることを検証する必要があります。

「ExpCookieURLパラメ [ータの変更（オプション）](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)[!DNL Sensor] 」で説明したように、設定ファイルのExpCookieURLパラメータで指定されたページを使用して、自分を特定のテストグループに配置できます。

デフォルトの仮想ペー [!DNL /setcookie.htm]ジはですが、ExpCookieURLパラメータで設定した値を使用する必要があります。

## テストページのリクエスト {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Webサイトの特定のテストグループをテストするには、ブラウザーがcookieを受け入れるように設定されている必要があります。また、このWebサイトのcookieを持っていない必要があります。

新しいグループをテストするたびに、WebサイトのCookieをクリアします。

特定のテスト内の特定のグループに自分を配置するには、次の形式のクエリ文字列を使用してテストページをリクエストします。

[!DNL http://] *&lt;[!DNL sitename/?Experiment Name=Group Name]>*

次に例を示します。

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

仮想URLリクエストがサーバーに送信されると、は指定されたテスト内の指定されたグループのメンバーとしてユーザーを識別し、 [!DNL Sensor] Webサイトのルートにリダイレクトします。 これで、Webサイト上の適切な場所に移動して、そのテストやグループに対して正しいコンテンツが表示されるかどうかを検証できます。

ブラウザに以下を入力すると、ブラウザにWebサイトのホームページが表示され、New_Homepageテスト内のindex2グループに配置されます。

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

index2グループの訪問者がホームページをリクエストすると、「デモをリクエスト」グラフィカルリンクがページの上部に表示されます。次の図を参照してください。

![](assets/TestPage.png)

