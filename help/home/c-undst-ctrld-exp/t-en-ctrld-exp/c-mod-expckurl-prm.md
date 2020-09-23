---
description: ExpCookieURLパラメータを使用して、制御対象のテストが適切に動作しているかどうかをテストできます。
solution: Analytics,Analytics
title: ExpCookieURL パラメーターの変更（オプション）
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---


# ExpCookieURL パラメーターの変更（オプション）{#modifying-the-expcookieurl-paramter-optional}

ExpCookieURLパラメータを使用して、制御対象のテストが適切に動作しているかどうかをテストできます。

このパラメーターは、要求されたときに指定したテストおよびグループに配置され、Webサイトのルートにリダイレクトされる仮想ページのURLを定義します。 その時点から、テストの最後まで、指定したテストとグループの一部となります。

このパラメーターのデフォルトのページはです [!DNL setcookie.htm]が、任意の有効な仮想URLを使用できます。

>[!NOTE]
>
>仮想URLを指定し、実際のページや既存のコンテンツの一部ではない必要があります。 指定したパスに、指定した名前のファイルはWebサーバー上に存在しない必要があります。

ExpCookieURLパラメータの例を次に示します。

[!DNL ExpCookieURL /setcookie.htm]
