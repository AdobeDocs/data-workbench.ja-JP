---
description: Data Workbenchの履歴プロファイルを使用して、設定、ハードウェア、その他の変更がパフォーマンス、安定性、サーバー容量に経時的に及ぼす影響を確認します。
title: Data Workbench の履歴ワークスペース
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Data Workbench の履歴ワークスペース{#data-workbench-historic-workspace}

Data Workbenchの履歴プロファイルを使用して、設定、ハードウェア、その他の変更がパフォーマンス、安定性、サーバー容量に経時的に及ぼす影響を確認します。

履歴プロファイルには、プロファイルベースの[プロファイルパフォーマンス](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d)データセットと、**[!UICONTROL Performance]**&#x200B;タブにあるサーバーベースの[サーバーパフォーマンス](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09)データセットが含まれます。 これらは、Data Workbenchサーバーのパフォーマンスに関する過去の観点で表示される、最も一般的に使用されるデータセットです。 また、「**[!UICONTROL Up Time]**」タブを選択すると、[コンポーネント](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)と[処理モード](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)を表示できます。

![](assets/Historic_Performance.png)

また、「**[!UICONTROL Up Time]**」タブを選択すると、[コンポーネント](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)と[処理モード](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)を表示できます。

Data Workbenchの履歴プロファイルで使用されるディメンションに関する追加のリファレンス情報については、 Insight履歴プロファイルの[Dimensionを参照してください。](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## プロファイルパフォーマンスワークスペース{#section-184a86f9de054970bf68515bb9dea85d}

このデータセットには、Data Workbenchの監視に関連する次の指標が含まれます。

* Fast Input MegaBytes per Minute：初回ログ処理時に重いデータ入力を表示するメトリック。
* Fast Merge MegaBytes per Minute：変換を表示するメトリック。

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>プロファイルの実際のパフォーマンス評価をおこなうには、カレンダー時間を経過するのではなく、率を調べます。 この率は、10分ごとにポーリング間の変更値として測定されます。

## サーバーパフォーマンスワークスペース{#section-5dad5870384b40e094d50173fcd90a09}

このデータセットは、含まれるプロファイルの範囲を超えたサーバー指標を監視し、data workbenchの監視に関連する次のサーバー指標を含みます。

* 「推定スイープ（分）」(Estimated Sweep Minutes) — クエリ解決の推定時間。
* ポーリング待ち時間のミリ秒 — 各コンポーネントのサービスの完全なサイクルに要する時間を測定することで、ソフトウェアのビジー状態を示すインジケータ。

![](assets/Historic_Server_Performance.png)

## コンポーネントワークスペース{#section-5be7223abb384784bafe7b37c764ea66}

このデータセットは、「アップタイム」タブにあります。

![](assets/Up_Time.png)

コンポーネントデータセットには、コンポーネントの正常性に関して次の2つの側面が含まれます。

* 通信指標 — Data Workbenchサーバーのプロセスは応答しましたか。
* すべてのコンポーネント指標 — 詳細なステータスページの上部に、Data Workbenchサーバープロセス内でホストがサービスしているコンポーネントのリストが表示されます。 エラー状態のコンポーネントがある場合は、そのコンポーネントが「エラーのコンポーネント」(Components in Error)テーブルに表示されます。

![](assets/Up_Time_components.png)

## 処理モードのワークスペース{#section-3e1dedb9474e4b4ba513240943e76817}

このワークスペースは、「アップタイム」タブにあります。 このワークスペースでは、高速入力、高速結合およびリアルタイムモードで取得される時間を確認できます。

![](assets/Up_Time_Processing_mode.png)

このデータセットは、

* 曜日（例えば、火曜日と水曜日の高速入力レート）
* 時刻（1日のうち何パーセントが高速入力モードですか？）
