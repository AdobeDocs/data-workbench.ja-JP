---
description: Insight Serverレプリケーションサービスを実行するTarget Insight Serverコンピューターは、このリピーターサーバー上のログファイルを読み取れる必要があります。
solution: Insight
title: ターゲットコンピューターのアクセス制御の設定
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ターゲットコンピューターのアクセス制御の設定{#configuring-access-control-for-target-machines}

Insight Serverレプリケーションサービスを実行するTarget Insight Serverコンピューターは、このリピーターサーバー上のログファイルを読み取れる必要があります。

ターゲット・マシンへのアクセスは、ファイルを使用して許可 [!DNL Access Control.cfg] されます。

**ターゲットコンピューターによるアクセスのアクセス制御を構成する[!DNL Insight Server]には**

1. リピーター機能をイ [!DNL Access Control] ンストールしたディレクトリ内のフォルダーに移動します。

   例：[!DNL D:\Adobe\Repeater\Access Control]

1. メモ帳 [!DNL Access Control.cfg] などのテキストエディターで開きます。
1. このリピーターサーバー上のログフ [!DNL Insight Server] ァイルにアクセスする必要があるコンピューターのアクセスグループを作成します。 このアクセスグループに「複製ターゲット」などの名前を付けます。

       次のファイルフラグメントは、アクセスグループの外観を示しています。
       
       ```
       . . .
       6 = AccessGroup:
      Members = vector:N項目
    0 =文字列：IP:Machine0IPAddress
    1 = string:IP:Machine1IPAddress
    。..
       N = string:IP:MachineNIPAddress
     Name = string:Replication Targets
     Read-Only Access = vector:1 items
     0 = string:EventDataLocation
     Read-Write Access = vector:0項目
    。..
      &quot;
   
   1. 「メンバー」セクションで、各マシンのIPアドレスを指定します。
   1. 挿入したコンピューターのIPアドレスの数を反映するように、Membersベクトルの項目数を更新します。
   1. [読み取り専用アクセス]セクションで、レプリケーションターゲットがアクセスするイベントデータの場所を指定します。 パスの指定(/)にスラッシュを使用します。 デフォルトの場所はリピ [!DNL Logs] ータマシン(/Logs/)上のフォルダです。
   1. 読み取り専用アクセスベクトルの項目数を更新し、挿入した場所の数を反映します。

1. ファイルの上部にあるAccess Control Groupsベクトル内のアクセスグループの数を更新し、新しいアクセスグループの追加を反映します。

   ```
   Access Control Groups = vector: n items
   ```

1. ファイルを保存します。
