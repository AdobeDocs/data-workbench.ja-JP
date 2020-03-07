---
description: 参照ファイルを参照して緯度と経度のデータを取得する要素ポイントレイヤーを作成すると、各要素および関連付けられた緯度と経度を参照ファイルから取得することによって、ポイントの位置を取得できます。
solution: Analytics
title: 参照ファイルを参照する要素ポイントレイヤーの定義
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 参照ファイルを参照する要素ポイントレイヤーの定義{#defining-element-point-layers-referencing-lookup-files}

参照ファイルを参照して緯度と経度のデータを取得する要素ポイントレイヤーを作成すると、各要素および関連付けられた緯度と経度を参照ファイルから取得することによって、ポイントの位置を取得できます。

Instead of using a lookup file, you can use the [!DNL Dynamic Points] functionality, which embeds the latitude and longitude of a location in the name of each element of a dimension. See [Defining Element Point Layers Using Dynamic Points](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

参照ファイルを参照する要素ポイントレイヤーを定義するには、以下のものを作成するか、既に利用可能でなければなりません。

* **ファイルまたは変換データセットインクルードファイルで定義された**&#x200B;ディメンション[!DNL Transformation.cfg]。変換設定ファイルについては、『*データセット設定ガイド*』を参照してください。

* 各データポイントのプロットに使用するデータを含む&#x200B;**参照ファイル**。このファイルには、データポイントごとにキー、経度、緯度の少なくとも 3 つのデータ列を含める必要があります。For more information about the required format of the lookup file, see [Element Point Lookup File Format](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* 参照ファイルの場所を指定し、参照ファイル内のキー、経度、緯度の列名だけでなく、関連ディメンションおよび指標を指定する&#x200B;**レイヤーファイル**。レイヤーファイルに必要な形式について詳しくは、「[要素ポイントレイヤーファイルの形式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)」を参照してください。

>[!NOTE]
>
>The [!DNL Zip Points.layer] file, provided with the [!DNL Geography] profile, is an element point layer that identifies the [!DNL Zipcode.dim] file, the [!DNL Sessions.metric] file, the [!DNL Zip Points.txt] lookup file, and the names of the key, longitude, latitude, and name columns in the lookup file.

