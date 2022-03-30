---
description: ExpFile パラメーターは、実験を定義する実験設定ファイルの場所を指します。
solution: Analytics
title: ExpFile パラメーターの変更
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# ExpFile パラメーターの変更{#modifying-the-expfile-parameter}

ExpFile パラメーターは、実験を定義する実験設定ファイルの場所を指します。

このパラメーターを設定すると、実験を実行できます。 実験設定ファイルを作成する手順については、 [実験の設定とデプロイ](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

以下に、ExpFile パラメーターの例を示します。

```
ExpFile /home/experiment.txt
```

このタブ区切りテキストファイル ( [!DNL .txt]) は [!DNL Sensor] フォルダーに保存し、任意の便利な名前を付けることができます。

この名前とこのディレクトリに実験設定ファイルを保存する必要があるので、実験ディレクトリの場所と指定した設定ファイルの名前を必ず記録してください。

>[!NOTE]
>
>このパラメーターを、Web クラスター内の各マシンで、 [!DNL Sensor] がインストールされている場合、対照実験は機能しません。

このエントリは事前設定され、 [!DNL Sensor] 設定ファイルを継続的に作成し、悪影響を及ぼさない。 指定した実験設定ファイル名が次の場所で見つからない場合： [!DNL Sensor] または空白（つまり、存在するがコンテンツがない）。 [!DNL Sensor] は実験をおこなわず、HTTP サーバー上にエラーイベントを記録し、その他のあらゆる点で引き続き正常に動作します。
