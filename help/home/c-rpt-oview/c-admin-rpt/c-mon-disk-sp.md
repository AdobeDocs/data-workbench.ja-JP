---
description: すべての Report Server マシンが可能な限り高いレベルで引き続き実行できるよう、使用可能なディスク容量を定期的に監視する必要があります。
title: ディスク容量の監視（レポートサーバ）
uuid: 590c8239-d20e-470e-b633-7785b75daaa6
exl-id: 0debd601-494f-4d4e-9452-c4d32678dc95
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 1%

---

# ディスク容量の監視{#monitoring-disk-space}

すべての Report Server マシンが可能な限り高いレベルで引き続き実行できるよう、使用可能なディスク容量を定期的に監視する必要があります。

各 [!DNL Report Server] マシンには次のタイプのデータが格納されます。

* オペレーティングシステムのデータ
* レポートデータ
* システムデータ

>[!NOTE]
>
>Adobeコンサルタントは、使用シナリオを評価して、Adobeソフトウェアアプリケーションが生成し、必要とするデータストレージの量をプロジェクトするのに役立ちます。 そのような評価をリクエストするには、Adobeコンサルティングサービスにお問い合わせください。

* [レポートデータ容量の監視](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-ad0a63f3a6824e68acd675da0b6c5c23)
* [オペレーティングシステム、レポート、およびシステムデータのバックアップ](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-b5efb132ca5d4ee69a8608f9b4ab245b)

## レポートデータ容量の監視 {#section-ad0a63f3a6824e68acd675da0b6c5c23}

**推奨頻度：** 5 ～ 10 分ごと

レポートを [!DNL Reports] フォルダー内の [!DNL Report] インストールディレクトリ。

## オペレーティングシステム、レポート、およびシステムデータのバックアップ {#section-b5efb132ca5d4ee69a8608f9b4ab245b}

**推奨頻度：** 毎日

レポート、システム、およびオペレーティング・システムのデータは、お客様の会社の通常のバックアップ・システムと災害復旧システムを使用して、定期的かつ慎重にバックアップする必要があります。
