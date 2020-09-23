---
description: 'null'
solution: Analytics,Analytics
title: ExpPartialMatch パラメーターの変更（オプション）
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 14%

---


# ExpPartialMatch パラメーターの変更（オプション）{#modifying-the-exppartialmatch-parameter-optional}

制御下の実験を有効にして、Webサイト全体またはWebサイトのサブディレクトリ全体を別の場所に再マップする場合は、 [!DNL txlogd.conf] ファイル内のExpPartialMatchパラメータを「on」に設定できます。 デフォルトは「off」です。

次に、ExpPartialMatchパラメータの例を示します。

[!DNL ExpPartialMatch off]

このパラメーターを「オン」に設定する場合は、Webサイト全体を誤って再マッピングする可能性があるので、注意が必要です。
