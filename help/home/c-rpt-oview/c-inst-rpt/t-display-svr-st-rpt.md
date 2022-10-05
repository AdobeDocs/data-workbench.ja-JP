---
description: Data Workbench の詳細なステータスインターフェイスは、Data WorkbenchサーバーのクライアントであるData Workbenchサーバーとレポートサーバーのコンピューターに関するエラーやその他の問題のトラブルシューティングに役立ちます。
title: レポートサーバーのステータスの表示
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# レポートサーバーのステータスの表示{#displaying-report-server-status}

{{eol}}

Data Workbench の詳細なステータスインターフェイスは、Data WorkbenchサーバーのクライアントであるData Workbenchサーバーとレポートサーバーのコンピューターに関するエラーやその他の問題のトラブルシューティングに役立ちます。

レポートのステータスを表示するには、 [!DNL Master Server Detailed Status] インターフェイスで、レポートステータスサーバーを [!DNL Servers] data workbench サーバーのベクトル [!DNL Communications.cfg] ファイル。 次の手順では、レポートステータスサーバーを [!DNL Communications.cfg] ファイル：

詳しくは、 [!DNL Detailed Status] インターフェイスについては、『管理インターフェイス』の章を参照してください。 *Data Workbenchユーザーガイド*.

**を追加するには、以下を実行します。[!DNL Report Status Server]**

1. Data Workbench サーバー (InsightServer64.exe) をインストールしたディレクトリ内の Components フォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Components]
1. 開く [!DNL Communications.cfg] をメモ帳などのテキストエディターで使用する。
1. を [!DNL Servers] ベクトルを参照し、次のファイルフラグメントでハイライト表示されているように、このベクトルにレポートステータスサーバーを追加します。

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

1. 次の項目数を更新 [!DNL Servers] ベクトル（つまり、前の手順でファイルフラグメントでハイライト表示された項目の値を 1 ずつ増やします）。
1. ファイルを保存します。
