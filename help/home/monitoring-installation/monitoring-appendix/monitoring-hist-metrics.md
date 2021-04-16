---
description: 次のリストは、Data Workbenchの履歴監視プロファイルに含まれる指標とその派生方法です。
title: Data Workbench 履歴監視プロファイルの指標
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Data Workbench 履歴監視プロファイルの指標{#metrics-in-the-data-workbench-historical-monitoring-profile}

次のリストは、Data Workbenchの履歴監視プロファイルに含まれる指標とその派生方法です。

| **アラートの重要度** | 各PingのAlert Criticalディメンションの合計。 |
|---|---|
| **アラートのダウン** | 各Pingのアラートダウンディメンションの合計。 |
| **警告** | 各Pingのアラート警告ディメンションの合計。 |
| **すべてのコンポーネント** | 「コンポーネントチェックの成功」が「1」で、ping指標に100を乗じた値であるpingの数。 |
| **遅延時間（分）** | この指標は、各Pingの基準遅延時間の合計をPing指標で割った値です。 |
| **ブロック** | 各ブロックの1つの合計。 |
| **すべてブロック** | すべてのブロック。 |
| **容量全体** | 容量サイズ指標に2を加え、容量行指標を3で割った値。 |
| **容量行** | 各PingのCapacity Row Percentageディメンションの合計をPing指標で割った値。 |
| **容量サイズ** | 各PingのCapacity Size Percentageディメンションの合計をPing指標で割った値。 |
| **通信** | Quick Check Successが「1」に一致するpingの数をPing指標で割った値。 |
| **詳細チェック秒数** | pingタイプが「サーバー」である各Pingの詳細なチェック秒ディメンションの合計を、Ping指標で割った値です。 |
| **DimensionGigaBytes** | 各PingのDimensionギガバイトの合計をPing指標で割った値。 |
| **ディスク「x」** | ディスク指標は、各Pingのディスク使用率の合計をPing指標で割って計算されます。 |
| **推定スイープ時間（分）** | これは、各Pingの推定スイープデカスコンドの合計をPing指標で割った値です。このPing指標では、推定スイープデカスコンドが0より大きく、すべて6で割られます。 |
| **Fast Input MB/分** | 各PingのFast Input MegaBytes/Minuteの合計をPingの数で割った値（Fast Input MegaBytes/Minuteが0より大きい場合）。 |
| **Fast Input Mode** | 処理モードディメンションが「Fast input」をPingで割った値と等しいping。 |
| **Fast Merge MegaBytes/Minute** | 各PingのFast Merge MB/分の合計をPing指標で割った値。 |
| **高速結合モード** | 「処理モード」が「高速結合」をPing指標で割った値と等しいping。 |
| **Field GigaBytes** | 各Pingのフィールドギガバイトディメンションの合計をPing指標で割った値。 |
| **Load** | 各Pingの読み込み平均ディメンションの合計をPing指標で割った値。 |
| **ログの読み取り** | 各PingのLog Reading Processingディメンションの合計をPing指標で割った値で、すべて10で割った値です。 |
| **メモリページ** | 各Pingのメモリページファイルの割合の合計をPing指標で割った値。 |
| **メモリ物理** | 各PingのMemory Physical Percentageディメンションの合計をPing指標で割った値。 |
| **メモリクエリ** | 各Pingのメモリクエリの割合の合計をPing指標で割った値。 |
| **メモリ合計GB** | 各PingのMemory Physical MegaBytes Totalディメンションの合計をPing指標で割った値。 |
| **ネットワーク接続** | これは、各Pingのネットワーク接続の合計をPing指標で割った値です。 |
| **Ping x Capacity Overal** | ping指標に「容量全体」指標を乗算した値。 |
| **ポーリング待ち時間ミリ秒** | 各Pingのポーリング待ち時間のセンチ秒ディメンションの合計をPing指標で割った値ですべて10を掛けた値です。 |
| **クエリ実行中** | Estimated Sweep Dekasecondsが「0」を超える各Pingに対して1を合計し、Ping Typeが「server」に等しいPing指標で割った値です。 |
| **クイックチェック秒数** | 各Pingのクイックチェック秒数の合計（Ping Typeが「サーバー」である場合）をPing指標で割った値。 |
| **出力行** | 各pingの出力行ディメンションの合計をping指標で割った値に100000を乗算した値。 |
| **リアルタイムモード** | 処理モードディメンションが「リアルタイム」で、ping指標を割った値ですべて100を掛けた値。 |
| **再処理モード** | 100から、処理モードが「リアルタイム」をPing指標で割った100を引いたpingの数を引いた値です。 |
| **Stalled** | Insight [プロファイルステータス](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)プロファイルの処理停止ディメンションの合計です。 |
| **一時DB** | 各Pingの一時DB領域の割合の合計をPing指標で割った値。 |
| **変換** | 各Pingの変換の割合の合計をPing指標で割り、すべて10で割った値です。 |
