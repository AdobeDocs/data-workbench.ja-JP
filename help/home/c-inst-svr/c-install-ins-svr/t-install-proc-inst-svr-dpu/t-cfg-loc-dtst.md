---
description: デフォルトでは、Insightサーバーは、Insightサーバープログラムファイルと同じドライブにデータセット(temp.db)を書き込みます。
solution: Analytics
title: データセット（temp.db）の場所の設定
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---


# データセット（temp.db）の場所の設定{#configuring-the-location-of-the-dataset-temp-db}

デフォルトでは、Insightサーバーは、Insightサーバープログラムファイルと同じドライブにデータセット(temp.db)を書き込みます。

例えば、ドライブCにをインストールす [!DNL Insight Server] ると、Cドライブにデータセットが書き込まれます。

データセットを別のドライブに維持する [!DNL Insight Server] 場合、または収集するデータ量に複数のドライブが必要な場合は、ファイルを書き込む場所を指定するために [!DNL Disk Files.cfg] ファイルを更新 [!DNL Insight Server][!DNL temp.db] する必要があります。

**temp.dbの場所を設定するには**

1. インストールしたディレクトリ内の [!DNL Components] フォルダーに移動し [!DNL Insight Server]ます。

   例：[!DNL C:\Adobe\Server\Components]

1. メモ帳などのテキストエディターで [!DNL Disk Files.cfg] ファイルを開きます。

   デフォルトでは、このファイルには、次に示すように、ディスクファイル構造に1つのエントリが含まれます。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. の場所を変更するに [!DNL temp.db]は、ディスクファイル定義を変更します。 次の例は、構成を編集してドライブC、D、Eに [!DNL temp.db] ファイルを分散させる方法を示しています。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >上記のファイル名には、重複の円記号を使用してください。 設定ファイルでは、バックスラッシュ文字はエスケープ文字です。 [!DNL Insight Server] テキスト内で特別な制御シーケンス（タブ文字の場合は¥tなど）を表すために使用します。 実際のバックスラッシュ文字を表すには、バックスラッシュを2回入力する必要があります（例えば、¥¥）。この場合、エスケープ関数は無効になります。 これは、設定ファイルをメモ帳などのテキストエディターで編集する場合にのみ適用されます。

