---
description: Report Serverの一部の機能を動作させるには、インストールの前にハードウェアまたはソフトウェアを提供し、設定する必要があります。
solution: Analytics
title: 始める前に
topic: Data workbench
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 始める前に{#before-you-begin}

Report Serverの一部の機能を動作させるには、インストールの前にハードウェアまたはソフトウェアを提供し、設定する必要があります。

## 基本レポートサーバーの要件 {#section-e891eaee79fe4fa98e658426dc3b2777}

出力されるレポートは、.PNG画像または.XLSスプレッドシートの形式でファイルシステムに配置するか、電子メールで送信できます。 ハードウェア要件は、Data Workbenchクライアント [と同じです](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)。

Report Serverには、次の要件があります。

* データ（ネットワーク共有、ローカルドライブ）の出力用のファイルシステムへのアクセス。
* 設定済みのSMTPサーバーへのアクセス。
* Microsoft Excel 2010 64-bit以上がサーバーにインストールされて [!DNL Report] います。 詳しく [は、「Officeのサーバー側自動化に関する考慮事項](http://support.microsoft.com/kb/257757) 」を参照してください。

## その他の要件 {#section-f53d4388656a4dfc90aefe29dfabef89}

* **適切なグラフィックアダプターを取り付けます。** レポートを正しくレンダリングするには、サーバーをインストールしたマシンに適切な [!DNL Report] グラフィックアダプターがインストールされている必要があります。

* **レポートをExcelファイルとして生成するには、Microsoft Excelをインストールします。** レポートをMicrosoft Excelファイル(または [!DNL .xls][!DNL .xlsx])として生成し、配信するには、Report Serverをインストールしたコンピューターに64ビット版のMicrosoft Excelがインストールされ、登録されている必要があります。 Excelが登録されていない状態で、Report Serverが初めてExcelにアクセスしようとすると、登録ダイアログボックスが表示されます。 コピーが登録されているかどうかが不明な場合は、Excelを手動で起動し、登録ダイアログボックスが表示されたら、登録プロセスを完了します。

   >[!NOTE]
   >
   >Excelファイルとしてレポートを生成する場合、Excelの新しいインスタンスを開きます。 この処理について詳しくは、[http://support.microsoft.com/ja-jp/kb/257757](http://support.microsoft.com/kb/257757) を参照してください。

* **SMTPサーバーへのアクセスを提供して、レポートを電子メールで配信します。** レポートを電子メールで配信する場合は、Report ServerがSMTPサーバーに接続でき、電子メール転送サービスに適したポートを開く必要があります。

