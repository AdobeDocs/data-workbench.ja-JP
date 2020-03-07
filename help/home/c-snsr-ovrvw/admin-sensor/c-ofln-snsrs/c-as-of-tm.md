---
description: Data Workbenchサーバーは、Sensorなどのデータソースからデータを受け取ると、そのソースを認識します。
solution: Insight
title: 「基準日」時間について
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 「基準日」時間について{#understanding-as-of-time}

Data Workbenchサーバーは、Sensorなどのデータソースからデータを受け取ると、そのソースを認識します。

基準日時は、が認識しているすべての [!DNL data workbench server] データソースのデータを保持する保証です。

データを次の3つのURLに送信す [!DNL Sensors] るとします [!DNL data workbench server]。WEB1、WEB2、WEB3。 これらのデ [!DNL data workbench server] ータを受信して処理すると、各ソ [!DNL Sensors]ースのデータが自動的に期待されます。 基準日時は、これら3つのソースからデータを [!DNL data workbench server] 受信した最後の時刻を示します。

実際には、基準時 [!DNL data workbench server] 間のみを考慮し、「時間」と呼ばれるものや、壁の時計からの時間は考慮しません。 時刻は [!DNL data workbench server] 基準時間としてのみ知られています。 これは、レポートが常に基準時間に基づいて実行され、部分的なデータのみを含むレポートがシステムのエンドユーザーに送信されないようにするので、レポートの目的で特に重要です。

は、 [!DNL data workbench server] 送信者から送信されたデータを使用して、Webサイトから収集された実際のデータか、または自分が送信した定期的なハートビートかに関わらず、基準日時を提供しま [!DNL Sensors]す。 これらのハートビートは、次の2つの目的を果たします。

1. との間でHTTP/1.1の永続的な接続を開いたままにす [!DNL Sensor] る場合 [!DNL data workbench server]。

1. Webサイトトラフィックが収集され、に送信されない場合に、基準日時を最新の状態に保つ場合 [!DNL data workbench server]。

