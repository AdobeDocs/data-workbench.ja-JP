---
description: テストを導入した後、テストが正しく動作していることを検証する必要があります。
solution: Analytics,Analytics
title: 実験の検証
topic: Data workbench
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---


# 実験の検証{#validating-the-experiment}

テストを導入した後、テストが正しく動作していることを検証する必要があります。

「ExpCookieURLパラメータの [変更（オプション）](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)」で説明されているように、 [!DNL Sensor] 設定ファイルのExpCookieURLパラメータで指定されたページを使用して、自分を特定のテストグループに配置できます。

デフォルトの仮想ページはです [!DNL /setcookie.htm]が、ExpCookieURLパラメータで設定した値を使用する必要があります。

## テストページのリクエスト {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Webサイト用の特定のテストグループをテストするには、ブラウザーがcookieを受け入れるように設定されている必要があります。また、このWebサイト用のcookieをまだ持っていない必要があります。

新しいグループをテストするたびに、WebサイトのCookieをクリアする必要があります。

特定のテスト内の特定のグループに自分を配置するには、次の形式のクエリ文字列を使用してテストページをリクエストします。

[!DNL http://] *&lt;[!DNL sitename/?Experiment Name=Group Name]>*

次に例を示します。

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

仮想URLリクエストがサーバーに送信されると、は、指定されたテスト内の指定されたグループのメンバーであることを [!DNL Sensor] 示し、Webサイトのルートにリダイレクトします。 これで、Webサイトの適切な場所に移動して、そのテストやグループに対して正しいコンテンツが表示されるかどうかを検証できます。

ブラウザーに次の項目を入力すると、ブラウザーにWebサイトのホームページが表示され、New_Homepageテスト内のindex2グループに配置されます。

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

index2グループの訪問者がホームページを要求すると、次の図のように、「Request a Demo」グラフィック・リンクがページ上の上部に表示されます。

![](assets/TestPage.png)

