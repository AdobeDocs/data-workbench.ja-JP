---
description: 変換機能は、Insight サーバー FSU マシン上で実行され、他のアプリケーションで使用するためのログソースデータの書き出しを有効にします。
title: 変換の設定
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 14%

---

# 変換の設定{#configuring-transform}

{{eol}}

変換機能は、Insight サーバー FSU マシン上で実行され、他のアプリケーションで使用するためのログソースデータの書き出しを有効にします。

[!DNL Transform] 読み取り可能 [!DNL .vsl] ファイル、ログファイル、XML ファイル、ODBC データを書き出し、 [!DNL .vsl] data warehouse の読み込みルーチン、監査エージェンシー、その他のターゲットで使用できるファイル、テキストファイル、または区切り文字付きテキストファイル。 データの抽出と変換は、常時実行できるほか、スケジュールに基づいて実行することもできます。各 [!DNL Insight Server] 変更されたイベントデータを出力する FSU を実行する必要がある [!DNL Transform].

>[!NOTE]
>
>通常、 [!DNL Transform] が [!DNL Insight Server] FSU。 ただし、実装時に、 [!DNL Insight Server] DPU。 詳しくは、アドビにお問い合わせください。

[!DNL Transform] をインストール、設定および操作するための必要システム構成について詳しくは、*必要システム構成*&#x200B;のドキュメントを参照してください。

Adobeが [!DNL Transform] の機能は、 [!DNL .zip] ファイル [!DNL Insight Server] パッケージをリリースします。 この [!DNL Transform] プロファイルは、 [!DNL Insight Server]. Adobeが提供する他のすべての内部プロファイルと同様に、プロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

プロファイルは、次のファイルで構成されます。

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* ログ処理データセットインクルードファイル

これらのファイルはすべて、 [!DNL Dataset] プロファイルのフォルダー。

**をインストールするには、以下を実行します。 [!DNL Transform] ～に関するプロフィール[!DNL Insight Server]**

>[!NOTE]
>
>以下のインストール手順は、がインストール済みであることを前提としています。 [!DNL Insight] そして～間のつながりを確立した [!DNL Insight] そして [!DNL Insight Server] インストール先 [!DNL Transform]. まだおこなっていない場合は、* [!DNL Insight] ユーザーガイド*。

1. を開きます。 [!DNL .zip] ファイル [!DNL Insight Server] パッケージをリリースし、 [!DNL Profiles] その中のフォルダ [!DNL .zip] ファイル。
1. を [!DNL Transform] フォルダーを [!DNL Profiles] の [!DNL Insight Server] インストールディレクトリ。 最後に [!DNL ...\Profiles\Transform] の [!DNL Insight Server] を次の例に示します。

   ![ステップ情報](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >インストールのすべての手順に従った場合 [!DNL Insight Server] ( [Insight サーバー](../../../home/c-inst-svr/c-msr-server/c-msr-server.md))、既に [!DNL Transform] フォルダーを作成します。

1. 次の手順を使用して、 [!DNL profile.cfg] 使用するプロファイルのファイル [!DNL Transform]. データセットは、これらの手順の完了時に再処理します。

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックします。 [!DNL profile.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. この [!DNL profile.cfg] ウィンドウが表示されます。

   1. 内 [!DNL profile.cfg]ウィンドウ、右クリック **[!UICONTROL Directories]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      新しいディレクトリをディレクトリのリストの末尾に追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. 新しいディレクトリの名前を入力します。 [!DNL Transform]
   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Profile Manager]、次のチェックマークを右クリック： [!DNL profile.cfg] 内 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Adobeが提供する内部プロファイル（プロファイルを含む）に対して、変更した設定ファイルを保存しないでください。これらのプロファイルの更新をインストールすると、変更内容が上書きされます。
