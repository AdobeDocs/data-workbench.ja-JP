---
description: Geography プロファイルには、画像レイヤーとファイルの集合が保存されます。
title: レイヤーの表示
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 69%

---

# レイヤーの表示{#display-layers}

Geography プロファイルには、画像レイヤーとファイルの集合が保存されます。

グローブを表示している場合、特定の分析作業のための表示に利用可能なレイヤーを選択できます。

* **ブルーマーブル 2km：**&#x200B;このレイヤーにはグローブが表示されます。このレイヤーを選択しない場合、グローブは非表示になります。
* **IP 座標：**&#x200B;この要素ポイントレイヤーには、訪問者の IP アドレスに基づいて、データセット内の場所の緯度と経度が表示されます。
* **郵便番号ポイント：**&#x200B;このレイヤーには、アドビが提供する米国の郵便番号リストに基づいて、データセット内の場所の緯度と経度が表示されます。[!DNL Zip Points.txt] 参照ファイルには、表示する郵便番号、緯度、経度のデータが含まれていますが、[!DNL Zip Points.layer] ファイルにはこのデータをグローブ上に表示するために必要な設定パラメーターが含まれています。これらのファイルはどちらも、 Profiles\Geography\Maps folder within the Data Workbench server installation directoryフォルダーに保存されます。

* ***その他の使用可能なレイヤー名：*** 各レイヤー名は、Insight Serverインストールディレクトリ内のProfiles\Geography\Maps folderフォルダー、プロファイルー\IP Geo-location\Mapsフォルダー、またはプロファイル\IP Geo-intelligence\Mapsフォルダーに保存されている [!DNL .layer] ファイルを表します。

>[!NOTE]
>
>IP Geo-LocationデータサービスまたはIP Geo-Intelligenceプロファイルを持つには、それぞれIP Geo-LocationデータサービスまたはIP Geo-Intelligenceデータサービスを購読する必要があります。

レイヤーの表示順を制御するため、[!DNL order.txt] ファイルを使用できます。 [Order.txtファイルを使用したメニューのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)を参照してください。

**グローブ内でレイヤーを切り替えるには**

* ビジュアライゼーション内で右クリックし、目的のレイヤー名をクリックします。レイヤーの左側の X は、そのレイヤーが表示されていることを示します。
