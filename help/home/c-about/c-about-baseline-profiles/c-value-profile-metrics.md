---
description: 'null'
solution: Analytics
title: 値プロファイルの指標
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: 662bf8fdff196814e5a11c1f5e1ae12d4d57e1db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 16%

---


# 値プロファイルの指標{#value-profile-metrics}

| 指標 | 数式 | レベル | 説明 |
|---|---|---|---|
| コンバージョン | `Sessions[not Session_Value=#0]/Sessions` | セッション | ビジネスバリューを生成したセッションの割合（ビジネスバリューモデルで定義）。 |
| 値の割合 | `Value/total(Value)` | セッション | 選択したセッションのセットから生成された値全体の割合。 |
| 値 | `sum(Session_Value, Session)*0.01` | セッション | 生成されたビジネスバリューの総額（ビジネスバリューモデルで定義）。 |
| 値のイベント | `Sessions[not Session_Value=#0]` | セッション | ビジネスバリューを生成したセッションの数（ビジネスバリューモデルで定義）。 |
| 訪問者ごとの値のイベント | `(Value_Events/Visitors) by Visitor` | 訪問者。 | ビジネスバリューを生成した各訪問者のセッションの平均数（ビジネスバリューモデルの定義に基づく）。 |
| 訪問者ごとの値 | `(Value/Visitors) by Visitor` | 訪問者。 | 各訪問者が生成した平均ビジネス価値（ドル）。 |
