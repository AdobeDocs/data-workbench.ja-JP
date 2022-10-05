---
description: ExpPartialMatch パラメーターの変更（オプション）
title: ExpPartialMatch パラメーターの変更（オプション）
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# ExpPartialMatch パラメーターの変更（オプション）{#modifying-the-exppartialmatch-parameter-optional}

{{eol}}

対照実験を有効にして、Web サイト全体または Web サイトのサブディレクトリ全体を別の場所に再マッピングする場合は、 [!DNL txlogd.conf] ファイルを「on」に設定します。 デフォルトは「off」です。

以下に、ExpPartialMatch パラメーターの例を示します。

[!DNL ExpPartialMatch off]

このパラメーターを「on」に設定する場合は、Web サイト全体が誤って再マッピングされる可能性があるので、注意が必要です。
