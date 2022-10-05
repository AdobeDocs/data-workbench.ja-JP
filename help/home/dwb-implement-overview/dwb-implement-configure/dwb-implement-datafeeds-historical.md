---
description: 履歴データフィードの検証と設定に必要な最小手順に関するクイックガイドです。
title: 履歴データフィードの検証
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
exl-id: 5a5e2cca-2fab-48a0-b58d-a8c46114b9a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 5%

---

# 履歴データフィードの検証{#validating-historical-data-feeds}

{{eol}}

履歴データフィードの検証と設定に必要な最小手順に関するクイックガイドです。

## データフィードの一貫性を確認するための検証手順 {#section-777b2c627a354627a02feb9461e23038}

1. ログイン先 *無歯歯* (https://oasis.omniture.com/drteeth/)
1. SiteCatalyst管理/データフィード定義（新規）に移動します。
1. サーバーの場所にジャンプします ( 例： ダラス、ロンドン…) 組織の所在地に応じて異なります。
1. RSID を入力し、フィードタイプ Insight を選択して、 *検索*.

   ![](assets/dwb_impl_historical.png)

1. クライアントの実際のフィード名を特定します。
1. アクションセクションの履歴をクリックします。 ![](assets/dwb_impl_historical1.png)

   ステータスフィールドでエラーを確認し、一部のフィードがエラー状態の場合は、フィードを選択して再処理をクリックします。 複数のリクエストでエラーが発生した場合は、に電子メールを送信します。 *`dataworkbench@adobe.com`* 再処理するフィード ID とレポートスイートの詳細を含む

1. 検証後は、NAS の場所の raw フォルダ内のログを確認します。
