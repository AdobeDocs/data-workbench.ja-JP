---
description: Data Workbenchサーバーは、Sensorなどのデータソースからデータを受け取ると、そのソースを認識します。
title: 「基準日」について
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# 「基準日」について{#understanding-as-of-time}

Data Workbenchサーバーは、Sensorなどのデータソースからデータを受け取ると、そのソースを認識します。

基準日時は、[!DNL data workbench server]が認識しているすべてのデータソースのデータを保持する保証です。

例えば、[!DNL data workbench server]にデータを送信する3つの[!DNL Sensors]があるとします。WEB1、WEB2およびWEB3。 [!DNL data workbench server]がこれらの[!DNL Sensors]からデータを受け取って処理すると、これらの各ソースからのデータが自動的に期待されます。 基準日の時刻は、[!DNL data workbench server]がこれら3つのソースすべてから最後にデータを受け取った時刻を示します。

実際には、[!DNL data workbench server]は基準日の時間だけを考慮し、「壁の時間」と呼ばれるものや、壁の時計からの時間は考慮しません。 [!DNL data workbench server]は時刻を基準時刻としてのみ知っています。 これは、レポートが常に基準日時に基づいて実行されるようにレポートする場合に特に重要です。これにより、部分的なデータのみを含むレポートがシステムのエンドユーザに送信されなくなります。

[!DNL data workbench server]は、送信者から送信されたデータを使用して基準日時を指定します。基準日時は、Webサイトから収集された実際のデータか、[!DNL Sensors]から送信された定期的なハートビートかに関係ありません。 これらのハートビートは、2つの目的を果たします。

1. [!DNL Sensor]と[!DNL data workbench server]の間でHTTP/1.1の持続的な接続を開いたままにする。

1. Webサイトトラフィックが収集され[!DNL data workbench server]に送信されていないイベントの基準日時を最新の状態に保つ。
