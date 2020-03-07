---
description: 障害が原因でWebサーバーがオフラインになった場合、このソリューションは、Data WorkbenchユーザーがLog Processing Mode.cfgファイルを開き、SensorのID（この例ではWEB2）を「Offline Sources」セクションに追加するのに適切な権限を持つ必要がある簡単なものです。
solution: Insight
title: 問題の解決
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 問題の解決{#solving-the-problem}

障害が原因でWebサーバーがオフラインになった場合、このソリューションは、Data WorkbenchユーザーがLog Processing Mode.cfgファイルを開き、SensorのID（この例ではWEB2）を「Offline Sources」セクションに追加するのに適切な権限を持つ必要がある簡単なものです。

このファイルのこのセクションは、実際 [!DNL data workbench server] はオフラインなので、このソースのデータを予期しないように指示します。

>[!NOTE]
>
>この変更は、アドビコンサルタントが実行する必要はありません。 ファイルを開く権限を持つユーザーはだれで [!DNL Log Processing Mode.cfg] も、この変更を行うことができます。

WEB2が再度データの送信を開始すると、はソースをオンラインに戻し、 [!DNL data workbench server] As Of Timeを調整して、認識されているすべてのソースから最後にデータを受け取った時間を反映します。 つまり、システムに取り込まれる新しいデータは、で書き込まれるデータよりも優先されま [!DNL Log Processing Mode.cfg file]す。

WEB2が再びオフラインになった場合は、基準日時が再び停止し、既にWEB2がオフラインソースとしてリストされている場合でも、ファイルを再編集する必要があ [!DNL Log Processing Mode.cfg] ります。 これは、基準時間の定義に従って、製品のデザインのアーティファクトです。システムが最後に既知のすべてのソースのデータを持つ時間。

さらにWebサーバー(WEB4、WEB5、WEB6)を追加し、そのサーバーがにデータを送信し始める場合、新しいソースを認識させるために何もする必要はあ [!DNL data workbench server][!DNL data workbench server] りません。 システムは、上記のように、これらの新しいソースからのデータを期待していることを単に認識します。
