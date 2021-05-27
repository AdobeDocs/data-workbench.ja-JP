---
description: Report Serverの一部の機能を動作させるには、インストールの前にハードウェアまたはソフトウェアを提供し、設定する必要があります。
title: 始める前に
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# 始める前に{#before-you-begin}

Report Serverの一部の機能を動作させるには、インストールの前にハードウェアまたはソフトウェアを提供し、設定する必要があります。

## 基本的なレポートサーバーの要件{#section-e891eaee79fe4fa98e658426dc3b2777}

出力されるレポートは、ファイルシステムに配置された.PNG画像または.XLSスプレッドシートの形式、または電子メールとして出力できます。 ハードウェア要件は、[data workbenchクライアント](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)と同じです。

レポートサーバーには次の要件があります。

* データ（ネットワーク共有、またはローカルドライブ）の出力用のファイルシステムへのアクセス
* 設定済みのSMTPサーバーにアクセスします。
* [!DNL Report]サーバーにMicrosoft Excel 2010 64ビット以降がインストールされている。 詳しくは、[Officeのサーバー側自動化に関する考慮事項](http://support.microsoft.com/kb/257757)を参照してください。

## その他の要件{#section-f53d4388656a4dfc90aefe29dfabef89}

* **適切なグラフィックアダプターを取り付けます。** レポートを正しくレンダリングするには、サーバーをインストールしたマシンに [!DNL Report] 適切なグラフィックアダプターがインストールされている必要があります。

* **レポートをExcelファイルとして生成するには、Microsoft Excelをインストールします。** レポートをMicrosoft Excelファイル(または [!DNL .xls]  [!DNL .xlsx])として生成して配布するには、Report Serverをインストールしたコンピューターに64ビットMicrosoft Excelの適切なバージョンがインストールされ、登録されている必要があります。Excelが登録されていない場合に、Report Serverが初めてExcelにアクセスしようとすると、登録ダイアログボックスが表示されます。 コピーが登録されているかどうかが不明な場合は、Excelを手動で起動し、登録ダイアログボックスが表示されたら、登録プロセスを完了します。

   >[!NOTE]
   >
   >レポートをExcelファイルとして生成する場合、Excelの新しいインスタンスを開くことになります。 この処理について詳しくは、[http://support.microsoft.com/ja-jp/kb/257757](http://support.microsoft.com/kb/257757) を参照してください。

* **SMTPサーバーへのアクセスを提供し、レポートを電子メールで配布します。** レポートを電子メールで配信する場合は、レポートサーバーがSMTPサーバーに接続でき、電子メール転送サービスに適したポートが開いている必要があります。
