---
description: 実験をデプロイしたら、実験が正しく機能していることを検証する必要があります。
solution: Analytics,Analytics
title: 実験の検証
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# 実験の検証{#validating-the-experiment}

実験をデプロイしたら、実験が正しく機能していることを検証する必要があります。

[ExpCookieURLパラメーターの変更（オプション）](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)で説明したように、[!DNL Sensor]設定ファイルのExpCookieURLパラメーターで指定されたページを使用して、特定の実験グループに自分を配置できます。

デフォルトの仮想ページは[!DNL /setcookie.htm]ですが、ExpCookieURLパラメーターに設定した値を使用する必要があります。

## テストページのリクエスト{#section-8aed3b48d47f4e6c8869c0216f8781b1}

Webサイトに対する特定の実験グループをテストするには、ブラウザーがcookieを受け入れるように設定されていて、このWebサイトのcookieをまだ持っていない必要があります。

新しいグループをテストする際は、必ずWebサイトのCookieをクリアしてください。

特定の実験内の特定のグループに自分を配置するには、次の形式のクエリ文字列を使用してテストページをリクエストします。

[!DNL http://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

次に例を示します。

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

仮想URLリクエストがサーバーに送信されると、[!DNL Sensor]は、指定された実験内の指定されたグループのメンバーであることを特定し、Webサイトのルートにリダイレクトします。 これで、Webサイト上の適切な場所に移動して、その実験とグループに対して正しいコンテンツが表示されるかどうかを検証できます。

ブラウザーに次のコードを入力すると、ブラウザーにWebサイトのホームページが表示され、New_Homepage実験内のindex2グループに配置されます。

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

index2グループの訪問者がホームページをリクエストすると、次の図のように、「デモをリクエスト」グラフィカルリンクがページの上位に表示されます。

![](assets/TestPage.png)
