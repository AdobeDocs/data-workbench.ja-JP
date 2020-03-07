---
description: 必要なMicrosoftコンポーネントをインストールする手順です。
solution: Analytics
title: 必要なコンポーネントのインストール
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 必要なコンポーネントのインストール{#installing-required-components}

必要なMicrosoftコンポーネントをインストールする手順です。

1. Microsoft .NET Framework v4.0をインストールします。

   >[!NOTE]
   >
   >これは、IIS Webの役割をインストールして構成した後にのみインストールする必要があります。

1. ウィザードに従って、インストールを完了するよう求められたデフォルトを選択します。
1. インストールが完了したら、ASP.NET v.4.0アプリケーションプールがIISの一覧に追加されたことを **[!UICONTROL Application Pools]** 確認します。
1. Microsoft SQL Serverデータベースをインストールします。

   管理ツールで任意のバージョンのSQL Server 2008または2008 R2（Expressはサポートされています）を使用します（Adobeでは、SQL Server 2008 R2 SP1 - Express Editionを推奨します）。 1.既存のSQL Serverインスタンスが事前に実行されていない汎用インストールの場合は、画面でオプション **[!UICONTROL Default Instance]** を選択してく **[!UICONTROL Instance Configuration]** ださい。
1. 残りの設定オプションについては、ウィザードに従って、インストールの完了を求められたらデフォルトを選択します。
1. Microsoft Web Deploy v2.0をインストールします。

   ほとんどの場合、インストー **[!UICONTROL Typical]** ルは正常です。 ただし、リモート展開を実行する場合は、完全なインストール（選択）を行う必要があり **[!UICONTROL Complete]**&#x200B;ます。

   すべての前提条件が正しくインストールされたら、Data Workbenchサーバーがダッシュボードと通信できるように準備する準備が整います。
