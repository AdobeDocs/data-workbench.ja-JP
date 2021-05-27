---
description: Data Workbenchサーバーは、Sensorなどのデータソースからデータを受け取ると、そのソースを認識します。
title: 「基準日」について
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# 「基準日」について{#understanding-as-of-time}

Data Workbenchサーバーは、Sensorなどのデータソースからデータを受け取ると、そのソースを認識します。

基準時間は、[!DNL data workbench server]が認識するすべてのデータソースのデータを保持する保証です。

例えば、[!DNL data workbench server]にデータを送信する3つの[!DNL Sensors]のセットがあるとします。WEB1、WEB2およびWEB3。 [!DNL data workbench server]がこれらの[!DNL Sensors]からデータを受け取って処理すると、各ソースからのデータが自動的に要求されます。 基準日時は、[!DNL data workbench server]がこれら3つのソースすべてから最後にデータを受け取った時刻を示します。

実際には、[!DNL data workbench server]は基準時間のみを考慮し、「ウォール時間」と呼ばれるものや、壁の時計からの時間は考慮しません。 [!DNL data workbench server]は時刻を基準時刻としてのみ認識します。 これは、レポートが常に基準時間に基づいて実行され、部分的なデータのみを含むレポートがシステムのエンドユーザーに送信されないようにするので、レポートの目的で特に重要です。

[!DNL data workbench server]は、トランスミッターから送信されたデータを使用して、Webサイトから収集された実際のデータか、[!DNL Sensors]から送信された定期的なハートビートかに関わらず、基準時間を提供します。 これらのハートビートは、次の2つの目的を果たします。

1. [!DNL Sensor]と[!DNL data workbench server]の間のHTTP/1.1の永続的な接続を開いたままにする。

1. Webサイトトラフィックが収集されて[!DNL data workbench server]に送信されていない場合に、基準日の時間を現在の状態に保つ。
