---
description: デフォルトでは、Insightサーバーは、データセット(temp.db)をInsightサーバープログラムファイルと同じドライブに書き込みます。
title: データセット（temp.db）の場所の設定
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# データセット（temp.db）の場所の設定{#configuring-the-location-of-the-dataset-temp-db}

デフォルトでは、Insightサーバーは、データセット(temp.db)をInsightサーバープログラムファイルと同じドライブに書き込みます。

例えば、ドライブCに[!DNL Insight Server]をインストールすると、データセットがドライブCに書き込まれます。

[!DNL Insight Server]でデータセットを別のドライブに維持する場合や、収集するデータ量に複数のドライブを使用する必要がある場合は、[!DNL Disk Files.cfg]ファイルを更新して、[!DNL Insight Server]で[!DNL temp.db]ファイルを書き込む場所を指定する必要があります。

**temp.dbの場所を設定するには**

1. [!DNL Insight Server]をインストールしたディレクトリ内の[!DNL Components]フォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Components]

1. [!DNL Disk Files.cfg]ファイルをメモ帳などのテキストエディターで開きます。

   デフォルトでは、このファイルには、次に示すように、Disk Files構造に1つのエントリが含まれます。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. [!DNL temp.db]の場所を変更するには、ディスクファイルの定義を変更します。 次の例は、[!DNL temp.db]ファイルをドライブC、D、Eに分散させる構成を編集する方法を示しています。

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
   >上記のファイル名では二重の円記号が使用されていることに注意してください。 [!DNL Insight Server]設定ファイルでは、バックスラッシュはエスケープ文字です。 テキスト内で特別な制御シーケンス（タブ文字の場合は\tなど）を表すために使用されます。 実際のバックスラッシュ文字を表すには、バックスラッシュを2回入力する必要があります（\\など）。エスケープ関数を上書きする場合は、 これは、メモ帳などのテキストエディターで設定ファイルを編集する場合にのみ適用されます。
