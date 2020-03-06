---
description: 'null'
solution: Analytics
title: バリュープロファイル指標
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# バリュープロファイル指標{#value-profile-metrics}

| 指標 | 数式 | レベル | 説明 |
|---|---|---|---|
| コンバージョン | [!DNL[Sessionsnot Session_Value=#0]/Sessions] | セッション | ビジネスバリュー(Business Value Model)で定義される、ビジネスバリューを生成したセッションの割合。 |
| 値の割合 | [!DNL Value/total(Value)] | セッション | 選択したセッションのセットから生成された全体的な値の割合。 |
| 値 | [!DNL sum(Session_Value, Session)*0.01] | セッション | 生成されたビジネスバリューの合計（ドル単位）（ビジネスバリューモデルで定義）。 |
| バリューイベント | [!DNL[Sessionsnot Session_Value=#0]] | セッション | ビジネスバリュー(Business Value Model)で定義されたビジネスバリューを生成したセッションの数。 |
| 訪問者ごとのバリューイベント | [!DNL (Value_Events/Visitors) by Visitor] | 訪問者 | ビジネスバリューを生成した各訪問者のセッションの平均数（ビジネスバリューモデルの定義に基づく）。 |
| 訪問者あたりの値 | [!DNL (Value/Visitors) by Visitor] | 訪問者 | 各訪問者が生み出した平均ビジネス価値（ドル）。 |
