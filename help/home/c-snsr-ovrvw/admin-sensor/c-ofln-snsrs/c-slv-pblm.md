---
description: 障害が原因でWebサーバーがオフラインになった場合、このソリューションは、 Log Processing Mode.cfgファイルを開き、Data WorkbenchのID（この例ではWEB2）を「Offline Sources」セクションに追加する適切な権限を持つユーザーが必要な簡単なものです。
title: 問題の解決
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 問題の解決{#solving-the-problem}

障害が原因でWebサーバーがオフラインになった場合、このソリューションは、 Log Processing Mode.cfgファイルを開き、Data WorkbenchのID（この例ではWEB2）を「Offline Sources」セクションに追加する適切な権限を持つユーザーが必要な簡単なものです。

ファイルのこのセクションは、実際にはオフラインなので、このソースからのデータを今後予期しないと[!DNL data workbench server]に伝えます。

>[!NOTE]
>
>この変更は、担当のコンサルタントが実行する必要はありません。Adobe [!DNL Log Processing Mode.cfg]ファイルを開く適切な権限を持つユーザーは誰でも、この変更を行うことができます。

WEB2がデータの送信を再開し始めた場合、[!DNL data workbench server]はソースをオンラインに戻し、認識対象のすべてのソースから最後にデータを受信した時刻を反映するように基準時刻を調整します。 つまり、システムに取り込まれる新しいデータは、[!DNL Log Processing Mode.cfg file]に書き込まれるデータよりも優先されます。

WEB2が再びオフラインになった場合は、基準時間が再び停止し、既にオフラインソースとしてWEB2がリストされている場合でも、[!DNL Log Processing Mode.cfg]ファイルを再び編集する必要があります。 これは、基準時間の定義に従って、製品のデザインのアーティファクトです。システムが既知のすべてのソースのデータを最後に持つ時間

さらにWebサーバー(WEB4、WEB5、WEB6)を追加して、[!DNL data workbench server]へのデータの送信を開始する場合、[!DNL data workbench server]が新しいソースを認識するために何もする必要はありません。 システムは、前述のように、これらの新しいソースからのデータを期待する必要があることを単に認識します。
