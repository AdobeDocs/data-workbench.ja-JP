---
description: 詳細テーブルから TargetBulkUpload.exe ファイルを使用して、Data Workbench を Adobe Target へエクスポートします。
title: Adobe Target へのエクスポート
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
exl-id: 41e885bb-182a-4983-98e8-65eec1da9fe9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 23%

---

# Adobe Target へのエクスポート{#export-to-adobe-target}

{{eol}}

詳細テーブルから TargetBulkUpload.exe ファイルを使用して、Data Workbench を Adobe Target へエクスポートします。

Data Workbenchを使用すると、統合Adobe Experience Cloudの一部としてAdobe Targetと統合するためのファイルを書き出すことができます。

**[!DNL TargetBulkUpload]** ファイルは、サーバーインストールファイルにある *Server\Scripts* フォルダーにあります。実行可能ファイルには再試行ロジックおよびパフォーマンスを最適化する追加ロジックがあります。

次の項目を変更できます。 `TargetBulkUpload.cfg` ファイルを次の場所に移動します。 *サーバー/管理者/書き出し* フォルダーに保存してから、アップロードスクリプトを実行します。 例えば、最大タイムアウト間隔を 720 分（デフォルト）に設定して、指定した時間が経過した後にアップロードをタイムアウトすることができます。

**仕組み**

データが Target に正常に送信された後、アップロードのステータスは継続的に監視されます。 アップロードが成功すると、成功メッセージが記録されます。 アップロードに失敗した場合や保留中の場合は、監視は続行されます。 タイムアウト間隔は、 `TargetBulkUpload.cfg` ファイル。 Target でアップロードが停止した場合は、メッセージがログに記録され、ステータスを監視できます。

トリガーされたエクスポートのトレースでは、次の場所で 2 つのログファイルが生成されます。 [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

この `targetbulkuploadexportname.log` ファイルには、複数のバッチのすべてのレコード、対象となるエッジサーバー、ステータス（成功、失敗、プロファイルが見つからない、ステータスが不明、停止）に関する詳細なステータスが含まれています。 バッチが停止していることが見つかった場合、バッチはそれ以上処理されません。 停止したバッチ URL を使用してステータスを追跡できます。 次の `targetbulkuploadexportname.log.completed` ファイル：

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

stuck ステータス値は、アップロードが成功したか失敗した回数に関係なく、stuck batch の合計サイズに従って増分されます。 合計行数の値も、停止したバッチサイズの同数だけ増加します。

>[!NOTE]
>
>以前は、DWB データは [!DNL ExportIntegration.exe]. 現在は、MMP、CRS および S/FTP エクスポートのみがこの実行可能ファイルで使用されています。Adobe Target統合は、 [!DNL TargetBulkUpload.exe] Data Workbench
