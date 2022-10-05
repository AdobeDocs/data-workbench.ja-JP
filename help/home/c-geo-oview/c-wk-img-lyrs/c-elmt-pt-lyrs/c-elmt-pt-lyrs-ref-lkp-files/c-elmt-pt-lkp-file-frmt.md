---
description: 要素ポイントレイヤーの列に関する情報。
title: 要素ポイント参照ファイルの形式
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 34%

---

# 要素ポイント参照ファイルの形式{#element-point-lookup-file-format}

{{eol}}

要素ポイントレイヤーの列に関する情報。

要素ポイントレイヤー参照ファイルには、以下の少なくとも 3 つの列を含める必要があります。

* **[!DNL Key]列：** この列には、共通キーデータが含まれている必要があります。これにより、Data Workbench サーバーは、ルックアップファイル内のデータをデータセット内のデータに接続できます。 この [!DNL Key] 列は、参照ファイルの最初の列である必要があります。 この列の各行は、ディメンションの要素です。

* **[!DNL Longitude]列：** この列には、 [!DNL Key] 列。

* **[!DNL Latitude]列：** この列には、 [!DNL Key] 列。

* **[!DNL Name]列：** （オプション）。 各データポイントのマップに表示する名前を指定する場合は、 [!DNL Name] 」列を使用して、ルックアップファイル内の値を指定します。

[!DNL Zip Points.txt] 参照ファイルの各行は、先頭列に郵便番号が含まれ、経度、緯度、関連付けられた都市名と続きます。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
