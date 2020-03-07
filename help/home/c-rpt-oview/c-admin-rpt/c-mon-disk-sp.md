---
description: すべてのReport Serverコンピューターが可能な限り高いレベルで動作するように、使用可能なディスク領域を定期的に監視する必要があります。
solution: Analytics
title: ディスク領域の監視
topic: Data workbench
uuid: 590c8239-d20e-470e-b633-7785b75daaa6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ディスク領域の監視{#monitoring-disk-space}

すべてのReport Serverコンピューターが可能な限り高いレベルで動作するように、使用可能なディスク領域を定期的に監視する必要があります。

各マシン [!DNL Report Server] には、次のタイプのデータが格納されます。

* オペレーティングシステムデータ
* レポートデータ
* システムデータ

>[!NOTE]
>
>アドビコンサルタントは、使用シナリオを評価し、アドビのソフトウェアアプリケーションが生成し、必要とするデータストレージの容量をプロジェクトするのに役立ちます。 そのような評価をリクエストする場合は、アドビのコンサルティングサービスにお問い合わせください。

* [レポートデータ領域の監視](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-ad0a63f3a6824e68acd675da0b6c5c23)
* [オペレーティングシステム、レポート、およびシステムデータのバックアップ](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-b5efb132ca5d4ee69a8608f9b4ab245b)

## レポートデータ領域の監視 {#section-ad0a63f3a6824e68acd675da0b6c5c23}

**推奨頻度：** 5 ～ 10分ごと

インストールディレクトリ内のフォルダーに、レポートを収容できる十分なディス [!DNL Reports] ク領域があることを確 [!DNL Report] 認します。

## オペレーティングシステム、レポート、およびシステムデータのバックアップ {#section-b5efb132ca5d4ee69a8608f9b4ab245b}

**推奨頻度：** 毎日

レポート、システム、およびオペレーティングシステムのデータは、お客様の会社の通常のバックアップおよび災害復旧システムを使用して、定期的に、かつ注意深くバックアップする必要があります。
