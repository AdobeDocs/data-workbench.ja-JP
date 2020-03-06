---
description: Data Workbenchサーバーに接続するには、Report Serverにそのサーバーへのアクセス権が必要です。
solution: Analytics
title: Data Workbenchサーバーへのアクセスの有効化
topic: Data workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbenchサーバーへのアクセスの有効化{#enabling-access-to-the-data-workbench-server}

Data Workbenchサーバーに接続するには、Report Serverにそのサーバーへのアクセス権が必要です。

Data Workbenchサーバーへのアクセスを許可するには、Report Serverの共通名（Report Serverのデジタル証明書で割り当てられた名前）をサーバーのアクセス制御ファイルに追加します。

>[!NOTE]
>
>クラスター環境で作業する場合は、同期の問題を回避するために、マスターData WorkbenchサーバーにアクセスするようにReport Serverを設定する必要があります。 In data workbench you can view information about processing servers in your cluster using the [!DNL Related Servers] menu item in the [!DNL Servers Manager]. For more information about the [!DNL Servers Manager], see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

次の手順では、Data Workbenchサーバー上のアクセス制御ファイルにReport Serverを手動で追加する方法を説明します。 この方法でアクセス制御ファイルを更新するには、Data Workbenchサーバーがインストールされているマシン上のファイルシステムアクセス権が必要です。

また、Data Workbenchのを使用して、サーバーのアクセス制御ファイルを更 [!DNL Server Files Manager] 新することもできます。 これを行うには、Data Workbenchクライアントがサーバー上での管理権限を持っている必要があります。

For more information about the [!DNL Server Files Manager], see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

**Data Workbenchサーバーへのアクセスを設定するには**

1. Data Workbenchサーバー(InsightServer64.exe)をインストールしたディレクトリ内のAccess Controlフォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Access Control]

1. メモ帳 [!DNL Access Control.cfg] などのテキストエディターで開きます。
1. を探し、次のフ [!DNL Report Server AccessGroup] ァイルフ [!DNL Report Server’s] ラグメントでハイライト表示されている通りに、このグループに共通名を追加します。 (共通名は、デジタル証明書に表示されるとおりに [!DNL Report Server’s] 入力します)。

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
