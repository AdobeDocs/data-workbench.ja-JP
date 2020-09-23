---
description: 場合によっては、Insightサーバーマシンを既存のInsightサーバークラスターに追加する必要があります。
solution: Analytics
title: 既存のクラスターへの Insight サーバーの追加
uuid: 951bd6fe-14e4-4192-917c-342fde7b43ba
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 12%

---


# 既存のクラスターへの Insight サーバーの追加{#adding-insight-servers-to-an-existing-cluster}

場合によっては、Insightサーバーマシンを既存のInsightサーバークラスターに追加する必要があります。

DPUまたはFSUをクラスターに追加する場合は、マスター上の設定ファイル [!DNL Insight Server][!DNL Insight Server][!DNL Insight Server] を更新して、新しいマシンのアドレス情報を含め、新しいDPUまたはFSUを設定する必要があります。

>[!NOTE]
>
>この節で説明する手順は必須で [!DNL Insight]す。 をインストールしていない場合は、「* [!DNL Insight][!DNL Insight] User Guide*」の指示に従って操作を続行してください。

