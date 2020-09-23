---
description: Data Workbenchサーバーは、Sensorなどのデータソースからデータを受け取ると、そのソースを認識します。
solution: Analytics
title: 「基準日」について
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---


# 「基準日」について{#understanding-as-of-time}

Data Workbenchサーバーは、Sensorなどのデータソースからデータを受け取ると、そのソースを認識します。

基準日時は、が認識しているすべてのデータソースのデータを [!DNL data workbench server] 持つことを保証します。

データを送信する3つ [!DNL Sensors] のセットがあるとし [!DNL data workbench server]ます。WEB1、WEB2およびWEB3。 これらのデータを [!DNL data workbench server][!DNL Sensors]受け取って処理する際に、各ソースのデータが自動的に期待されます。 基準日時は、これら3つのソースすべてから最後にデータを [!DNL data workbench server] 受け取った日時を示します。

実際的には、基準日の時間に関する [!DNL data workbench server] のみが重要で、「壁の時間」と呼ばれるものや、壁の時計からの時間は重要ではありません。 その時刻 [!DNL data workbench server] は基準日の時刻と同じ時刻しか認識されません。 これは、レポートが常に基準日時に基づいて実行されるようにレポートする場合に特に重要です。これにより、部分的なデータのみを含むレポートがシステムのエンドユーザに送信されなくなります。

は、送信機から送信されたデータを [!DNL data workbench server] 使用して基準日時を指定します。基準日時は、Webサイトから収集された実際のデータか、自分が送信した定期的なハートビートかにかかわらず [!DNL Sensors]です。 これらのハートビートは、2つの目的を果たします。

1. との間でHTTP/1.1の永続的な接続を開いたままにす [!DNL Sensor] るには、次のように指定し [!DNL data workbench server]ます。

1. Webサイトトラフィックが収集されてWebサイトに送信されないイベントの基準日時を最新の状態に保つ [!DNL data workbench server]。

