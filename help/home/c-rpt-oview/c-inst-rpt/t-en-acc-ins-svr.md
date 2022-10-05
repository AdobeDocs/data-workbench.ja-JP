---
description: Data Workbench サーバーに接続するには、そのサーバーにアクセスする権限がレポートサーバーに必要です。
title: Data Workbench サーバーへのアクセスの有効化
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Data Workbench サーバーへのアクセスの有効化{#enabling-access-to-the-data-workbench-server}

{{eol}}

Data Workbench サーバーに接続するには、そのサーバーにアクセスする権限がレポートサーバーに必要です。

Data Workbench サーバーへのアクセス権を付与するには、Report Server の共通名（Report Server の電子証明書で割り当てられたもの）をサーバーのアクセス制御ファイルに追加します。

>[!NOTE]
>
>クラスター環境で作業する場合は、同期の問題を回避するために、マスター Data Workbench サーバーにアクセスするようにレポートサーバーを設定する必要があります。 Data Workbench では、 [!DNL Related Servers] メニュー項目 [!DNL Servers Manager]. 詳しくは、 [!DNL Servers Manager]詳しくは、 *Data Workbenchユーザーガイド*.

次の手順では、Data Workbench サーバー上のアクセス制御ファイルにレポートサーバーを手動で追加する方法について説明します。 このようにアクセス制御ファイルを更新するには、Data Workbench サーバーがインストールされているマシン上でファイルシステムにアクセスできる必要があります。

また、 [!DNL Server Files Manager] （data workbench の） これをおこなうには、Data Workbench クライアントがサーバー上での管理者権限を持っている必要があります。

詳しくは、 [!DNL Server Files Manager]詳しくは、 *Data Workbenchユーザーガイド*.

**Data Workbench サーバーへのアクセスを設定するには**

1. Data Workbench サーバー (InsightServer64.exe) をインストールしたディレクトリ内の Access Control フォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Access Control]

1. 開く [!DNL Access Control.cfg] をメモ帳などのテキストエディターで使用する。
1. を [!DNL Report Server AccessGroup] とを追加します。 [!DNL Report Server’s] 次のファイルフラグメントでハイライト表示されている、このグループの共通名。 ( 共通名を [!DNL Report Server’s] 電子証明書 )

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. ファイルを保存します。
