---
description: Data Workbench v6.5 にアップグレードするには、この手順に従います。
title: 6.4 から 6.5 へのアップグレード
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 6.4 から 6.5 へのアップグレード{#upgrading-to}

Data Workbench v6.5 にアップグレードするには、この手順に従います。

## アップグレード要件と推奨事項 {#section-8704a9ac358246cd81233dd0982d534f}

Data Workbench 6.5 にアップグレードする際は、以下の要件および推奨事項に従ってください。

* Changes in the **[!DNL Components for Processing Servers\Communications.cfg]** file require you to update this file for the DWB 6.5 release. *SourceListServer*、*SegmentExportServer*、*NormalizeServer* の各エントリは削除されました（DPU で&#x200B;*ソースリスト*、*セグメントの書き出し*、または&#x200B;*サーバーの正規化*&#x200B;を動作させないでください）。

* クロス集計の弦、相関行列、関連付けの弦、傾向スコア、および最適なアトリビューションの視覚化が、マルチパス視覚化になりました。

   1 つのワークスペースにマルチパス視覚化が複数含まれている場合、レポートサーバーは、デフォルトでは次のエラーを出力してレポート生成に失敗します。

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   このエラーを避けるには、[!DNL ReportServer.cfg] ファイルを更新するか、既存のファイルの *Reporting* セクションに次の行を追加します。

   ```
   Max Multipass Per Slice = int: n
   ```

   ただし、&quot;n&quot; の箇所には、1 つのワークスペースについてレポートサーバーでサポートされるマルチパス視覚化の最大数を入力してください。

