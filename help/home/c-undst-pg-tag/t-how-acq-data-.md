---
description: サイトのコンテンツを提供する Web サーバーごとにセンサーをインストールして実行し、これらのサーバーで認識されるすべての要求を収集する必要があります。
title: データの取得方法
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
exl-id: 1c886f60-eae9-48c2-b641-396c622035d4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# データの取得方法{#how-do-i-acquire-this-data}

{{eol}}

サイトのコンテンツを提供する Web サーバーごとにセンサーをインストールして実行し、これらのサーバーで認識されるすべての要求を収集する必要があります。

これらのリクエストは、サイトに対しておこなわれたリクエストの 90%以上と、サイトのトラフィックを完全に分析するために必要なデータの 90%以上を占めます。 [!DNL Page Tags] を使用して、web サーバーに認識されない残りの 10%以下のトラフィックデータを収集します。 ただし、以下は、運用上の経験に基づき、好みに応じて、サイトから Web リクエストデータを収集するための有効な設定です。

1. [!DNL Sensor] が、管理対象の各 web サーバー、およびサイトをサポートする各 web サーバーにインストールされている。 サードパーティサイトのコンテンツ、キャッシュから提供されるコンテンツ、特定の種類の動的コンテンツにタグを付ける必要があり、そのようなページタグは、収集したデータを実行中の Web サーバーに送信する必要があります [!DNL Sensor]. ページタグリクエストのトラフィックレベルがそのような妥当性を満たす場合や、特殊な場合は、Web サーバーを追加して、これらのページタグリクエストを収集する専用の Web サーバーを作成できます。
1. [!DNL Sensor] は、このガイドでデータ収集サーバーとも呼ばれる 2 つの Web サーバー（タグ付きページからのページタグ要求データの収集専用の場所）にインストールされます。 サイト上のすべてのコンテンツにタグが付けられ、すべてのページタグは 2 つのデータ収集サーバーに送られます。
1. [!DNL Sensor’s] データ収集サービスは、データ収集サーバーを実行してすべての web リクエストデータを収集する外部業者によって提供されます。 この場合、サイト上のすべてのコンテンツにタグが付けられ、ページタグがそのデータをアウトソースのデータ収集サーバーに送信します。

   詳しくは、 [!DNL Sensor]を参照し、 *Data Workbench [!DNL Sensor] ガイド*.
