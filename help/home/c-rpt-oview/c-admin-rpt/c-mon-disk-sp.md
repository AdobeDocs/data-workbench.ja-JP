---
description: すべてのReport Serverマシンが可能な限り高いレベルで引き続き実行できるように、使用可能なディスク領域を定期的に監視する必要があります。
title: ディスク容量の監視
uuid: 590c8239-d20e-470e-b633-7785b75daaa6
exl-id: 0debd601-494f-4d4e-9452-c4d32678dc95
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 3%

---

# ディスク容量の監視{#monitoring-disk-space}

すべてのReport Serverマシンが可能な限り高いレベルで引き続き実行できるように、使用可能なディスク領域を定期的に監視する必要があります。

各[!DNL Report Server]マシンは、次のタイプのデータを保存します。

* オペレーティングシステムデータ
* レポートデータ
* システムデータ

>[!NOTE]
>
>Adobeコンサルタントは、使用シナリオを評価し、Adobeソフトウェアアプリケーションが生成し、必要とするデータストレージの量をプロジェクトするのに役立ちます。 そのような評価をリクエストするには、Adobeコンサルティングサービスにお問い合わせください。

* [レポートのデータ容量の監視](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-ad0a63f3a6824e68acd675da0b6c5c23)
* [オペレーティングシステム、レポート、およびシステムデータのバックアップ](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-b5efb132ca5d4ee69a8608f9b4ab245b)

## レポートデータ容量の監視{#section-ad0a63f3a6824e68acd675da0b6c5c23}

**推奨頻度：** 5 ～ 10分ごと

[!DNL Report]インストールディレクトリ内の[!DNL Reports]フォルダーに、レポート用に十分なディスク領域を用意してください。

## オペレーティングシステム、レポート、およびシステムデータのバックアップ{#section-b5efb132ca5d4ee69a8608f9b4ab245b}

**推奨頻度：** 毎日

レポート、システム、オペレーティングシステムのデータは、お客様の企業の通常のバックアップシステムと災害復旧システムを使用して、定期的かつ慎重にバックアップする必要があります。
