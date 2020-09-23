---
description: 障害が発生してWebサーバーがオフラインになった場合、このソリューションは、Log Processing Mode.cfgファイルを開き、SensorのID（例えば、WEB2）を「Offline Sources」セクションに追加する適切な権限を持つData Workbenchユーザーを必要とする単純なものです。
solution: Analytics
title: 問題の解決
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# 問題の解決{#solving-the-problem}

障害が発生してWebサーバーがオフラインになった場合、このソリューションは、Log Processing Mode.cfgファイルを開き、SensorのID（例えば、WEB2）を「Offline Sources」セクションに追加する適切な権限を持つData Workbenchユーザーを必要とする単純なものです。

このファイルのこのセクションは、実際はオフラインなの [!DNL data workbench server] で、このソースのデータを予期すべきではないということを示しています。

>[!NOTE]
>
>この変更は、Adobeコンサルタントが実行する必要はありません。 ファイルを開く権限を持つユーザーはだれでも、この変更を行うことができ [!DNL Log Processing Mode.cfg] ます。

WEB2が再度データの送信を開始した場合、はそのソースをオンラインに戻し、対応するすべてのソースから最後にデータを受信した時刻を反映するように基準日時を調整します。 [!DNL data workbench server] つまり、システムに新しく入力するデータは、に書き込まれるデータよりも優先され [!DNL Log Processing Mode.cfg file]ます。

WEB2が再びオフラインになった場合、基準時点が再び停止し、既にオフラインソースとしてリストされているWEB2がある場合でも、 [!DNL Log Processing Mode.cfg] ファイルを編集し直す必要があります。 これは、基準日時の定義に合わせて、製品のデザインのアーティファクトです。システムが既知のすべてのソースのデータを最後に取得したとき。

他のWebサーバー(WEB4、WEB5、WEB6)を追加した場合、そのサーバーがにデータを送信し始めると [!DNL data workbench server]き、新しいソースを認識するために何もする必要はありません [!DNL data workbench server] 。 システムは、上記のように、これらの新しいソースからのデータを期待していることに気づくだけです。
