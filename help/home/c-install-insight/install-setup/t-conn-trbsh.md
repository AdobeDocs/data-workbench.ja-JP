---
description: 指定した設定を使用してInsightサーバーに接続できない場合は、サーバーマネージャーに赤いノードが表示されます。
title: 接続のトラブルシューティング
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 接続のトラブルシューティング{#connection-troubleshooting}

指定した設定を使用してInsightサーバーに接続できない場合は、サーバーマネージャーに赤いノードが表示されます。

This might occur, for example, if you configure the connection incorrectly or you do not have permission to view the [!DNL Insight Server’s] status.

**Insightが接続を確立できない理由を判断するには**

1. Right-click the red server node and click **[!UICONTROL Detailed Status]**.
1. インターフェイス [!DNL Detailed Status] で、番号付きの項 **[!UICONTROL Network Connections]** 目をクリックして展開します。 The [!DNL Status] parameter provides information about why Insight is not able to establish a connection:

   * 500 番台のステータスコードは設定エラーを示します。
   * ステータスコード 403 は、通常、サーバーのステータスを表示する権限がないことを示します。

その他のステータス情報は、[!DNL insight.log] ファイルで参照できます。This log file is located in the [!DNL Trace] folder in the directory where you installed Insight. ファイルを表示するには、メモ帳などのテキストエディターでファイルを開きます。

[!DNL insight.log] ファイル内の情報を理解するために支援が必要な場合は、まずシステム管理者に問い合わせてください。詳しくは、アドビカスタマーケアにお問い合わせください。
