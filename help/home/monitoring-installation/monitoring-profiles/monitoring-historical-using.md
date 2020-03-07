---
description: Data Workbenchの履歴プロファイルを使用して、設定、ハードウェア、その他の変更がパフォーマンス、安定性、サーバー容量に長期的な影響を与える方法を確認します。
solution: Analytics
title: Data Workbenchの履歴ワークスペース
topic: Data workbench
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbenchの履歴ワークスペース{#data-workbench-historic-workspace}

Data Workbenchの履歴プロファイルを使用して、設定、ハードウェア、その他の変更がパフォーマンス、安定性、サーバー容量に長期的な影響を与える方法を確認します。

履歴プロファイルには、タブの下に、プロファイルベースの [Profile Performance](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) （プロファイルパフォーマンス）データセットと、サーバーベースの [Server Performance](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) （サーバーパフォーマンス）データセットが含 **[!UICONTROL Performance]** まれます。 これらは、Data Workbenchサーバーのパフォーマンスに関する過去の観点から見た、最も一般的に使用されるデータセットです。 また、タブを選択して、コンポーネ [ント](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) / [処理モード](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) を表示で **[!UICONTROL Up Time]** きます。

![](assets/Historic_Performance.png)

また、タブを選択して、コンポーネ [ント](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) / [処理モード](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) を表示で **[!UICONTROL Up Time]** きます。

Data Workbenchの履歴プロファイルで使用されるディメンションに関するその他の参照情報については、Insightの履歴プロファ [イルのディメンションを参照してください。](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## プロファイルパフォーマンスワークスペース {#section-184a86f9de054970bf68515bb9dea85d}

このデータセットには、Data Workbenchの監視に関連する次の指標が含まれています。

* Fast Input MegaBytes/Minute — 初期ログ処理時に大量のデータ入力が表示される指標。
* Fast Merge MegaBytes per Minute — 指標に変換が表示されています。

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>プロファイルの実際のパフォーマンス評価を行うには、カレンダーの経過時間ではなくレートを調べます。 レートは、10分ごとのポーリング間の変更値として測定されます。

## サーバーパフォーマンスワークスペース {#section-5dad5870384b40e094d50173fcd90a09}

このデータセットは、含まれるプロファイルの範囲を超えるサーバー指標を監視し、Data Workbenchでの監視用に次の関連するサーバー指標を含みます。

* 推定スイープ時間（分） — クエリの解決の推定時間。
* ポーリング待ち時間ミリ秒 — ソフトウェアがどの程度ビジー状態かを示す指標。各コンポーネントの完全なサイクルを通過するまでの時間を測定します。

![](assets/Historic_Server_Performance.png)

## コンポーネントワークスペース {#section-5be7223abb384784bafe7b37c764ea66}

このデータセットは、「アップタイム」タブにあります。

![](assets/Up_Time.png)

コンポーネントデータセットには、コンポーネントの正常性に関する2つの側面が含まれています。

* 通信指標 — Data Workbenchサーバーのプロセスが応答したか。
* すべてのコンポーネント指標 — 「詳細なステータス」ページの上部には、Data Workbenchサーバーが処理するホストのサービス対象のコンポーネントのリストが表示されます。 エラー状態のコンポーネントがある場合は、「エラーのコンポーネント」(Components in Error)テーブルの下に表示されます。

![](assets/Up_Time_components.png)

## 処理モードのワークスペース {#section-3e1dedb9474e4b4ba513240943e76817}

このワークスペースは、「アップタイム」タブの下にあります。 このワークスペースでは、高速入力、高速結合およびリアルタイムモードでの時間を確認できます。

![](assets/Up_Time_Processing_mode.png)

このデータセットは、

* 曜日（例えば、火曜日と水曜日の速い入力レート）、
* 時間帯（Fast Inputモードでは、1日の何パーセントが表示されますか）

