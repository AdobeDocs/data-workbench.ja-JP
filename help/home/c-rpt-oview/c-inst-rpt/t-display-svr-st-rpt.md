---
description: data workbenchの詳細なステータスインターフェイスは、Data WorkbenchサーバーのクライアントであるData Workbenchサーバーとレポートサーバーのコンピューターに関するエラーや他の問題のトラブルシューティングに役立ちます。
title: レポートサーバーのステータスの表示
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# レポートサーバーのステータスの表示{#displaying-report-server-status}

data workbenchの詳細なステータスインターフェイスは、Data WorkbenchサーバーのクライアントであるData Workbenchサーバーとレポートサーバーのコンピューターに関するエラーや他の問題のトラブルシューティングに役立ちます。

[!DNL Master Server Detailed Status]インターフェイスでレポートのステータスを表示するには、data workbenchサーバーの[!DNL Communications.cfg]ファイル内の[!DNL Servers]ベクトルにレポートステータスサーバーを追加する必要があります。 次の手順では、[!DNL Communications.cfg]ファイルにレポートステータスサーバーを追加する方法を説明します。

[!DNL Detailed Status]インターフェイスの詳細については、『*Data Workbenchユーザーガイド*』の「管理インターフェイス」という章を参照してください。

**を追加するには[!DNL Report Status Server]**

1. Data Workbenchサーバー(InsightServer64.exe)をインストールしたディレクトリ内のComponentsフォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Components]
1. メモ帳などのテキストエディターで[!DNL Communications.cfg]を開きます。
1. [!DNL Servers]ベクトルを探し、次のファイルフラグメントで強調表示されているように、このベクトルにレポートステータスサーバーを追加します。

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

1. 前の手順のファイルフラグメントで強調表示されているように、[!DNL Servers]ベクトルの項目数を更新します（つまり、項目の値を1ずつ増分します）。
1. ファイルを保存します。
