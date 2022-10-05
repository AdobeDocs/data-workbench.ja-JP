---
description: データサービスプロファイル（IP Geo-Intelligence および IP Geo-Location）は、Adobeアプリケーションに追加の機能を提供する内部プロファイルです。
title: データサービスプロファイルのインストール
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 5%

---

# データサービスプロファイルのインストール{#installing-the-data-service-profile}

{{eol}}

データサービスプロファイル（IP Geo-Intelligence および IP Geo-Location）は、Adobeアプリケーションに追加の機能を提供する内部プロファイルです。

Adobeが提供するその他すべての内部プロファイルと同様に、これらのプロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

データサービスプロファイルには、Data Workbench サーバーにインストールされる次のデータセットインクルードファイルが含まれています。

* **プロファイル\*プロファイル名&#x200B;*\Dataset\Log Processing\Traffic\IP.cfg:**ログ処理から変換に渡す c-ip フィールドをリストします。
* **プロファイル\*プロファイル名&#x200B;*\Dataset\Transformation\Geography\IPLookup.cfg:**提供された IP Geo-Intelligence または IP Geo-Location ルックアップファイルを使用して地理データの複数のフィールドを生成する IPLookup 変換を定義します。

変換データセットインクルードファイルについて詳しくは、 *データセット設定ガイド*.

また、各データサービスプロファイルには、という名前の要素ポイントレイヤーファイルが用意されています [!DNL IP Coordinates.layer]. このレイヤーファイルを使用すると、IP アドレスを使用して、グローブ上のデータセットの場所を動的にマッピングできます。 インストール後、レイヤーは Data Workbench サーバーのインストールディレクトリ内の Profiles\*data service name*\Maps フォルダーに保存されます。

この [!DNL IP Coordinates.layer] ファイルは、 [!DNL Coordinates.cfg] 次に示すファイル： [!DNL Geography] プロファイルとは、 Dataset\Transformation\Geography フォルダーにあります。 データセットで定義された Coordinates ディメンションの各要素は、その要素に含まれる緯度と経度の情報を使用してグローブ上にマッピングされます。 ダイナミックポイントを使用する要素ポイントレイヤの詳細については、を参照してください。 [動的ポイントを使用した要素ポイントレイヤーの定義](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>バージョン 5.1 より前に IP Geo-Intelligence および IP Geo-location データサービスをインストールした場合、要素ポイントレイヤーファイルは、動的ポイントを使用する代わりにルックアップファイルを参照します。 各レイヤーファイルは、IP ジオコード参照ファイルと IP ジオコードディメンションを参照します。 IP ジオコード参照ファイルには、IP ジオコード（IP アドレスに基づく地理的な場所）と、それぞれの緯度と経度のリストが含まれます。 データセットで定義された IP Geocode ディメンションの各要素は、IP Geocodes ルックアップファイルにその IP Geocode の緯度と経度が一覧表示され、その IP Geocode に対してグローブ上でマッピングされます。

レイヤーファイルの名前と参照するファイルは、データサービスごとに異なります。

* この [!DNL IP Geocodes D.layer] ファイルは、IP Geo-intelligence(Digital Envoy) プロファイルと共にインストールされます。 この要素ポイントレイヤーは、 [!DNL IP Geocodes D yyyymmdd.txt] ルックアップファイル（定期的に更新する必要がある）と IP Geocode D ディメンション。

* この [!DNL IP Geocodes Q.layer] ファイルが IP Geo-location(Quova) プロファイルと共にインストールされます。 この要素ポイントレイヤーは、 [!DNL IP Geocodes Q yyyymmdd.txt] 参照ファイル（定期的に更新する必要があります）と IP Geocode Q ディメンション。

参照ファイルを使用する要素ポイント画層の詳細については、を参照してください。 [参照ファイルを参照する要素ポイントレイヤーの定義](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## IP Geo-Intelligence または IP Geo-location プロファイルをインストールするには {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>以下のインストール手順は、Data Workbench をインストールし、Data Workbench をインストールする Data Workbench サーバーとの間に接続を確立したことを前提としています [!DNL Geography]. まだおこなっていない場合は、 *Data Workbenchユーザーガイド*.

1. 次の場所から Profiles フォルダーを開きます。 [!DNL .zip] Adobe
1. IP Geo-intelligence または IP Geo-location フォルダーを、Data Workbench サーバーのインストールディレクトリにある Profiles フォルダーにコピーします。 次のような結果になりたい場合：\Profiles\IP Geo-intelligence フォルダーまたは…\Profiles\IP Data Workbench サーバー上の位置情報（以下の例を参照）。 内の他のフォルダーの名前 [!DNL Profiles] フォルダーは、表示されるフォルダーとは異なる場合があります。

   ![](assets/Geo_installProfiles_dirIP.png)

1. 次の手順を使用して、 [!DNL profile.cfg] を使用する各プロファイルのファイル [!DNL IP Geo-intelligence] または [!DNL IP Geo-location] プロファイル。

   1.  **[!UICONTROL Profile Manager]**.
   1. の横のチェックマークを右クリックします。 [!DNL profile.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. この [!DNL profile.cfg] ウィンドウが表示されます。

   1. 内 [!DNL profile.cfg]ウィンドウ、右クリック **[!UICONTROL Directories]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      新しいディレクトリをディレクトリのリストの末尾に追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. 新しいディレクトリの名前を入力します。 [!DNL IP Geo-intelligence] または I [!DNL P Geo-location].

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Profile Manager]、次のチェックマークを右クリック： [!DNL profile.cfg] 内 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>変更した設定ファイルを、Adobeが提供する内部プロファイル ( [!DNL IP Geo-location] または [!DNL IP Geo-intelligence] プロファイル )。変更内容は、これらのプロファイルの更新をインストールすると上書きされます。
