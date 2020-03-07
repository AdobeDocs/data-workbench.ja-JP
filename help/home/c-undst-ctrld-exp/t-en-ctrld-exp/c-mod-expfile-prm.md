---
description: ExpFileパラメータは、テストを定義するテスト設定ファイルの場所を指します。
solution: Insight,Analytics
title: ExpFileパラメータの変更
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ExpFileパラメータの変更{#modifying-the-expfile-parameter}

ExpFileパラメータは、テストを定義するテスト設定ファイルの場所を指します。

このパラメータを設定すると、実験を実行できます。 テスト設定ファイルを作成する手順については、「テストの設 [定と展開」を参照してください](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。

次に、ExpFileパラメータの例を示します。

```
ExpFile /home/experiment.txt
```

このタブ区切りテキストファ [!DNL .txt]イル()は、フォルダー内の任意の場所に配置 [!DNL Sensor] でき、任意の名前を付けることができます。

実験ディレクトリの場所と指定した設定ファイルの名前を必ず記録してください。この名前を使用して（このガイドで後述する）実験設定ファイルを保存する必要があるからです。

>[!NOTE]
>
>このパラメーターを、がインストールされているWebクラスター内の各マシンに同じように設定しない場合、 [!DNL Sensor] 対照実験は機能しません。

このエントリは事前に設定され、設定ファイルに [!DNL Sensor] 継続的に保持され、悪影響を及ぼすことはありません。 指定したテスト設定ファイル名がで見つからない場合、または空白の場合（つまり、存在するがコンテンツは含まれない場合）、テストを実行せず、 [!DNL Sensor][!DNL Sensor] HTTPサーバー上でエラーイベントをログに記録し、その他の点でも正常に動作し続けます。
