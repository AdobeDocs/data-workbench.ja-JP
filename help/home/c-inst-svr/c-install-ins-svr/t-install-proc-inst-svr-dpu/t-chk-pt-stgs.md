---
description: Insightサーバーは、デフォルトで、ポート80（HTTPの場合）および443（HTTPSの場合）をリッスンします。
solution: Analytics
title: ポート設定の確認
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---


# ポート設定の確認{#checking-the-port-settings}

Insightサーバーは、デフォルトで、ポート80（HTTPの場合）および443（HTTPSの場合）をリッスンします。

これらのポートが、をインストールしたマシン上の別のプロセスによって既に割り当てられている場合 [!DNL Insight Server]は、次の手順に従って、 [!DNL Insight Server’s] ポート割り当てを変更します。

**ポートの割り当てを変更するには**

1. インストールしたディレクトリ内の [!DNL Components] フォルダーに移動し [!DNL Insight Server]ます。

   例：[!DNL C:\Adobe\Server\Components]

1. メモ帳などのテキストエディターで [!DNL Communications.cfg] ファイルを開きます。
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

1. これらのポートが使用したくない場合は、ポートの割り当てを変更 [!DNL Insight Server] し、ファイルを保存して閉じます。
