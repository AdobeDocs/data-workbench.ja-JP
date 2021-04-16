---
description: 依存関係マップから引き出し線として、または管理者メニューから単独のビジュアライゼーションとして、フィールドビューアを開けます。
title: フィールドビューアの作成
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 63%

---

# フィールドビューアの作成{#create-a-field-viewer}

依存関係マップから引き出し線として、または管理者メニューから単独のビジュアライゼーションとして、フィールドビューアを開けます。

## 依存関係マップからフィールドビューアを作成する{#section-040cb83c902b49c48b841d35abc127e5}

依存関係マップ（[フィールドビューアを開く](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)に示すように）からフィールドビューアを開くと、右クリックしたログソース、変換、ディメンションに基づいて、ビューアの内容が自動的に設定されます。 ログソースまたは変換の場合、ビューアのフィールドは、ログソースまたは変換の入力または出力です。ディメンションの場合、フィールドはディメンションの入力です。必要に応じてフィールドを追加したり、削除したりできます。

## 独立したビジュアライゼーションとしてのフィールドビューアの作成{#section-11d10e46631d4fdca45d7534336e1e80}

単独のビジュアライゼーションとしてフィールドビューアを開く場合は、[!DNL Log Processing Field Viewer]または[!DNL Transformation Field Viewer]を作成できます。 ビューアは空白なので、目的のフィールドをビューアに追加する必要があります。[!DNL Log Processing Field Viewer]の場合は、[!DNL Log Processing.cfg]ファイルまたは任意の[!DNL Log Processing dataset include]ファイルからフィールドを追加できます。 [!DNL Transformation Field Viewer]の場合は、[!DNL Transformation.cfg]ファイルまたは任意の[!DNL Transformation dataset include]ファイルからフィールドを追加できます。

設定ファイルとインクルードファイルについて詳しくは、『*データセット設定ガイド*』を参照してください。

## フィールド追加{#section-9c0d4f5735a044a8b21dc7a99c63a59a}を削除します。

**フィールドビューアにフィールドを追加するには**

* フィールドビューア内で右クリックし、**[!UICONTROL Fields]**/*&lt;**[!UICONTROL field name]***/***[!UICONTROL instance]***&#x200B;をクリックします。

   -or-

* フィールドビューアの既存の列内で右クリックし、**[!UICONTROL Fields]**/*&lt;**[!UICONTROL field name]***/***[!UICONTROL instance]***&#x200B;をクリックします。

フィールド名はフィールドの名前を指し、インスタンスはデータセット設定内でフィールドが使用される場所（データセット処理ステージまたは変換など）を指します。データセット設定内の複数の場所で使用されているフィールドもあるので（例えば、1 つのフィールドを複数の変換で変更できます）、フィールドビューアに追加するフィールドのインスタンスを選択する必要があります。

使用可能なフィールドのリストで、ビューアに既に表示されているフィールドの左側には X が表示されます。

**フィールドビューアからフィールドを削除するには**

* 削除するフィールドの列内で右クリックし、「**[!UICONTROL Remove Field]**」をクリックします。
