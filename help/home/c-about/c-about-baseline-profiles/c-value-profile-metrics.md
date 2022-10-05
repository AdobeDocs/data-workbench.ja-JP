---
description: 値プロファイルの指標
title: 値プロファイルの指標
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 17%

---

# 値プロファイルの指標{#value-profile-metrics}

{{eol}}

| 指標 | 数式 | レベル | 説明 |
|---|---|---|---|
| コンバージョン | `Sessions[not Session_Value=#0]/Sessions` | セッション | （ビジネス価値モデルで定義された）ビジネス価値を生み出したセッションの割合。 |
| 価値の% | `Value/total(Value)` | セッション | 選択したセッションセットから生成された値全体の割合。 |
| 値 | `sum(Session_Value, Session)*0.01` | セッション | 生成されたビジネス価値の合計（ビジネス価値モデルで定義される）。 |
| バリューイベント | `Sessions[not Session_Value=#0]` | セッション | （ビジネス価値モデルで定義された）ビジネス価値を生成したセッションの数。 |
| 訪問者ごとのバリューイベント | `(Value_Events/Visitors) by Visitor` | 訪問者。 | （ビジネスバリューモデルで定義された）ビジネスバリューを生み出した各訪問者の平均セッション数。 |
| 訪問者あたりの値 | `(Value/Visitors) by Visitor` | 訪問者。 | 各訪問者が生成した平均ビジネス価値（ドル単位）。 |
