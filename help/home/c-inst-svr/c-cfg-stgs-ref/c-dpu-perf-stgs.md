---
description: DPUパフォーマンスを調整する手順です。
solution: Analytics
title: DPU パフォーマンスの設定
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---


# DPU パフォーマンスの設定{#dpu-performance-settings}

DPUパフォーマンスを調整する手順です。

* [!DNL Insight Server] installation directory*\Components\DPU.cfgファイルで、次のパラメーターを指定します。

| パラメーター | 説明 |
|---|---|
| 実行バッチ数 | これはチューニングパラメータです。 デフォルト値は 65536 です。任意に小さい実行バッチ数を指定できます。 この値を変更する前に、Adobeにお問い合わせください。 |
| 実行バッチ | これはチューニングパラメータです。 デフォルト値は 128 です。この値を変更する前に、Adobeにお問い合わせください。 |
| 実行時間 | これはチューニングパラメータです。 デフォルト値は0.100です。この値を変更する前に、Adobeにお問い合わせください。 |
| エラー時のフィールドダンプ | このパラメーターはtrueまたはfalseに設定できます。 trueに設定した場合、実行エンジンのエラーが発生した場合は常に、 [!DNL Insight Server] トレースディレクトリ [!DNL Field Dump number.txt] にという名前のファイルが作成されます。 &lt; [!DNL Field Dump][!DNL number]> [!DNL .txt] はトラブルシューティングに役立ちます。 |
| プロファイルパス | すべてのプロファイルのファイルを保存する場所。 デフォルトの場所はプロファイルです。 |
| クエリメモリ制限 | クエリ結果を保存するために [!DNL Insight Server] 予約するメモリ量（バイト）。 デフォルト値は10000000(100MB)です。 クエリ結果の領域が必要な場合（例えば、同時に使用できるユーザー数を増やす場合）は、設定を増やすことができますが、メモリの負荷を引き続き確認する必要があり [!DNL Insight Server’s] ます。 |
| 状態パス | システム状態ファイルの場所。 デフォルトの場所は「状態」です。 |
| スレッド | 複数のプロセッサーを搭載した [!DNL Insight Server] マシンのパフォーマンス調整パラメータ。 一般に、nコアシステムの場合は、この値をnに設定する必要があります。デフォルト値は1です。 |
| User Path | 許可されたユーザーのファイルの場所。 デフォルトの場所はUsers\です。 |

