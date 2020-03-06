---
description: デフォルトでは、Insightサーバーは、Insightサーバープログラムファイルと同じドライブにデータセット(temp.db)を書き込みます。
solution: Insight
title: データセットの場所の設定(temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データセットの場所の設定(temp.db){#configuring-the-location-of-the-dataset-temp-db}

デフォルトでは、Insightサーバーは、Insightサーバープログラムファイルと同じドライブにデータセット(temp.db)を書き込みます。

例えば、ドライブCにをインスト [!DNL Insight Server] ールすると、データセットがドライブCに書き込まれます。

データセット [!DNL Insight Server] を別のドライブに維持する場合、または収集するデータの量が複数のドライブの使用を必要とする場合は、ファイルを更新して、ファイルの書き込み先を指定する [!DNL Disk Files.cfg] 必要があり [!DNL Insight Server][!DNL temp.db] ます。

**temp.dbの場所を設定するには**

1. インストールしたデ [!DNL Components] ィレクトリ内のフォルダに移動しま [!DNL Insight Server]す。

   例：[!DNL C:\Adobe\Server\Components]

1. ファイルをメモ [!DNL Disk Files.cfg] 帳などのテキストエディターで開きます。

   デフォルトでは、このファイルには、次に示すように、Disk Files構造に1つのエントリが含まれています。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. の場所を変更するには、デ [!DNL temp.db]ィスクファイルの定義を変更します。 次の例は、構成を編集して、ファイルをドライブC、D、E [!DNL temp.db] に分散させる方法を示しています。

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
   >上記のファイル名には、二重の円記号を使用します。 設定フ [!DNL Insight Server] ァイルでは、バックスラッシュ文字はエスケープ文字です。 テキスト内で特別な制御シーケンス（タブ文字の場合は¥tなど）を表すために使用します。 実際のバックスラッシュ文字を表すには、バックスラッシュを2回（例えば、¥¥）入力して、エスケープ関数を上書きする必要があります。 これは、メモ帳などのテキストエディターで設定ファイルを編集する場合にのみ該当します。

