---
description: Data WorkbenchGeography で提供される Geography プロファイルは、Adobeアプリケーションに追加の機能を提供する内部プロファイルです。
title: Geography プロファイルのインストール
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 9%

---

# Geography プロファイルのインストール{#installing-the-geography-profile}

{{eol}}

Data WorkbenchGeography で提供される Geography プロファイルは、Adobeアプリケーションに追加の機能を提供する内部プロファイルです。

Adobeが提供する他のすべての内部プロファイルと同様に、 [!DNL Geography] プロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

この [!DNL Geography] プロファイルには、 [!DNL Dataset\Transformation\Geography] フォルダー ) を使用して、地理的ディメンションを定義できます。 以下に、 [!DNL Geography] プロファイル：

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

各ファイルの名前は、定義する拡張ディメンションに対して付けられます。 追加のファイル [!DNL IPLookup.cfg]は、他の変換データセットインクルードファイルでディメンションを定義するために使用される、複数の地理データフィールドを定義します。

変換データセットインクルードファイルについて詳しくは、 *データセット設定ガイド*.

**をインストールするには、以下を実行します。 [!DNL Geography] data workbench サーバー上のプロファイル**

>[!NOTE]
>
>以下のインストール手順は、Data Workbench をインストールし、Data Workbench をインストールする Data Workbench サーバーとの間に接続を確立したことを前提としています [!DNL Geography]. まだおこなっていない場合は、 *Data Workbenchユーザーガイド*.

1. 次の場所から Profiles フォルダーを開きます。 [!DNL .zip] ファイルがAdobeで提供された。
1. を [!DNL Geography] フォルダーから data workbench サーバーのインストールディレクトリにある Profiles フォルダーに移動します。 最後に [!DNL ...\Profiles\Geography] フォルダー内に保存されます。 Profiles フォルダー内の他のフォルダーの名前は、表示される名前とは異なる場合があります。

   ![ステップ情報](assets/Geo_installProfiles_dir.png)

1. 次の手順を使用して、 [!DNL profile.cfg] data workbench を使用する各プロファイルのファイル [!DNL Geography].

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックします。 [!DNL profile.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. この [!DNL profile.cfg] ウィンドウが表示されます。

   1. 内 [!DNL profile.cfg] ウィンドウ、右クリック **[!UICONTROL Directories]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      新しいディレクトリをディレクトリのリストの末尾に追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. 新しいディレクトリの名前を入力します。 [!DNL Geography].
   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Profile Manager]、次のチェックマークを右クリック： [!DNL profile.cfg] 内 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >変更した設定ファイルを、Adobeが提供する内部プロファイル ( [!DNL Geography] プロファイル )。変更内容は、これらのプロファイルの更新をインストールすると上書きされます。
