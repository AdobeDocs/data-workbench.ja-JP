---
description: デフォルトでは、Insight サーバーは Insight サーバープログラムファイルと同じドライブにデータセット (temp.db) を書き込みます。
title: データセット（temp.db）の場所の設定
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# データセット（temp.db）の場所の設定{#configuring-the-location-of-the-dataset-temp-db}

{{eol}}

デフォルトでは、Insight サーバーは Insight サーバープログラムファイルと同じドライブにデータセット (temp.db) を書き込みます。

例えば、 [!DNL Insight Server] ドライブ C で、データセットをドライブ C に書き込みます。

必要に応じて [!DNL Insight Server] 別のドライブにデータセットを維持する場合、または収集するデータの量に複数のドライブを使用する必要がある場合は、 [!DNL Disk Files.cfg] ファイルで指定する場所 [!DNL Insight Server] 書く [!DNL temp.db] ファイル。

**temp.db の場所を設定するには**

1. 次に移動： [!DNL Components] をインストールしたディレクトリ内のフォルダー [!DNL Insight Server].

   例：[!DNL C:\Adobe\Server\Components]

1. を開きます。 [!DNL Disk Files.cfg] ファイルをメモ帳などのテキストエディターで作成します。

   デフォルトでは、このファイルには、次に示すように、Disk Files 構造に 1 つのエントリが含まれています。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. 場所を変更するには [!DNL temp.db]、ディスクファイルの定義を変更します。 次の例は、 [!DNL temp.db] ドライブ C、D、E のファイル：

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
   >上記のファイル名では、二重の円記号が使用されていることに注意してください。 In [!DNL Insight Server] 設定ファイルのバックスラッシュはエスケープ文字です。 テキスト内の特殊な制御シーケンス（タブ文字の場合は\t など）を表すために使用されます。 実際のバックスラッシュ文字を表すには、バックスラッシュを 2 回（\\など）入力して、エスケープ関数を上書きする必要があります。 これは、メモ帳などのテキストエディターで設定ファイルを編集する場合にのみ適用されます。
