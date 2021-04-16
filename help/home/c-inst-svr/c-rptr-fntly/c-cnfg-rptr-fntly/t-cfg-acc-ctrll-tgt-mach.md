---
description: Insight Server Replication Serviceを実行するターゲットインサイトサーバーコンピューターは、このリピーターサーバー上のログファイルを読み取れる必要があります。
title: ターゲットマシンのアクセス制御の設定
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# ターゲットマシンのアクセス制御の設定{#configuring-access-control-for-target-machines}

Insight Server Replication Serviceを実行するターゲットインサイトサーバーコンピューターは、このリピーターサーバー上のログファイルを読み取れる必要があります。

ターゲットマシンへのアクセスは[!DNL Access Control.cfg]ファイルを使って許可されます。

**ターゲット [!DNL Insight Server] マシンからのアクセス用にアクセス制御を構成するには**

1. リピーター機能をインストールしたディレクトリの[!DNL Access Control]フォルダーに移動します。

   例：[!DNL D:\Adobe\Repeater\Access Control]

1. メモ帳などのテキストエディターで[!DNL Access Control.cfg]を開きます。
1. [!DNL Insight Server]マシン用に、このリピーターサーバー上のログファイルにアクセスする必要のあるアクセスグループを作成します。 このアクセスグループに「レプリケーションターゲット」などの名前を付けます。

   次のファイルフラグメントは、アクセスグループの見え方を示しています。

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. 「Members」セクションで、各マシンのIPアドレスを指定します。
   1. Membersベクトルの項目数を更新して、挿入したマシンのIPアドレスの数を反映します。
   1. [読み取り専用アクセス]セクションで、レプリケーションターゲットがアクセスするイベントデータの場所を指定します。 パスの指定にはスラッシュ(/)を使用してください。 デフォルトの場所は、リピーターマシンの[!DNL Logs]フォルダー(/Logs/)です。
   1. 読み取り専用アクセスベクトルの項目数を更新し、挿入した場所の数を反映します。

1. ファイルの上部にあるアクセス制御グループベクトル内のアクセスグループ数を更新し、新しいアクセスグループの追加を反映します。

   ```
   Access Control Groups = vector: n items
   ```

1. ファイルを保存します。
