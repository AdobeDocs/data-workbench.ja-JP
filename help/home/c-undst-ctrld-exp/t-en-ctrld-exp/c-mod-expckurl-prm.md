---
description: ExpCookieURLパラメータを使用して、制御対象のテストが適切に動作しているかどうかをテストできます。
solution: Analytics,Analytics
title: ExpCookieURL パラメーターの変更（オプション）
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# ExpCookieURL パラメーターの変更（オプション）{#modifying-the-expcookieurl-paramter-optional}

ExpCookieURLパラメータを使用して、制御対象のテストが適切に動作しているかどうかをテストできます。

このパラメーターは、要求されたときに指定したテストおよびグループに配置され、Webサイトのルートにリダイレクトされる仮想ページのURLを定義します。 その時点から、テストの最後まで、指定したテストとグループの一部となります。

このパラメーターのデフォルトのページは[!DNL setcookie.htm]ですが、任意の有効な仮想URLを使用できます。

>[!NOTE]
>
>仮想URLを指定し、実際のページや既存のコンテンツの一部ではない必要があります。 指定したパスに、指定した名前のファイルはWebサーバー上に存在しない必要があります。

ExpCookieURLパラメータの例を次に示します。

[!DNL ExpCookieURL /setcookie.htm]
