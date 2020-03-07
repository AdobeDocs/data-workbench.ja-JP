---
description: 文字列パラメーターおよび数値パラメーターは、それぞれ文字列および数値として値を受け取ります。
solution: Analytics
title: 文字列パラメーターと数値パラメーター
topic: Data workbench
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 文字列パラメーターと数値パラメーター{#string-and-numeric-parameters}

文字列パラメーターおよび数値パラメーターは、それぞれ文字列および数値として値を受け取ります。

両者は同じように使用できますが、数値パラメーターは、数値を格納するように定義する必要があります。文字列パラメーターと数値パラメーターは、変換、条件、拡張ディメンションを定義する際に参照できます。同じ行で複数のパラメーターを参照することもできます。

[!DNL Input] フィールドまたは [!DNL Output] フィールドから文字列パラメーターや数値パラメーターを参照することはできませんが、文字列パラメーターを使用して定数の入力フィールドを定義することはできます。加えて、デコーダーまたはデコーダーグループから文字列パラメーターや数値パラメーターを参照することもできません。

This example shows a [!DNL Log Processing Dataset Include] file that defines a string parameter and a numeric parameter. 「Value Lookups」という名前の文字列パラメーターは、Data Workbench サーバーのインストールディレクトリを基準にファイルの場所（Lookups\Values）を定義しています。

![](assets/cfg_Parameters_StringNumeric.png)

