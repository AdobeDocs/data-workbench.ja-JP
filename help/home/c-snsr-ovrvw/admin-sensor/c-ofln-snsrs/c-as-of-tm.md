---
description: Data Workbench サーバーは、Sensor などのデータのソースからデータを受け取ると、そのソースを認識します。
title: 「基準日」について
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# 「基準日」について{#understanding-as-of-time}

{{eol}}

Data Workbench サーバーは、Sensor などのデータのソースからデータを受け取ると、そのソースを認識します。

基準日は、 [!DNL data workbench server] には、対応するすべてのデータソースのデータが含まれます。

例えば、3 つのセットがあるとします [!DNL Sensors] にデータを送信する [!DNL data workbench server]:WEB1、WEB2 および WEB3。 を [!DNL data workbench server] これらのデータを受信して処理します [!DNL Sensors]の場合、各ソースからのデータを自動的に期待します。 基準日は、 [!DNL data workbench server] これら 3 つのソースのすべてからデータを受け取った。

実際には、 [!DNL data workbench server] 「基準時間」を気にするだけで、「壁時間」と呼ばれるものや、壁の時計からの時間は気にしない。 この [!DNL data workbench server] は、時刻を基準日時としてのみ認識します。 これは、レポートが常に基準時間に基づいて実行され、部分的なデータのみを含むレポートをシステムのエンドユーザーに送信できないようにするので、レポート作成の目的で特に重要です。

この [!DNL data workbench server] トランスミッターから送信されたデータを使用して、Web サイトから収集された実際のデータか、サイトから送信された定期的なハートビートかに関わらず、基準時間を提供します [!DNL Sensors]. これらのハートビートは、次の 2 つの目的を果たします。

1. HTTP/1.1 の永続的な接続を [!DNL Sensor] そして [!DNL data workbench server].

1. Web サイトトラフィックが収集されて [!DNL data workbench server].
