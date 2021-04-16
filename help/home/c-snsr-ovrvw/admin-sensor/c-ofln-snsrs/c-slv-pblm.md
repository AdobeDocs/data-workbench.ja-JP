---
description: 障害が発生してWebサーバーがオフラインになった場合、このソリューションは、Log Processing Mode.cfgファイルを開き、SensorのID（例えば、WEB2）を「Offline Sources」セクションに追加する適切な権限を持つData Workbenchユーザーを必要とする単純なものです。
title: 問題の解決
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 問題の解決{#solving-the-problem}

障害が発生してWebサーバーがオフラインになった場合、このソリューションは、Log Processing Mode.cfgファイルを開き、SensorのID（例えば、WEB2）を「Offline Sources」セクションに追加する適切な権限を持つData Workbenchユーザーを必要とする単純なものです。

このファイルのこのセクションは、実際はオフラインなので、このソースのデータはもはや予期しないと[!DNL data workbench server]に伝えます。

>[!NOTE]
>
>この変更は、Adobeコンサルタントが実行する必要はありません。 [!DNL Log Processing Mode.cfg]ファイルを開く権限を持っている人なら誰でも、この変更を行うことができます。

WEB2が再度データの送信を開始すると、[!DNL data workbench server]はソースをオンラインに戻し、認識対象のすべてのソースから最後にデータを受信した時刻を反映するように基準日時を調整します。 つまり、システムに入る新しいデータは、[!DNL Log Processing Mode.cfg file]に書き込まれるデータよりも優先されます。

WEB2が再びオフラインになった場合は、基準時点が再び停止し、既にオフラインソースとしてリストされているWEB2がある場合でも、[!DNL Log Processing Mode.cfg]ファイルを再度編集する必要があります。 これは、基準日時の定義に合わせて、製品のデザインのアーティファクトです。システムが既知のすべてのソースのデータを最後に取得したとき。

他のWebサーバー(WEB4、WEB5、WEB6)を追加し、それらのサーバーが[!DNL data workbench server]にデータを送信し始める場合、[!DNL data workbench server]に新しいソースを認識させるために何もする必要はありません。 システムは、上記のように、これらの新しいソースからのデータを期待していることに気づくだけです。
