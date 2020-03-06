---
description: 履歴データフィードの検証と設定に必要な最小手順のクイックガイドです。
title: 履歴データフィードの検証
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 履歴データフィードの検証{#validating-historical-data-feeds}

履歴データフィードの検証と設定に必要な最小手順のクイックガイドです。

## データフィードの一貫性を保つための検証手順 {#section-777b2c627a354627a02feb9461e23038}

1. drteathにログ *イン* (https://oasis.omniture.com/drteeth/)
1. SiteCatalyst管理者/データフィードの定義（新規）に移動します。
1. サーバーの場所に移動(例： ダラス、ロンドン…)組織の場所に応じて異なります。
1. RSIDを指定し、フィードのタイプ「Insight」を選択して、「検索」をクリ *ックしま*&#x200B;す。

   ![](assets/dwb_impl_historical.png)

1. クライアントの実際のフィード名を指定します。
1. 「アクション」セクションの「履歴」をクリックします。 ![](assets/dwb_impl_historical1.png)

   ステータスフィールドでエラーを確認し、一部のフィードがエラー状態の場合は、フィードを選択して「再処理」をクリックします。 複数のリクエストに対してエラーが発生した場合は、再処理のために、フィードIDとレ *`dataworkbench@adobe.com`* ポートスイートの詳細を記載した電子メールをに送信します。

1. 検証後は、NASの場所のrawフォルダ内のログを確認します。

