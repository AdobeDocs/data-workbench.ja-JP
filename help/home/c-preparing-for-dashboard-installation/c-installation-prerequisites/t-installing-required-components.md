---
description: 必要なMicrosoftコンポーネントをインストールする手順です。
title: 必須コンポーネントのインストール
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# 必須コンポーネントのインストール{#installing-required-components}

必要なMicrosoftコンポーネントをインストールする手順です。

1. Microsoft .NET Framework v4.0をインストールします。

   >[!NOTE]
   >
   >IIS Webの役割をインストールおよび構成した後にのみインストールする必要があります。

1. ウィザードに従って、インストールを完了するよう求められたデフォルトを選択します。
1. インストールが完了したら、ASP.NET v.4.0アプリケーションプールがIISの&#x200B;**[!UICONTROL Application Pools]**&#x200B;リストに追加されたことを確認します。
1. Microsoft SQL Serverデータベースをインストールします。

   管理ツールで任意のバージョンのSQL Server 2008または2008 R2（Expressはサポートされています）を使用します(Adobeでは、SQL Server 2008 R2 SP1 - Express Editionを推奨します)。 1.前もって実行されている既存のSQL Serverインスタンスを持たない汎用インストールの場合は、**[!UICONTROL Instance Configuration]**&#x200B;画面で&#x200B;**[!UICONTROL Default Instance]**&#x200B;オプションを選択してください。
1. 残りの構成オプションについては、ウィザードに従って、インストールを完了するよう求められたらデフォルトを選択します。
1. Microsoft Web Deploy v2.0をインストールします。

   ほとんどのインストールでは、**[!UICONTROL Typical]**&#x200B;のインストールは問題ありません。 ただし、リモート展開を実行する場合は、完全なインストールを行う必要があります（**[!UICONTROL Complete]**&#x200B;を選択）。

   すべての前提条件が正しくインストールされると、Data Workbenchサーバーがダッシュボードと通信できる状態になります。
