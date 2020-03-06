---
description: Data Workbenchの履歴監視プロファイルに含まれる指標と、その派生方法を以下に示します。
solution: Analytics
title: Data Workbenchの履歴監視プロファイルの指標
topic: Data workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbenchの履歴監視プロファイルの指標{#metrics-in-the-data-workbench-historical-monitoring-profile}

Data Workbenchの履歴監視プロファイルに含まれる指標と、その派生方法を以下に示します。

| **重要なアラート** | 各Pingの警告の重大ディメンションの合計。 |
|---|---|
| **アラートのダウン** | 各PingのAlert Downディメンションの合計。 |
| **警告** | 各Pingのアラート警告ディメンションの合計。 |
| **すべてのコンポーネント** | コンポーネントチェックの成功が「1」に等しいpingの数を、ping指標に100を掛けた値です。 |
| **遅延時間（分）** | この指標は、各Pingの基準遅延時間（分）の合計をPing指標で割った値です。 |
| **ブロック** | 各ブロックの1つの合計。 |
| **すべてをブロック** | すべてのブロック。 |
| **全体的な容量** | 容量サイズ指標に2を加え、容量行指標を3で割った値。 |
| **容量行** | 各PingのCapacity Row Percentageディメンションの合計をPing指標で割った値。 |
| **容量サイズ** | 各PingのCapacity Size Percentageディメンションの合計をPing指標で割った値。 |
| **通信** | 「1」に一致するPingの数をPing指標で割った値。 |
| **詳細チェック秒数** | pingタイプが「サーバー」である各Pingの詳細なチェック秒数ディメンションの合計を、Ping指標で割った値です。 |
| **ディメンションGigaBytes** | 各Pingのディメンションのギガバイト数をPing指標で割った値。 |
| **ディスク「x」** | ディスク指標は、各Pingのディスク使用率の合計をPing指標で割って計算されます。 |
| **推定スイープ時間（分）** | これは、各Pingの推定スイープデケイ秒の合計を、Estimated Sweep Dekasecondsが0より大きいPing指標で割って、すべて6で割った値です。 |
| **Fast Input MB/分** | Fast Input MegaBytes/Minuteの合計が0より大きい場合、各PingのFast Input MegaBytes/Minuteの値をPingの数で割った値。 |
| **高速入力モード** | 処理モードディメンションが「Fast input」をPingで割った値と等しいping。 |
| **Fast Merge MegaBytes/Minute** | 各PingのFast Merge Megabits/分の合計をPing指標で割った値。 |
| **高速結合モード** | 「処理モード」が「高速結合」をPing指標で割った値になるping。 |
| **Field GigaBytes** | 各Pingのフィールドギガバイトディメンションの合計をPing指標で割った値。 |
| **Load** | 各Pingの読み込み平均ディメンションの合計をPing指標で割った値。 |
| **ログの読み取り** | 各Pingのログ読み取り処理ディメンションの合計をPing指標で割り、すべて10で割った値。 |
| **メモリページ** | 各Pingのメモリページファイルの割合の合計をPing指標で割った値。 |
| **メモリ物理** | 各Pingのメモリ物理割合ディメンションの合計をPing指標で割った値。 |
| **メモリクエリ** | 各Pingのメモリクエリの割合の合計をPing指標で割った値。 |
| **メモリ合計GB** | 各PingのMemory Physical MegaBytes Totalディメンションの合計をPing指標で割った値。 |
| **ネットワーク接続** | これは、各Pingのネットワーク接続の合計をPing指標で割った値です。 |
| **Ping x Capacity Overall** | ping指標に「Capacity Overall」指標を掛けた値。 |
| **ポーリング待ち時間ミリ秒** | 各Pingのポーリング待ち時間のセンチ秒数ディメンションの合計を、Ping指標で割った値で、すべて10を掛けた値です。 |
| **クエリの実行** | Estimated Sweep Dekasecondsが「0」を超える各Pingの合計が、Ping Typeが「server」に等しいPing指標で割られた値です。 |
| **クイックチェック秒数** | Pingタイプが「サーバー」に等しい各Pingのクイックチェック秒数をPing指標で割った値。 |
| **出力行** | 各pingの出力行ディメンションの合計をPing指標で割り、100000を掛けた値です。 |
| **リアルタイムモード** | 処理モードディメンションが「リアルタイム」に等しいpingの数を、ping指標で割った値ですべて100を掛けた値です。 |
| **再処理モード** | 100から、処理モードが「リアルタイム」をping指標で割ったpingの数を100で乗算した値を引いた値です。 |
| **停止** | Insight [Profile StatusプロファイルのProcessing Stalledディメンションの合計](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) 。 |
| **一時DB** | 各Pingの一時DB領域の割合の合計をPing指標で割った値。 |
| **変換** | 各Pingの変換率の合計をPing指標で割った値で、すべて10で割った値です。 |

