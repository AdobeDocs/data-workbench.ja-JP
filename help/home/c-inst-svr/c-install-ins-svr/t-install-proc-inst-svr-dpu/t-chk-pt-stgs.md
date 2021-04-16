---
description: Insightサーバーは、デフォルトで、ポート80（HTTPの場合）および443（HTTPSの場合）をリッスンします。
title: ポート設定の確認
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# ポート設定の確認{#checking-the-port-settings}

Insightサーバーは、デフォルトで、ポート80（HTTPの場合）および443（HTTPSの場合）をリッスンします。

[!DNL Insight Server]をインストールしたマシン上の別のプロセスによって、これらのポートが既に割り当てられている場合は、次の手順に従って[!DNL Insight Server’s]ポートの割り当てを変更します。

**ポートの割り当てを変更するには**

1. [!DNL Insight Server]をインストールしたディレクトリの[!DNL Components]フォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Components]

1. [!DNL Communications.cfg]ファイルをメモ帳などのテキストエディターで開きます。
1. 次に示すように、PortとSSL Portのエントリを探します。

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

1. [!DNL Insight Server]で使用したくないポートがある場合は、ポートの割り当てを変更し、ファイルを保存して閉じます。
