---
description: 参照ファイルを参照して緯度と経度のデータを取得する要素ポイントレイヤーを作成すると、各要素および関連付けられた緯度と経度を参照ファイルから取得することによって、ポイントの位置を取得できます。
title: 参照ファイルを参照する要素ポイントレイヤーの定義
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 70%

---

# 参照ファイルを参照する要素ポイントレイヤーの定義{#defining-element-point-layers-referencing-lookup-files}

{{eol}}

参照ファイルを参照して緯度と経度のデータを取得する要素ポイントレイヤーを作成すると、各要素および関連付けられた緯度と経度を参照ファイルから取得することによって、ポイントの位置を取得できます。

参照ファイルを使用する代わりに、 [!DNL Dynamic Points] 機能：ディメンションの各要素の名前に場所の緯度と経度を埋め込みます。 詳しくは、 [動的ポイントを使用した要素ポイントレイヤーの定義](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

参照ファイルを参照する要素ポイントレイヤーを定義するには、以下のものを作成するか、既に利用可能でなければなりません。

* **ファイルまたは変換データセットインクルードファイルで定義された**&#x200B;ディメンション[!DNL Transformation.cfg]。変換設定ファイルについては、『*データセット設定ガイド*』を参照してください。

* 各データポイントのプロットに使用するデータを含む&#x200B;**参照ファイル**。このファイルには、データポイントごとにキー、経度、緯度の少なくとも 3 つのデータ列を含める必要があります。参照ファイルに必要な形式について詳しくは、 [要素ポイント参照ファイルの形式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* 参照ファイルの場所を指定し、参照ファイル内のキー、経度、緯度の列名だけでなく、関連ディメンションおよび指標を指定する&#x200B;**レイヤーファイル**。レイヤーファイルに必要な形式について詳しくは、「[要素ポイントレイヤーファイルの形式](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)」を参照してください。

>[!NOTE]
>
>この [!DNL Zip Points.layer] ファイル。 [!DNL Geography] profile は、 [!DNL Zipcode.dim] ファイル、 [!DNL Sessions.metric] ファイル、 [!DNL Zip Points.txt] 参照ファイル、および参照ファイル内のキー、経度、緯度、名前の列の名前。
