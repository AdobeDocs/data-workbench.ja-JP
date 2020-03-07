---
description: Data Workbenchの「詳細なステータス」インターフェイスは、Data WorkbenchサーバーのクライアントであるData Workbenchサーバーおよびレポートサーバーのコンピューターに関するエラーやその他の問題のトラブルシューティングに役立ちます。
solution: Analytics
title: レポートサーバーのステータスの表示
topic: Data workbench
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# レポートサーバーのステータスの表示{#displaying-report-server-status}

Data Workbenchの「詳細なステータス」インターフェイスは、Data WorkbenchサーバーのクライアントであるData Workbenchサーバーおよびレポートサーバーのコンピューターに関するエラーやその他の問題のトラブルシューティングに役立ちます。

インターフェイスにレポートのステータスを表示す [!DNL Master Server Detailed Status] るには、Data Workbenchサーバーのファイル内のベクトルにレポートステータスサーバー [!DNL Servers] を追加する必要があ [!DNL Communications.cfg] ります。 次の手順では、レポートステータスサーバーをファイルに追加する方法を説明 [!DNL Communications.cfg] します。

For more information about [!DNL Detailed Status] interfaces, see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

**を[!DNL Report Status Server]**

1. Data Workbenchサーバー(InsightServer64.exe)をインストールしたディレクトリ内のComponentsフォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Components]
1. メモ帳 [!DNL Communications.cfg] などのテキストエディターで開きます。
1. ベクトルを探 [!DNL Servers] し、次のファイルフラグメントで強調表示されているように、レポートステータスサーバーをこのベクトルに追加します。

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. 前の手順のファイルフラグメ [!DNL Servers] ントでハイライト表示されているように、ベクトルの項目数を更新（つまり、項目の値を1ずつ増分）します。
1. ファイルを保存します。
