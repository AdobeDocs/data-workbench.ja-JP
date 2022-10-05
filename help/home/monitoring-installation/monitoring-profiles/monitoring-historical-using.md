---
description: Data Workbench の履歴プロファイルを使用して、設定、ハードウェア、その他の変更が、パフォーマンス、安定性、サーバー容量に時間の経過と共にどのように影響するかを確認します。
title: Data Workbench の履歴ワークスペース
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Data Workbench の履歴ワークスペース{#data-workbench-historic-workspace}

{{eol}}

Data Workbench の履歴プロファイルを使用して、設定、ハードウェア、その他の変更が、パフォーマンス、安定性、サーバー容量に時間の経過と共にどのように影響するかを確認します。

履歴プロファイルには、プロファイルベースの [プロファイル効果](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) データセットとサーバーベース [サーバーのパフォーマンス](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) データセットを **[!UICONTROL Performance]** タブをクリックします。 これらは、Data Workbench サーバーのパフォーマンスに関する過去の観点で表示された、最も一般的に使用されるデータセットです。 また、 [コンポーネント](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) および [処理モード](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) 選択 **[!UICONTROL Up Time]** タブをクリックします。

![](assets/Historic_Performance.png)

また、 [コンポーネント](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) および [処理モード](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) 選択 **[!UICONTROL Up Time]** タブをクリックします。

Data Workbench の履歴プロファイルで使用されるディメンションに関する追加のリファレンス情報については、 [Dimension（Insight 履歴プロファイル内）](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## プロファイルパフォーマンスワークスペース {#section-184a86f9de054970bf68515bb9dea85d}

このデータセットには、Data Workbench の監視に関連する次の指標が含まれています。

* Fast Input MegaBytes/Minute — 初回ログ処理時に大量のデータ入力を表示するメトリック。
* Fast Merge MegaBytes per Minute — 変換を表示するメトリック。

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>プロファイルの実際のパフォーマンス評価を行うには、カレンダーの経過時間ではなく率を調べます。 レートは、10 分ごとのポーリング間の変更値として測定されます。

## サーバーパフォーマンスワークスペース {#section-5dad5870384b40e094d50173fcd90a09}

このデータセットは、含まれるプロファイルの範囲を超えるサーバー指標を監視し、data workbench の監視に関連する次のサーバー指標を含みます。

* 「推定スイープ時間（分）」(Estimated Sweep Minutes) — クエリ解決時間の推定値。
* ポーリング待ち時間のミリ秒 — 各コンポーネントのサービスのフルサイクルを経るまでの時間を測定することで、ソフトウェアのビジー状態を示すインジケーター。

![](assets/Historic_Server_Performance.png)

## コンポーネントワークスペース {#section-5be7223abb384784bafe7b37c764ea66}

このデータセットは、「アップタイム」タブにあります。

![](assets/Up_Time.png)

コンポーネントデータセットには、コンポーネントの正常性に関して次の 2 つの側面が含まれます。

* 通信指標 — Data Workbench サーバープロセスが応答したか。
* 「すべてのコンポーネント」指標 — 詳細なステータスページの上部に、Data Workbench サーバープロセス内でホストがサービスを提供しているコンポーネントのリストが表示されます。 エラー状態のコンポーネントがある場合は、そのコンポーネントが「エラーのコンポーネント」(Components in Error) テーブルに表示されます。

![](assets/Up_Time_components.png)

## 処理モードのワークスペース {#section-3e1dedb9474e4b4ba513240943e76817}

このワークスペースは、「アップタイム」タブにあります。 このワークスペースでは、高速入力、高速結合およびリアルタイムモードで取得される時間を確認できます。

![](assets/Up_Time_Processing_mode.png)

このデータセットは、次のデータの読み込みを識別するなど、重要なサーバー読み込み特性を提供します。

* 曜日（例えば、火曜日と水曜日の速い入力率）
* 時間帯（高速入力モードの場合、1 日のうち何パーセントですか？）
