---
description: data workbenchのGeographyに付属するGeographyプロファイルは、Adobeアプリケーションに追加機能を提供する内部プロファイルです。
title: Geography プロファイルのインストール
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 9%

---

# Geography プロファイルのインストール{#installing-the-geography-profile}

data workbenchのGeographyに付属するGeographyプロファイルは、Adobeアプリケーションに追加機能を提供する内部プロファイルです。

Adobeが提供する他の内部プロファイルと同様に、[!DNL Geography]プロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

[!DNL Geography]プロファイルーには、地理的なディメンションを定義するいくつかの変換データセットインクルードファイル（[!DNL Dataset\Transformation\Geography]フォルダー内）が含まれています。 [!DNL Geography]プロファイルーに付属する変換データセットインクルードファイルのリストを以下に示します。

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

各ファイルには、定義された拡張ディメンションに対して名前が付けられます。 追加のファイル[!DNL IPLookup.cfg]は、他の変換データセットインクルードファイルのディメンションの定義に使用する複数の地理データフィールドを定義します。

変換データセットインクルードファイルについて詳しくは、『*データセット設定ガイド*』を参照してください。

**Data Workbenchサーバーに [!DNL Geography] プロファイルをインストールするには**

>[!NOTE]
>
>以下のインストール手順は、data workbenchをインストールし、data workbench [!DNL Geography]をインストールするdata workbenchサーバーとdata workbenchサーバーとの接続を確立したことを前提としています。 まだ実行していない場合は、『*Data Workbenchユーザーガイド*』を参照してください。

1. Adobeから提供された[!DNL .zip]ファイルからプロファイルフォルダーを開きます。
1. [!DNL Geography]フォルダーを、Data Workbenchサーバーのインストールディレクトリにあるプロファイルフォルダーにコピーします。 次の例に示すように、Data Workbenchサーバー上の[!DNL ...\Profiles\Geography]フォルダーを使用して終了します。 プロファイルフォルダー内の他のフォルダーの名前は、表示されているものと異なる場合があります。

   ![ステップ情報](assets/Geo_installProfiles_dir.png)

1. 次の手順を使用して、Data Workbench [!DNL Geography]を使用する各プロファイルの[!DNL profile.cfg]ファイルを更新します。

   1.  [!DNL Profile Manager].
   1. [!DNL profile.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL from the workbench]**&#x200B;をクリックします。 [!DNL profile.cfg]ウィンドウが表示されます。

   1. [!DNL profile.cfg]ウィンドウで&#x200B;**[!UICONTROL Directories]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Directory]**&#x200B;をクリックします。

      新しいディレクトリをディレクトリのリストの最後に追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Directory]**&#x200B;をクリックします。

   1. 新しいディレクトリの名前を入力します。[!DNL Geography].
   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Profile Manager]で、[!DNL User]列の[!DNL profile.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL profile name]**>*&#x200B;をクリックします。

      >[!NOTE]
      >
      >変更した設定ファイルは、Adobeが提供する内部プロファイル([!DNL Geography]プロファイルを含む)には一切保存しないでください。これらのプロファイルに対するアップデートをインストールすると、変更内容が上書きされます。
