---
description: 指定した設定で Insight サーバーに接続できない場合は、サーバーマネージャーに赤いノードが表示されます。
title: 接続のトラブルシューティング
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
exl-id: 7938d4d6-e1ab-46d9-9ccb-cf79677c5688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 34%

---

# 接続のトラブルシューティング{#connection-troubleshooting}

{{eol}}

指定した設定で Insight サーバーに接続できない場合は、サーバーマネージャーに赤いノードが表示されます。

これは、例えば、接続の設定が間違っている場合や、 [!DNL Insight Server’s] ステータス。

**Insight が接続を確立できない理由を判断するには、以下を実行します。**

1. 赤いサーバーノードを右クリックし、 **[!UICONTROL Detailed Status]**.
1. 内 [!DNL Detailed Status] インタフェース、 **[!UICONTROL Network Connections]** 番号付き項目を展開します。 この [!DNL Status] パラメーターは、Insight が接続を確立できない理由に関する情報を提供します。

   * 500 番台のステータスコードは設定エラーを示します。
   * ステータスコード 403 は、通常、サーバーのステータスを表示する権限がないことを示します。

その他のステータス情報は、[!DNL insight.log] ファイルで参照できます。このログファイルは、 [!DNL Trace] Insight をインストールしたディレクトリ内のフォルダー。 ファイルを表示するには、メモ帳などのテキストエディターでファイルを開きます。

[!DNL insight.log] ファイル内の情報を理解するために支援が必要な場合は、まずシステム管理者に問い合わせてください。さらにサポートが必要な場合は、Adobeカスタマーケアにお問い合わせください。
