---
description: 対照実験とは、実験用サンプル群から得られた結果を標準の対照群から得た結果と比較することが可能な実験です。
solution: Analytics
title: Data Workbench対照実験
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Data Workbench対照実験{#data-workbench-controlled-experiments}

{{eol}}

対照実験とは、実験用サンプル群から得られた結果を標準の対照群から得た結果と比較することが可能な実験です。

Site では、Web サイトの様々な側面に関連する、対照実験とその結果を実装、測定、分析できます。 これにより、提案された変更を完全に実装するのに大きな時間や費用を費やす前に、Web サイトのパフォーマンスの向上に関する仮説をテストできます。

>[!NOTE]
>
>サイト実験は、使用される訪問者識別の唯一の方法が [!DNL Sensor] 永続的な cookie メソッドを設定します。 J2EE サーバー (JBoss、Tomcat、WebLogic、WebSphere) 上で動作するセンサーは、対照実験をサポートしていません。 詳しくは、次の節を参照してください。

Site を使用すると、A/B、A/B/A、多変量分析制御実験を実装して、現在の Web サイトのパフォーマンスに影響を与えることなく、統計的に正確なデータを得て仮説の詳細を評価できる十分なテストデータを収集できます。
