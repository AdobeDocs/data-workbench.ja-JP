---
description: Data Workbenchに付属するGeographyプロファイルは、アドビアプリケーションに追加の機能を提供する内部プロファイルです。
solution: Analytics
title: 地域プロファイルのインストール
topic: Data workbench
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 地域プロファイルのインストール{#installing-the-geography-profile}

Data Workbenchに付属するGeographyプロファイルは、アドビアプリケーションに追加の機能を提供する内部プロファイルです。

アドビが提供する他のすべての内部プロファイルと同様に、プロファ [!DNL Geography] イルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

このプロ [!DNL Geography] ファイルには、地理的なディメンションを定義する（フォルダー内の） [!DNL Dataset\Transformation\Geography] 変換データセットインクルードファイルが含まれています。 次に、プロファイルと共に提供される変換データセットインクルードファイルの一覧を示 [!DNL Geography] します。

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

各ファイルには、定義された拡張ディメンションの名前が付けられます。 別のファイルでは、他の変 [!DNL IPLookup.cfg]換データセットインクルードファイルのディメンションを定義するために使用される複数の地理データフィールドを定義します。

For information about transformation dataset include files, see the *Dataset Configuration Guide*.

**Data Workbenchサーバーにプロ[!DNL Geography]ファイルをインストールするには**

>[!NOTE]
>
>次のインストール手順は、Data Workbenchをインストールし、Data WorkbenchをインストールするData Workbenchサーバーとの接続を確立したことを前提としていま [!DNL Geography]す。 まだ実行していない場合は、『 *Data Workbenchユーザーガイド』を参照してください*。

1. アドビから提供されたファイル [!DNL .zip] からProfilesフォルダーを開きます。
1. Data Workbenchサーバー [!DNL Geography] のインストールディレクトリ内のProfilesフォルダーにフォルダーをコピーします。 次の例に示すように、Data Workbenchサ [!DNL ...\Profiles\Geography] ーバー上のフォルダーが作成されます。 Profilesフォルダー内の他のフォルダーの名前は、表示されているものと異なる場合があります。

   ![ステップ情報](assets/Geo_installProfiles_dir.png)

1. 次の手順を使用して、Data Workbenchを使 [!DNL profile.cfg] 用する各プロファイルのファイルを更新しま [!DNL Geography]す。

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックし、をク [!DNL profile.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL from the workbench]**&#x200B;す。 The [!DNL profile.cfg] window appears.

   1. ウィンドウ [!DNL profile.cfg] で右クリックし、「>」 **[!UICONTROL Directories]** をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Directory]**&#x200B;す。

      新しいディレクトリをディレクトリのリストの最後に追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、/をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Directory]**&#x200B;す。

   1. 新しいディレクトリの名前を入力します。 [!DNL Geography].
   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Profile Manager]のチェックマークを右クリ [!DNL profile.cfg] ックし [!DNL User] 、/ **[!UICONTROL Save to]** &lt; *>をクリック&#x200B;**[!UICONTROL profile name]**します*。

      >[!NOTE]
      >
      >Do not save the modified configuration file to any of the internal profiles provided by Adobe (including the [!DNL Geography] profile), as your changes are overwritten when you install updates to these profiles.

