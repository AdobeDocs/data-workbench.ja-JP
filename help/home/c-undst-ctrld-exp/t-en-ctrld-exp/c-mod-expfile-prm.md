---
description: ExpFileパラメータは、テストを定義するテスト設定ファイルの場所を指します。
solution: Analytics,Analytics
title: ExpFile パラメーターの変更
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---


# ExpFile パラメーターの変更{#modifying-the-expfile-parameter}

ExpFileパラメータは、テストを定義するテスト設定ファイルの場所を指します。

このパラメーターを設定すると、実験を実行できます。 テスト設定ファイルを作成する手順については、「テストの [設定と導入](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)」を参照してください。

次に、ExpFileパラメータの例を示します。

```
ExpFile /home/experiment.txt
```

このタブ区切りテキストファイル( [!DNL .txt])は、 [!DNL Sensor] フォルダー内の任意の場所に配置でき、任意の名前を付けることができます。

実験ディレクトリの場所と指定した設定ファイルの名前を記録してください。これは、テスト設定ファイルをこの名前とこのディレクトリに保存する必要があるからです。

>[!NOTE]
>
>このパラメーターを、がインストールされているWebクラスター内の各マシンで同一に設定しない場合、実験の制御 [!DNL Sensor] は機能しません。

このエントリは事前に設定され、 [!DNL Sensor] 設定ファイルに継続的に残すことができ、悪影響はありません。 指定したテスト設定ファイル名がで見つからない場合、 [!DNL Sensor][!DNL Sensor] または空白の場合（つまり、存在するがコンテンツはない場合）、テストを実行せず、HTTPサーバーにエラーイベントを記録し、それ以外の点でも通常どおりに動作し続けます。
