---
description: Report Serverの一部の機能を動作させるには、ハードウェアまたはソフトウェアを提供し、構成してから、インストールを行う必要があります。
title: 始める前に
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# 始める前に{#before-you-begin}

Report Serverの一部の機能を動作させるには、ハードウェアまたはソフトウェアを提供し、構成してから、インストールを行う必要があります。

## 基本レポートサーバー要件{#section-e891eaee79fe4fa98e658426dc3b2777}

出力されるレポートは、.PNG画像形式、ファイルシステムに配置された.XLSスプレッドシート形式、または電子メール形式で表示できます。 ハードウェア要件は、[data workbenchクライアント](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)と同じです。

Report Serverには、次の要件があります。

* データの出力（ネットワーク共有、ローカルドライブ）用にファイルシステムにアクセスする。
* 設定済みのSMTPサーバーにアクセスします。
* [!DNL Report] ServerにMicrosoft Excel 2010 64ビット以上がインストールされています。 詳しくは、[Officeのサーバー側自動化に関する考慮事項](http://support.microsoft.com/kb/257757)を参照してください。

## 追加の要件{#section-f53d4388656a4dfc90aefe29dfabef89}

* **適切なグラフィックスアダプタを取り付けます。** レポートを正しくレンダリングするには、 [!DNL Report] サーバーをインストールしたマシンに適切なグラフィックアダプターがインストールされている必要があります。

* **レポートをExcelファイルとして生成するには、Microsoft Excelをインストールします。** レポートをMicrosoft Excelファイル( [!DNL .xls] または [!DNL .xlsx])として生成して配信するには、Report Serverをインストールしたコンピューターに64ビット版のMicrosoft Excelがインストールされ、登録されている必要があります。Excelが登録されていない状態でReport Serverが初めてアクセスを試みると、Excelの登録ダイアログボックスが表示されます。 コピーが登録されているかどうかが不明な場合は、Excelを手動で開始し、登録ダイアログボックスが表示されたら、登録プロセスを完了します。

   >[!NOTE]
   >
   >Excelファイルとしてのレポートを生成する場合、Excelの新しいインスタンスが開かれます。 この処理について詳しくは、[http://support.microsoft.com/ja-jp/kb/257757](http://support.microsoft.com/kb/257757) を参照してください。

* **SMTPサーバーへのアクセスを提供し、レポートを電子メールで配布します。** レポートを電子メールで配信する場合は、Report ServerがSMTPサーバーに接続でき、電子メール転送サービスに適したポートを開く必要があります。
