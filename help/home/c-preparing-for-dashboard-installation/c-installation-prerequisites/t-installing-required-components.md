---
description: 必要なMicrosoftコンポーネントのインストール手順です。
title: 必須コンポーネントのインストール
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# 必須コンポーネントのインストール{#installing-required-components}

{{eol}}

必要なMicrosoftコンポーネントのインストール手順です。

1. Microsoft .NET Framework v4.0 をインストールします。

   >[!NOTE]
   >
   >IIS Web ロールをインストールおよび設定した後にのみインストールする必要があります。

1. ウィザードに従って、インストールを完了するよう求められたデフォルトを選択します。
1. インストールが完了したら、ASP.NET v.4.0 アプリケーションプールが **[!UICONTROL Application Pools]** IIS でのリスト。
1. Microsoft SQL Server データベースをインストールします。

   管理ツールで SQL Server 2008 または 2008 R2 （Express がサポートされている）の任意のバージョンを使用します (Adobeでは、SQL Server 2008 R2 SP1 - Express Edition を推奨します )。 1.事前に実行されている既存の SQL Server インスタンスを使用しない汎用インストールの場合は、 **[!UICONTROL Default Instance]** オプションを **[!UICONTROL Instance Configuration]** 画面
1. 残りの設定オプションについては、ウィザードに従って、インストールを完了するよう求められたらデフォルトを選択します。
1. Microsoft Web Deploy v2.0 をインストールします。

   ほとんどのインストールでは、 **[!UICONTROL Typical]** インストールに問題はありません。 ただし、リモートデプロイメントを実行する予定の場合は、完全インストールを実行する必要があります ( **[!UICONTROL Complete]**) をクリックします。

   すべての前提条件が正しくインストールされたら、ダッシュボードと通信する Data Workbench サーバーを準備する準備が整います。
