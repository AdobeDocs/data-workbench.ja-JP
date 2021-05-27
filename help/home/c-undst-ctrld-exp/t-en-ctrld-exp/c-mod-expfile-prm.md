---
description: ExpFileパラメーターは、実験を定義する実験設定ファイルの場所を指します。
solution: Analytics,Analytics
title: ExpFile パラメーターの変更
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# ExpFile パラメーターの変更{#modifying-the-expfile-parameter}

ExpFileパラメーターは、実験を定義する実験設定ファイルの場所を指します。

このパラメーターを設定すると、実験を実行できます。 実験設定ファイルを作成する手順については、「[実験の設定とデプロイ](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)」を参照してください。

次に、ExpFileパラメーターの例を示します。

```
ExpFile /home/experiment.txt
```

このタブ区切りテキストファイル([!DNL .txt])は、[!DNL Sensor]フォルダー内の任意の場所に配置でき、任意の名前を付けることができます。

実験ディレクトリの場所と指定した設定ファイルの名前を必ず記録してください。これは、この名前とこのディレクトリに実験設定ファイルを保存する必要があるからです（このガイドで後述します）。

>[!NOTE]
>
>[!DNL Sensor]がインストールされているWebクラスター内の各マシンで、このパラメーターを同じように設定しないと、対照実験は機能しません。

このエントリは事前に設定して、[!DNL Sensor]構成ファイルに継続的に残しておくことができ、悪影響はありません。 指定された実験設定ファイル名が[!DNL Sensor]で見つからない場合や空白（存在するが内容がない場合）は、[!DNL Sensor]は実験を実行せず、HTTPサーバーにエラーイベントを記録し、他のあらゆる点で引き続き正常に動作します。
