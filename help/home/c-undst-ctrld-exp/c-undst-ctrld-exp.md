---
description: 制御実験とは、実験用のサンプルグループから得られた結果を標準のコントロール母集団から得られた結果と比較できるテストです。
solution: Analytics,Analytics
title: Data Workbench制御実験
topic: Data workbench
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---


# Data Workbench Controlled Experiments{#data-workbench-controlled-experiments}

制御実験とは、実験用のサンプルグループから得られた結果を標準のコントロール母集団から得られた結果と比較できるテストです。

Siteでは、Webサイトの様々な側面に関連する制御された実験とその結果を実装、測定、分析できます。 これにより、提案された変更を完全に実装するのにかなりの時間や費用を費やす前に、Webサイトのパフォーマンスの向上に関する仮説をテストできます。

>[!NOTE]
>
>サイトの実験はデータセットでのみ分析できます。データセットでは、使用中の訪問者を識別する唯一の方法は [!DNL Sensor] set persistent cookieメソッドです。 J2EEサーバー（JBoss、Tomcat、WebLogicおよびWebSphere）上で実行されるセンサーは、実験の制御をサポートしません。 詳しくは、次の節を参照してください。

Siteを使用すると、現在のWebサイトのパフォーマンスに影響を与えることなく、十分なテストデータを収集し、統計的に正確なデータを仮説の詳細な評価に提供するためのA/B、A/B/Aおよび多変量制御実験を実装できます。
