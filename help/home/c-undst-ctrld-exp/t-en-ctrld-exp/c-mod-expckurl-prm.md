---
description: ExpCookieURLパラメータを使用して、制御されたテストが正しく動作しているかどうかをテストできます。
solution: Insight,Analytics
title: ExpCookieURLパラメータの変更（オプション）
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ExpCookieURLパラメータの変更（オプション）{#modifying-the-expcookieurl-paramter-optional}

ExpCookieURLパラメータを使用して、制御されたテストが正しく動作しているかどうかをテストできます。

このパラメーターは、要求されたときに指定したテストとグループに配置され、Webサイトのルートにリダイレクトされる仮想ページのURLを定義します。 この時点から、テストの最後まで、指定したテストとグループの一部となります。

このパラメーターのデフォルトのペ [!DNL setcookie.htm]ージはですが、任意の有効な仮想URLを使用できます。

>[!NOTE]
>
>これは仮想URLであり、実際のページや既存のコンテンツではない。 Webサーバー上の指定されたパスに、指定された名前のファイルは存在しません。

ExpCookieURLパラメータの例を次に示します。

[!DNL ExpCookieURL /setcookie.htm]
