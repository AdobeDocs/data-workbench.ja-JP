---
description: Report Server の一部の機能を動作させるには、インストールの前にハードウェアまたはソフトウェアを提供し、設定する必要があります。
title: 始める前に
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# 始める前に{#before-you-begin}

Report Server の一部の機能を動作させるには、インストールの前にハードウェアまたはソフトウェアを提供し、設定する必要があります。

## 基本レポートサーバーの要件 {#section-e891eaee79fe4fa98e658426dc3b2777}

出力されるレポートは、.PNG 画像形式または.XLS スプレッドシート形式でファイルシステムに配置するか、電子メール形式で配置できます。 ハードウェア要件は、[data workbench クライアント ](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements) と同じです。

レポートサーバーには次の要件があります。

* データ（ネットワーク共有、またはローカルドライブ）の出力用のファイルシステムへのアクセス
* 設定済みの SMTP サーバーへのアクセス
* Microsoft Excel 2010 64 ビット以降が [!DNL Report] Server にインストールされている。 詳しくは、[Office のサーバー側自動化に関する考慮事項 ](https://support.microsoft.com/kb/257757) を参照してください。

## その他の要件 {#section-f53d4388656a4dfc90aefe29dfabef89}

* **適切なグラフィックスアダプタを取り付けます。** レポートを適切にレンダリングするには、Server をインストールしたマシンに適切なグ [!DNL Report] ラフィックアダプタがインストールされている必要があります。

* **Microsoft Excel をインストールして、レポートを Excel ファイルとして生成します。** レポートを生成してMicrosoft Excel ファイル ( または [!DNL .xls]  [!DNL .xlsx]) として配布するには、Report Server をインストールしたマシンに 64 ビット版のMicrosoft Excel がインストールされ、登録されている必要があります。Excel が登録されていない場合に、Report Server が初めてアクセスを試みると、登録ダイアログボックスが表示されます。 コピーが登録されているかどうかが不明な場合は、Excel を手動で起動し、登録ダイアログボックスが表示されたら、登録プロセスを完了します。

   >[!NOTE]
   >
   >Excel ファイルとしてレポートを生成する場合、Excel の新しいインスタンスが開きます。 このプロセスの詳細については、[https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757) を参照してください。

* **SMTP サーバーへのアクセスを提供して、レポートを電子メールで配布します。** レポートを電子メールで配信する場合は、レポートサーバーが SMTP サーバーに接続でき、電子メール転送サービスに適したポートを開く必要があります。
