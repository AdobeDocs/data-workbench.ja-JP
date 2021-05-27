---
description: Insightサーバーレプリケーションサービスを実行するTarget Insightサーバーマシンは、このリピーターサーバー上のログファイルを読み取れる必要があります。
title: ターゲットマシンのアクセス制御の設定
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# ターゲットマシンのアクセス制御の設定{#configuring-access-control-for-target-machines}

Insightサーバーレプリケーションサービスを実行するTarget Insightサーバーマシンは、このリピーターサーバー上のログファイルを読み取れる必要があります。

ターゲットマシンへのアクセスは、[!DNL Access Control.cfg]ファイルを使用して許可されます。

**ターゲットマシンによるアクセスのアクセス制御を構成する [!DNL Insight Server] には**

1. リピーター機能をインストールしたディレクトリ内の[!DNL Access Control]フォルダーに移動します。

   例：[!DNL D:\Adobe\Repeater\Access Control]

1. メモ帳などのテキストエディターで[!DNL Access Control.cfg]を開きます。
1. [!DNL Insight Server]マシンのアクセスグループを作成し、このリピーターサーバー上のログファイルにアクセスする必要があります。 このアクセスグループに「レプリケーションターゲット」などの名前を付けます。

   次のファイルフラグメントは、アクセスグループの外観を示しています。

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

   1. 「メンバー」セクションで、各マシンのIPアドレスを指定します。
   1. 挿入したマシンIPアドレスの数を反映するように、Membersベクトルの項目数を更新します。
   1. 「読み取り専用アクセス」セクションで、レプリケーションターゲットがアクセスするイベントデータの場所を指定します。 パスの指定(/)にはスラッシュを使用します。 デフォルトの場所は、リピーターマシン(/Logs/)の[!DNL Logs]フォルダーです。
   1. 挿入した位置の数を反映するように、読み取り専用アクセスベクトルの項目数を更新します。

1. 新しいアクセスグループの追加を反映するように、ファイルの最上部にあるAccess Control Groupsベクトルのアクセスグループの数を更新します。

   ```
   Access Control Groups = vector: n items
   ```

1. ファイルを保存します。
