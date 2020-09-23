---
description: 変換機能は、InsightサーバーのFSUマシン上で実行され、他のアプリケーションで使用するログソースデータをエクスポートできるようになります。
solution: Analytics
title: 変換の設定
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 14%

---


# 変換の設定{#configuring-transform}

変換機能は、InsightサーバーのFSUマシン上で実行され、他のアプリケーションで使用するログソースデータをエクスポートできるようになります。

[!DNL Transform] は、 [!DNL .vsl][!DNL .vsl] ファイル、ログファイル、XMLファイル、ODBCデータを読み込み、データをファイル、テキストファイル、または区切り文字付きのテキストファイルとして書き出すことができます。このファイルは、data warehouseの読み込みルーチン、監査機関、その他のターゲットで使用できます。 データの抽出と変換は、常時実行できるほか、スケジュールに基づいて実行することもできます。変更されたイベントデータの出力を提供する各 [!DNL Insight Server] FSUを実行する必要があり [!DNL Transform]ます。

>[!NOTE]
>
>通常、 [!DNL Transform] は [!DNL Insight Server] FSUにインストールされます。 ただし、お客様の導入では、 [!DNL Insight Server] DPUへのインストールが必要になる場合があります。 詳しくは、アドビにお問い合わせください。

[!DNL Transform] をインストール、設定および操作するための必要システム構成について詳しくは、*必要システム構成*&#x200B;のドキュメントを参照してください。

Adobeは、この [!DNL Transform] 機能をリリースパッケージの [!DNL .zip] ファイル内にプロファイルとして配布し [!DNL Insight Server] ます。 この [!DNL Transform] プロファイルは、に追加機能を提供する内部プロファイルで [!DNL Insight Server]す。 Adobeが提供する他のすべての内部プロファイルと同様に、プロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

プロファイルは、次のファイルで構成されます。

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* ログ処理データセットインクルードファイル

これらのファイルはすべて、プロファイルの [!DNL Dataset] フォルダーに格納されます。

**に[!DNL Transform]プロファイルをインストールするには[!DNL Insight Server]**

>[!NOTE]
>
>以下のインストール手順は、との間の接続をインストール [!DNL Insight] して確立し [!DNL Insight] たことを前提としてい [!DNL Insight Server][!DNL Transform]ます。 まだ実行していない場合は、『* [!DNL Insight] ユーザガイド*』を参照してください。

1. リリースパッケージの [!DNL .zip] ファイルを開き、そのフ [!DNL Insight Server] ァイル内の [!DNL Profiles][!DNL .zip] フォルダーを開きます。
1. インストー [!DNL Transform] ルディレクトリ内の [!DNL Profiles] フォルダーにフォルダーをコピー [!DNL Insight Server] します。 次の例に示すように、最後に [!DNL ...\Profiles\Transform] フォルダー [!DNL Insight Server] を作成します。

   ![ステップ情報](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >インストールのすべての手順に従っている場合 [!DNL Insight Server] (「 [Insightサーバー」を参照](../../../home/c-inst-svr/c-msr-server/c-msr-server.md))は、プロファイルーディレクトリに既に [!DNL Transform] フォルダーがある可能性があります。

1. 使用するプロファイルの [!DNL profile.cfg] ファイルを更新するには、次の手順に従い [!DNL Transform]ます。 データセットは、これらの手順が完了すると再処理されます。

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックし、 [!DNL profile.cfg] をクリックし **[!UICONTROL Make Local]**&#x200B;ます。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** /をクリックし **[!UICONTROL in Insight]**&#x200B;ます。 The [!DNL profile.cfg] window appears.

   1. ウィ [!DNL profile.cfg]ンドウで右クリックし、「>」 **[!UICONTROL Directories]** をクリックし **[!UICONTROL Add new]** ま **[!UICONTROL Directory]**&#x200B;す。

      ディレクトリのリストの最後に新しいディレクトリを追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、 **[!UICONTROL Add new]** /をクリックし **[!UICONTROL Directory]**&#x200B;ます。

   1. 新しいディレクトリの名前を入力します。 [!DNL Transform]
   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. で、 [!DNL Profile Manager]列ののチェックマーク [!DNL profile.cfg] を右クリックし、 [!DNL User] / **[!UICONTROL Save to]** &lt; *>をクリックします&#x200B;**[!UICONTROL profile name]***。

      >[!NOTE]
      >
      >変更した設定ファイルは、Adobeが提供する内部プロファイル(プロファイルを含む)には一切保存しないでください。内部プロファイルに対するアップデートをインストールすると変更内容が上書きされます。

