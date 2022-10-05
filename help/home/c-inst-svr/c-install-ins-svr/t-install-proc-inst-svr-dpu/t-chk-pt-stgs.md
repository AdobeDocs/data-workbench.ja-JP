---
description: デフォルトでは、Insight サーバーは、ポート 80（HTTP の場合）および 443（HTTPS の場合）をリッスンします。
title: ポート設定の確認
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# ポート設定の確認{#checking-the-port-settings}

{{eol}}

デフォルトでは、Insight サーバーは、ポート 80（HTTP の場合）および 443（HTTPS の場合）をリッスンします。

これらのポートが、をインストールしたマシン上の別のプロセスによって既に割り当てられている場合 [!DNL Insight Server]、次の手順を使用して、 [!DNL Insight Server’s] ポートの割り当て。

**ポートの割り当てを変更するには**

1. 次に移動： [!DNL Components] をインストールしたディレクトリ内のフォルダー [!DNL Insight Server].

   例：[!DNL C:\Adobe\Server\Components]

1. を開きます。 [!DNL Communications.cfg] ファイルをメモ帳などのテキストエディターで作成します。
1. 次に示すように、ポートと SSL ポートのエントリを見つけます。

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. これらが必要なポートでない場合 [!DNL Insight Server] 使用するには、ポートの割り当てを変更し、ファイルを保存して閉じます。
