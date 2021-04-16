---
description: デフォルトでは、Insightサーバーは、Insightサーバープログラムファイルと同じドライブにデータセット(temp.db)を書き込みます。
title: データセット（temp.db）の場所の設定
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# データセット（temp.db）の場所の設定{#configuring-the-location-of-the-dataset-temp-db}

デフォルトでは、Insightサーバーは、Insightサーバープログラムファイルと同じドライブにデータセット(temp.db)を書き込みます。

例えば、[!DNL Insight Server]をドライブCにインストールすると、Cドライブにデータセットが書き込まれます。

[!DNL Insight Server]にデータセットを別のドライブに保持したい場合、または収集するデータ量が複数のドライブを使用する必要がある場合は、[!DNL Insight Server]に[!DNL temp.db]ファイルを書き込む場所を指定するように[!DNL Disk Files.cfg]ファイルを更新する必要があります。

**temp.dbの場所を設定するには**

1. [!DNL Insight Server]をインストールしたディレクトリの[!DNL Components]フォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Components]

1. [!DNL Disk Files.cfg]ファイルをメモ帳などのテキストエディターで開きます。

   デフォルトでは、このファイルには、次に示すように、ディスクファイル構造に1つのエントリが含まれます。

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. [!DNL temp.db]の場所を変更するには、ディスクファイルの定義を変更します。 次の例は、[!DNL temp.db]ファイルをドライブC、D、Eに分散させるように構成を編集する方法を示しています。

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
   >上記のファイル名には、重複の円記号を使用してください。 [!DNL Insight Server]設定ファイルでは、バックスラッシュ文字はエスケープ文字です。 テキスト内で特別な制御シーケンス（タブ文字の場合は¥tなど）を表すために使用します。 実際のバックスラッシュ文字を表すには、バックスラッシュを2回入力する必要があります（例えば、¥¥）。この場合、エスケープ関数は無効になります。 これは、設定ファイルをメモ帳などのテキストエディターで編集する場合にのみ適用されます。
