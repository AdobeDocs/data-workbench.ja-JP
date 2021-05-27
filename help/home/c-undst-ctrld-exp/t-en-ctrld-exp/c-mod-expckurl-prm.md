---
description: ExpCookieURLパラメーターを使用して、対照実験が正しく機能していることをテストできます。
solution: Analytics,Analytics
title: ExpCookieURL パラメーターの変更（オプション）
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# ExpCookieURL パラメーターの変更（オプション）{#modifying-the-expcookieurl-paramter-optional}

ExpCookieURLパラメーターを使用して、対照実験が正しく機能していることをテストできます。

このパラメーターは、要求されたときに指定の実験とグループに配置し、Webサイトのルートにリダイレクトする仮想ページのURLを定義します。 その時点から実験の終わりまで、ユーザーは指定した実験とグループの一部になります。

このパラメーターのデフォルトのページは[!DNL setcookie.htm]ですが、任意の有効な仮想URLを使用できます。

>[!NOTE]
>
>これは仮想URLにする必要があり、実際のページや既存のコンテンツではない必要があります。 指定したパスに、指定した名前のファイルがWebサーバー上に存在しない必要があります。

次に、ExpCookieURLパラメーターの例を示します。

[!DNL ExpCookieURL /setcookie.htm]
