---
description: ChangeCase 変換は、Action パラメーターの指定に従って、文字列の大文字と小文字を切り替えます。
solution: Analytics
title: ChangeCase
topic: Data workbench
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ChangeCase{#changecase}

ChangeCase 変換は、Action パラメーターの指定に従って、文字列の大文字と小文字を切り替えます。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| アクション | upper または lower。大文字（upper）にするか、小文字（lower）にするかを指定します。 | lower |
| Comments | (オプション)変換についてのメモ。 |  |
| Condition | この変換が適用される条件。 |  |
| Input | ログエントリからの入力として使用するフィールドの名前。 |  |
| Output | 出力フィールドの名前。 |  |

次の例は、Web サイトトラフィックから収集されたデータのフィールドを使用するものです。s-dns フィールド内の文字列を小文字に変更し、その変更後の値を x-lowercase-dns という新しいフィールドに出力しています。

![](assets/cfg_TransformationType_ChangeCase.png)

