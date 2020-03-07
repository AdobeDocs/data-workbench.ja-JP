---
description: Insightサーバーは、デフォルトで、ポート80（HTTPの場合）と443（HTTPSの場合）をリッスンします。
solution: Insight
title: ポート設定の確認
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ポート設定の確認{#checking-the-port-settings}

Insightサーバーは、デフォルトで、ポート80（HTTPの場合）と443（HTTPSの場合）をリッスンします。

これらのポートが、をインストールしたマシン上の別のプロセスによって既に割り当てられている場合は、次 [!DNL Insight Server]の手順に従ってポート割り当てを [!DNL Insight Server’s] 変更します。

**ポートの割り当てを変更するには**

1. インストールしたデ [!DNL Components] ィレクトリ内のフォルダに移動しま [!DNL Insight Server]す。

   例：[!DNL C:\Adobe\Server\Components]

1. ファイルをメモ [!DNL Communications.cfg] 帳などのテキストエディターで開きます。
1. 次に示すように、ポートとSSLポートのエントリを見つけます。

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

1. これらのポートが使用したくない場合は、 [!DNL Insight Server] ポートの割り当てを変更し、ファイルを保存して閉じます。
