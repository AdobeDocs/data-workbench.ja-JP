---
description: 最後の手順は、ダッシュボードを初めて実行して初期化できるようにすることです。
title: ダッシュボードの初期化
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# ダッシュボードの初期化{#initializing-the-dashboard}

{{eol}}

最後の手順は、ダッシュボードを初めて実行して初期化できるようにすることです。

1. Web ブラウザーを開き、新しくデプロイされたサイトの URL を入力します ( 例：https://localhost/dashboard)。
1. 初めて接続すると、データベーステーブルが設定されるので、少し遅れが生じる場合があります。
1. 最初のログオン資格情報は次のとおりです。

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. 初回ログイン時に、に移動します。 **[!UICONTROL User]** > **[!UICONTROL Account Settings]** を選択し、 **[!UICONTROL Change Password]** 管理者パスワードを変更する場合。

これで、ダッシュボードのインストールが完了しました。 まだの場合は、このガイドのData Workbenchの準備に関する節に記載されている手順に従って、Data Workbench サーバーとの通信を設定し、ユーザーとグループを管理します。

>[!NOTE]
>
>ダッシュボードのエラーと監査ログは、 [!DNL logs] インストールパス内のディレクトリ。

>[!NOTE]
>
>アプリケーションプールの ID を別のアカウントに変更する必要がある場合は、必ずデータベースへのアクセス権を付与し、ID に対する読み取り/書き込みアクセス権を付与します。 [!DNL logs] フォルダーをインストールパスに含めます。

>[!NOTE]
>
>データベースの接続文字列を変更する必要がある場合は、 **[!UICONTROL IIS Management Console]**.
