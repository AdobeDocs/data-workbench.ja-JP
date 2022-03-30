---
description: ExpCookieURL パラメーターを使用して、対照実験が正しく機能していることをテストできます。
solution: Analytics
title: ExpCookieURL パラメーターの変更（オプション）
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# ExpCookieURL パラメーターの変更（オプション）{#modifying-the-expcookieurl-paramter-optional}

ExpCookieURL パラメーターを使用して、対照実験が正しく機能していることをテストできます。

このパラメーターは、要求されたときに指定の実験とグループに配置し、Web サイトのルートにリダイレクトする仮想ページの URL を定義します。 この時点から実験の終わりまで、ユーザーは指定した実験とグループに含まれます。

このパラメーターのデフォルトのページは [!DNL setcookie.htm]に含まれていますが、任意の有効な仮想 URL を使用できます。

>[!NOTE]
>
>これは仮想 URL にする必要があり、実際のページや既存のコンテンツの一部にすることはできません。 指定したパスに、指定した名前のファイルが Web サーバー上に存在しないはずです。

以下に、ExpCookieURL パラメーターの例を示します。

[!DNL ExpCookieURL /setcookie.htm]
