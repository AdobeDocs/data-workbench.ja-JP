---
description: 要素ポイントレイヤーの列に関する情報です。
solution: Analytics
title: 要素ポイント参照ファイルの形式
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 要素ポイント参照ファイルの形式{#element-point-lookup-file-format}

要素ポイントレイヤーの列に関する情報です。

要素ポイントレイヤー参照ファイルには、以下の少なくとも 3 つの列を含める必要があります。

* **[!DNL Key]列：**この列には、Data Workbenchサーバーが参照ファイル内のデータをデータセット内のデータに接続できるようにする、共通のキーデータを含める必要があります。 The[!DNL Key]column must be the first column in the lookup file. この列の各行は、ディメンションの要素です。

* **[!DNL Longitude]列：**この列には、列内の各データポイントの経度を含める必要があ[!DNL Key]ります。

* **[!DNL Latitude]列：**この列には、列内の各データポイントの緯度が含まれている必要があ[!DNL Key]ります。

* **[!DNL Name]列：**（オプション）。 If you want to specify a name to be displayed on the map for each data point, you can include a[!DNL Name]column in the lookup file.

[!DNL Zip Points.txt] 参照ファイルの各行は、先頭列に郵便番号が含まれ、経度、緯度、関連付けられた都市名と続きます。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

