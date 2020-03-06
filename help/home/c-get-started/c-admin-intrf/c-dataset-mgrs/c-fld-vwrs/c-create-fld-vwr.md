---
description: 依存関係マップから引き出し線として、または管理者メニューから単独のビジュアライゼーションとして、フィールドビューアを開けます。
solution: Analytics
title: フィールドビューアの作成
topic: Data workbench
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# フィールドビューアの作成{#create-a-field-viewer}

依存関係マップから引き出し線として、または管理者メニューから単独のビジュアライゼーションとして、フィールドビューアを開けます。

## 依存関係マップからのフィールドビューアの作成 {#section-040cb83c902b49c48b841d35abc127e5}

When you open a field viewer from a dependency map (as shown in [Opening Field Viewers](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)), the viewer is populated automatically based on the log source, transformation, or dimension that you right-click. ログソースまたは変換の場合、ビューアのフィールドは、ログソースまたは変換の入力または出力です。ディメンションの場合、フィールドはディメンションの入力です。必要に応じてフィールドを追加したり、削除したりできます。

## スタンドアロンのビジュアライゼーションとしてのフィールドビューアの作成 {#section-11d10e46631d4fdca45d7534336e1e80}

フィールドビューアをスタンドアロンのビジュアライゼーションとして開くと、またはを作 [!DNL Log Processing Field Viewer] 成できま [!DNL Transformation Field Viewer]す。 ビューアは空白なので、目的のフィールドをビューアに追加する必要があります。の場合は、フ [!DNL Log Processing Field Viewer]ァイルまたは任意のファイルからフ [!DNL Log Processing.cfg] ィールドを追加で [!DNL Log Processing dataset include] きます。 の場合は、フ [!DNL Transformation Field Viewer]ァイルまたは任意のファイルからフ [!DNL Transformation.cfg] ィールドを追加で [!DNL Transformation dataset include] きます。

設定ファイルとインクルードファイルについて詳しくは、『*データセット設定ガイド*』を参照してください。

## フィールドの追加と削除 {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**フィールドビューアにフィールドを追加するには**

* Right-click within the field viewer and click **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   - または -

* Right-click within an existing column in the field viewer and click **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

フィールド名はフィールドの名前を指し、インスタンスはデータセット設定内でフィールドが使用される場所（データセット処理ステージまたは変換など）を指します。データセット設定内の複数の場所で使用されているフィールドもあるので（例えば、1 つのフィールドを複数の変換で変更できます）、フィールドビューアに追加するフィールドのインスタンスを選択する必要があります。

使用可能なフィールドのリストで、ビューアに既に表示されているフィールドの左側には X が表示されます。

**フィールドビューアからフィールドを削除するには**

* Right-click within the column for the field that you want to remove and click **[!UICONTROL Remove Field]**.

