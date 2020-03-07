---
description: 詳細テーブルから TargetBulkUpload.exe ファイルを使用して、Data Workbench を Adobe Target へエクスポートします。
title: Adobe Targetへの書き出し
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adobe Targetへの書き出し{#export-to-adobe-target}

詳細テーブルから TargetBulkUpload.exe ファイルを使用して、Data Workbench を Adobe Target へエクスポートします。

Data Workbenchでは、ファイルを書き出して、統合されたAdobe Experience Cloudの一部としてAdobe Targetと統合できます。

**[!DNL TargetBulkUpload]** ファイルは、サーバーインストールファイルにある *Server\Scripts* フォルダーにあります。実行可能ファイルには再試行ロジックおよびパフォーマンスを最適化する追加ロジックがあります。

アップロードスクリプ `TargetBulkUpload.cfg` トを実行する前に、フ *ァイルを変更し、Server* /Admin/Exportフォルダーに移動できます。 例えば、「最大タイムアウト間隔」を720分（デフォルト）に設定して、指定した期間が経過した後にアップロードをタイムアウトにすることができます。

**動作の仕組み**

データがTargetに正常に送信された後、アップロードのステータスは継続的に監視されます。 アップロードが成功すると、成功メッセージが記録されます。 アップロードが失敗した場合や保留中の場合は、監視が続行されます。 ファイル内でタイムアウトの間隔を設定で `TargetBulkUpload.cfg` きます。 アップロードがTargetで停止した場合は、メッセージがログに記録され、ステータスを監視できます。

トリガーされたエクスポートのトレースには、次の2つのログファイルが生成されま [!DNL /server/Trace/]す。

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

ファイ `targetbulkuploadexportname.log` ルには、複数のバッチのすべてのレコード、対象となるエッジサーバー、およびステータス（成功、失敗、プロファイルが見つからない、ステータスが不明、停止）の詳細なステータスが含まれます。 バッチがスタックしていることが検出された場合、そのバッチは処理されません。 スタックバッチURLを使用して、ステータスを追跡できます。 ファイルの次のデータ例を参照してく `targetbulkuploadexportname.log.completed` ださい。

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

stuckステータス値は、アップロードが成功したか失敗したかに関係なく、スタックバッチの合計サイズで増加します。 また、合計行数の値も、同じ数のスタックバッチサイズだけ増分されます。

>[!NOTE]
>
>Previously, DWB data was exported using the [!DNL ExportIntegration.exe]. 現在は、MMP、CRS および S/FTP エクスポートのみがこの実行可能ファイルで使用されています。Adobe Target integration now uses the [!DNL TargetBulkUpload.exe] in Data Workbench.

