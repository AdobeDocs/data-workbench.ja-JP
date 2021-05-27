---
description: Data Workbenchサーバーに接続するには、レポートサーバーにそのサーバーへのアクセス権が必要です。
title: Data Workbench サーバーへのアクセスの有効化
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Data Workbench サーバーへのアクセスの有効化{#enabling-access-to-the-data-workbench-server}

Data Workbenchサーバーに接続するには、レポートサーバーにそのサーバーへのアクセス権が必要です。

レポートサーバーの共通名（レポートサーバーのデジタル証明書で割り当てられた名前）をサーバーのアクセス制御ファイルに追加することで、Data Workbenchサーバーへのアクセスを許可します。

>[!NOTE]
>
>クラスター環境で作業する場合は、同期の問題を回避するために、マスターData Workbenchサーバーにアクセスするようにレポートサーバーを設定する必要があります。 Data Workbenchでは、[!DNL Servers Manager]の[!DNL Related Servers]メニュー項目を使用して、クラスター内の処理サーバーに関する情報を表示できます。 [!DNL Servers Manager]の詳細については、『*Data Workbenchユーザーガイド*』の「管理インターフェイス」の章を参照してください。

次の手順では、Data Workbenchサーバー上のアクセス制御ファイルにレポートサーバーを手動で追加する方法について説明します。 この方法でアクセス制御ファイルを更新するには、Data Workbenchサーバーがインストールされているマシン上でファイルシステムにアクセスできる必要があります。

Data Workbenchの[!DNL Server Files Manager]を使用して、サーバーのアクセス制御ファイルを更新することもできます。 これをおこなうには、Data Workbenchクライアントにサーバー上の管理者権限が必要です。

[!DNL Server Files Manager]の詳細については、『*Data Workbenchユーザーガイド*』の「管理インターフェイス」の章を参照してください。

**Data Workbenchサーバーへのアクセスを設定するには**

1. Data Workbenchサーバー(InsightServer64.exe)をインストールしたディレクトリ内のアクセス制御フォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Access Control]

1. メモ帳などのテキストエディターで[!DNL Access Control.cfg]を開きます。
1. [!DNL Report Server AccessGroup]を探し、次のファイルフラグメントでハイライト表示されているように、このグループに[!DNL Report Server’s]共通名を追加します。 （[!DNL Report Server’s]電子証明書に表示されるとおりに、共通名を入力します）。

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
