---
description: ExpFileパラメータは、テストを定義するテスト設定ファイルの場所を指します。
solution: Analytics,Analytics
title: ExpFile パラメーターの変更
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# ExpFile パラメーターの変更{#modifying-the-expfile-parameter}

ExpFileパラメータは、テストを定義するテスト設定ファイルの場所を指します。

このパラメーターを設定すると、実験を実行できます。 テスト設定ファイルを作成する手順については、「[テストの設定と展開](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)」を参照してください。

次に、ExpFileパラメータの例を示します。

```
ExpFile /home/experiment.txt
```

このタブ区切りテキストファイル([!DNL .txt])は、[!DNL Sensor]フォルダー内の任意の場所に置くことができ、任意の名前を付けることができます。

実験ディレクトリの場所と指定した設定ファイルの名前を記録してください。これは、テスト設定ファイルをこの名前とこのディレクトリに保存する必要があるからです。

>[!NOTE]
>
>[!DNL Sensor]がインストールされているWebクラスター内の各マシンでこのパラメーターを同じように設定しないと、対照実験は機能しません。

このエントリは事前に設定され、悪影響を与えることなく継続的に[!DNL Sensor]設定ファイルに残すことができます。 [!DNL Sensor]が指定したテスト設定ファイル名を見つけなかったり、空白（つまり、存在するがコンテンツはない）の場合、[!DNL Sensor]はテストを実行せず、HTTPサーバにエラーイベントを記録し、それ以外の点でも通常どおりに動作し続けます。
