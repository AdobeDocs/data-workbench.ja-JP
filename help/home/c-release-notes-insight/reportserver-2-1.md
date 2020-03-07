---
description: Data Workbench Report Portal のセキュリティ更新。
title: DWB Report Portal 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWB Report Portal 2.1{#dwb-report-portal}

Data Workbench Report Portal のセキュリティ更新。

**セキュリティの重要な更新**

Report Portal には、ソルティングをサポートしている、より強力なハッシュアルゴリズムが導入されました。Report Portal 2.1 にアップグレードする場合は、フィールドサイズが 20 文字の新しいテキストフィールド PasswordSalt を users.mdb データベースに追加します。このフィールドは、パスワードソルトを保存するのに必要です。
