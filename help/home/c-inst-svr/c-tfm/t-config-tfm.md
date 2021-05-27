---
description: 変換機能は、InsightサーバーのFSUマシン上で実行され、他のアプリケーションで使用するためのログソースデータの書き出しを有効にします。
title: 変換の設定
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 14%

---

# 変換の設定{#configuring-transform}

変換機能は、InsightサーバーのFSUマシン上で実行され、他のアプリケーションで使用するためのログソースデータの書き出しを有効にします。

[!DNL Transform] は、ファ [!DNL .vsl] イル、ログファイル、XMLファイル、ODBCデータを読み取り、データをファイル、テキストファイル、または区切り文字付きテキストファイルとして書き出しま [!DNL .vsl] す。データの抽出と変換は、常時実行できるほか、スケジュールに基づいて実行することもできます。変更されたイベントデータの出力を提供する各[!DNL Insight Server] FSUは、[!DNL Transform]を実行する必要があります。

>[!NOTE]
>
>通常、[!DNL Transform]は[!DNL Insight Server] FSUにインストールされます。 ただし、[!DNL Insight Server] DPUにインストールする必要が生じる場合があります。 詳しくは、アドビにお問い合わせください。

[!DNL Transform] をインストール、設定および操作するための必要システム構成について詳しくは、*必要システム構成*&#x200B;のドキュメントを参照してください。

Adobeは、[!DNL Transform]機能を[!DNL Insight Server]リリースパッケージ用の[!DNL .zip]ファイル内にプロファイルとして配布します。 [!DNL Transform]プロファイルは、[!DNL Insight Server]に追加機能を提供する内部プロファイルです。 Adobeが提供するその他すべての内部プロファイルと同様に、プロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

プロファイルは、次のファイルで構成されます。

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* ログ処理データセットインクルードファイル

これらのファイルはすべて、プロファイルの[!DNL Dataset]フォルダーにあります。

**にプロファイルをインス [!DNL Transform] トールするには[!DNL Insight Server]**

>[!NOTE]
>
>以下のインストール手順は、[!DNL Insight]をインストールし、[!DNL Insight]と、[!DNL Transform]をインストールする[!DNL Insight Server]との間に接続を確立したことを前提としています。 まだおこなっていない場合は、『ユーザーガイド』を参照してください。[!DNL Insight]

1. [!DNL Insight Server]リリースパッケージの[!DNL .zip]ファイルを開き、[!DNL .zip]ファイル内の[!DNL Profiles]フォルダーを開きます。
1. [!DNL Transform]フォルダーを[!DNL Insight Server]インストールディレクトリの[!DNL Profiles]フォルダーにコピーします。 次の例に示すように、 [!DNL Insight Server]上に[!DNL ...\Profiles\Transform]フォルダーを作成します。

   ![ステップ情報](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >[!DNL Insight Server]のインストールのすべての手順に従うと（[Insightサーバー](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)を参照）、既にProfilesディレクトリに[!DNL Transform]フォルダーが存在する可能性があります。

1. [!DNL Transform]を使用するプロファイルの[!DNL profile.cfg]ファイルを更新するには、次の手順を実行します。 データセットは、これらの手順が完了すると再処理されます。

   1.  [!DNL Profile Manager].
   1. [!DNL profile.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。 [!DNL profile.cfg]ウィンドウが表示されます。

   1. [!DNL profile.cfg]ウィンドウで&#x200B;**[!UICONTROL Directories]**&#x200B;を右クリックし、**[!UICONTROL Add new]** / **[!UICONTROL Directory]**&#x200B;をクリックします。

      新しいディレクトリをディレクトリのリストの最後に追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、**[!UICONTROL Add new]** / **[!UICONTROL Directory]**&#x200B;をクリックします。

   1. 新しいディレクトリの名前を入力します。[!DNL Transform]
   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

   1. [!DNL Profile Manager]で、[!DNL User]列の[!DNL profile.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL profile name]***&#x200B;をクリックします。

      >[!NOTE]
      >
      >変更した設定ファイルを、Adobeが提供する内部プロファイル（プロファイルを含む）に保存しないでください。内部プロファイルに対する更新をインストールすると、変更内容が上書きされます。
