---
description: 変換機能は、InsightサーバーのFSUマシン上で実行され、他のアプリケーションで使用するログソースデータのエクスポートを有効にします。
solution: Insight
title: 変換の設定
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 変換の設定{#configuring-transform}

変換機能は、InsightサーバーのFSUマシン上で実行され、他のアプリケーションで使用するログソースデータのエクスポートを有効にします。

[!DNL Transform] は、ファイ [!DNL .vsl][!DNL .vsl] ル、ログファイル、XMLファイル、ODBCデータを読み取り、データをファイル、テキストファイル、または区切り文字付きのテキストファイルとして書き出し、Data Warehouseの読み込みルーチン、監査機関、その他のターゲットで使用できます。 データの抽出と変換は、常時実行できるほか、スケジュールに基づいて実行することもできます。変更され [!DNL Insight Server] たイベントデータの出力を提供する各FSUを実行する必要がありま [!DNL Transform]す。

>[!NOTE]
>
>通常、は [!DNL Transform] FSUにインストールさ [!DNL Insight Server] れます。 ただし、DPUへのインストールが必要な場合があ [!DNL Insight Server] ります。 詳しくは、アドビにお問い合わせください。

[!DNL Transform] をインストール、設定および操作するための必要システム構成について詳しくは、*必要システム構成*&#x200B;のドキュメントを参照してください。

アドビは、リリースパ [!DNL Transform] ッケージ用の機能をプロファイルと [!DNL .zip] してファイル内に配 [!DNL Insight Server] 布しています。 プロファ [!DNL Transform] イルは、に追加機能を提供する内部プロファイルで [!DNL Insight Server]す。 アドビが提供する他のすべての内部プロファイルと同様に、プロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

プロファイルは、次のファイルで構成されます。

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* ログ処理データセットインクルードファイル

これらのファイルはすべて、プロファイルのフ [!DNL Dataset] ォルダーに格納されます。

**プロファイルをインスト[!DNL Transform]ールするには[!DNL Insight Server]**

>[!NOTE]
>
>次のインストール手順は、との間の接続がインスト [!DNL Insight] ールされ、確立され [!DNL Insight] ているこ [!DNL Insight Server] とを前提としています [!DNL Transform]。 まだ行っていない場合は、『*ユーザガイド*』を参 [!DNL Insight] 照してください。

1. リリースパッ [!DNL .zip] ケージのフ [!DNL Insight Server] ァイルを開き、そのファイ [!DNL Profiles] ル内のフォルダーを開 [!DNL .zip] きます。
1. インストールデ [!DNL Transform] ィレクトリ内の [!DNL Profiles] フォルダにフォルダをコ [!DNL Insight Server] ピーします。 次の例に示すように、最 [!DNL ...\Profiles\Transform] 後にフォ [!DNL Insight Server] ルダーを作成します。

   ![ステップ情報](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >インストールのすべての手順に従った場合 [!DNL Insight Server] ( [Insightサーバーを参照](../../../home/c-inst-svr/c-msr-server/c-msr-server.md))、Profilesディレクトリに既にフ [!DNL Transform] ォルダーが存在する可能性があります。

1. 次の手順を実行して、使用する [!DNL profile.cfg] プロファイルのファイルを更新しま [!DNL Transform]す。 データセットは、これらの手順が完了すると再処理されます。

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックし、をク [!DNL profile.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL in Insight]**&#x200B;す。 The [!DNL profile.cfg] window appears.

   1. ウィンドウ [!DNL profile.cfg]で右クリックし、「>」 **[!UICONTROL Directories]** をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Directory]**&#x200B;す。

      新しいディレクトリをディレクトリのリストの最後に追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、/をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Directory]**&#x200B;す。

   1. 新しいディレクトリの名前を入力します。 [!DNL Transform]
   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Profile Manager]のチェックマークを右クリ [!DNL profile.cfg] ックし [!DNL User] 、/ **[!UICONTROL Save to]** &lt; *>をクリック&#x200B;**[!UICONTROL profile name]**します*。

      >[!NOTE]
      >
      >変更した設定ファイルは、アドビが提供する内部プロファイル（プロファイルを含む）に保存しないでください。内部プロファイルに対する更新をインストールすると、変更内容が上書きされます。

