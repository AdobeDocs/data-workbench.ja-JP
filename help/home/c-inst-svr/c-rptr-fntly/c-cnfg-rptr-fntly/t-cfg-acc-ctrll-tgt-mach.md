---
description: Insight サーバーレプリケーションサービスを実行する Target Insight サーバーマシンは、このリピーターサーバー上のログファイルを読み取れる必要があります。
title: ターゲットマシンのアクセス制御の設定
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# ターゲットマシンのアクセス制御の設定{#configuring-access-control-for-target-machines}

{{eol}}

Insight サーバーレプリケーションサービスを実行する Target Insight サーバーマシンは、このリピーターサーバー上のログファイルを読み取れる必要があります。

ターゲットマシンへのアクセスは、 [!DNL Access Control.cfg] ファイル。

**Target によるアクセスに対するアクセス制御を構成するには [!DNL Insight Server] マシン**

1. 次に移動： [!DNL Access Control] フォルダー内のリピーター機能をインストールしたディレクトリに格納します。

   例：[!DNL D:\Adobe\Repeater\Access Control]

1. 開く [!DNL Access Control.cfg] をメモ帳などのテキストエディターで使用する。
1. のアクセスグループの作成 [!DNL Insight Server] このリピーターサーバー上のログファイルにアクセスする必要があるマシン。 このアクセスグループに「レプリケーションターゲット」などの名前を付けます。

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

   1. 「メンバー」セクションで、各マシンの IP アドレスを指定します。
   1. Members ベクトルの items 数を更新し、挿入したマシン IP アドレスの数を反映します。
   1. 「読み取り専用アクセス」セクションで、レプリケーションターゲットがアクセスするイベントデータの場所を指定します。 パスの指定にはスラッシュ (/) を使用します。 デフォルトの場所は、 [!DNL Logs] フォルダーをリピーターマシン (/Logs/) 上に置きます。
   1. 読み取り専用アクセスベクトルの項目数を更新し、挿入した位置の数を反映します。

1. 新しいアクセスグループの追加を反映するように、ファイルの上部にあるアクセス制御グループベクトルのアクセスグループの数を更新します。

   ```
   Access Control Groups = vector: n items
   ```

1. ファイルを保存します。
