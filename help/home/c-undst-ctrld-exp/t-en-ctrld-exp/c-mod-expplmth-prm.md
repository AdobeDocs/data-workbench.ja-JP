---
description: ExpPartialMatch パラメーターの変更（オプション）
title: ExpPartialMatch パラメーターの変更（オプション）
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# ExpPartialMatch パラメーターの変更（オプション）{#modifying-the-exppartialmatch-parameter-optional}

対照実験を有効にして、Webサイト全体またはWebサイトのサブディレクトリ全体を別の場所に再マップする場合は、[!DNL txlogd.conf]ファイルのExpPartialMatchパラメーターを「on」に設定できます。 デフォルトは「off」です。

次に、ExpPartialMatchパラメーターの例を示します。

[!DNL ExpPartialMatch off]

このパラメーターを「on」に設定する場合は、Webサイト全体が誤って再マッピングされる可能性があるので、注意が必要です。
