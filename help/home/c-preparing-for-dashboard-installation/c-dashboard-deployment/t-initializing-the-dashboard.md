---
description: 最後の手順は、ダッシュボードを初めて実行し、初期化できるようにすることです。
title: ダッシュボードの初期化
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# ダッシュボードの初期化{#initializing-the-dashboard}

最後の手順は、ダッシュボードを初めて実行し、初期化できるようにすることです。

1. Web ブラウザーを開き、新しくデプロイしたサイトの URL( 例：https://localhost/dashboard) を入力します。
1. 初めて接続すると、データベーステーブルが設定されるので、若干の遅れが生じる場合があります。
1. 初期ログオン資格情報は次のとおりです。

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. 最初のログイン時に、**[!UICONTROL User]** > **[!UICONTROL Account Settings]** に移動し、**[!UICONTROL Change Password]** を選択して管理者のパスワードを変更します。

これで、ダッシュボードのインストールが完了しました。 まだの場合は、このガイドのData Workbenchの準備の節に記載されている手順を使用して、Data Workbench サーバーとの通信を設定し、ユーザーとグループを管理します。

>[!NOTE]
>
>ダッシュボードのエラーと監査ログは、インストールパス内の [!DNL logs] ディレクトリにあります。

>[!NOTE]
>
>アプリケーションプールの ID を別のアカウントに変更する必要がある場合は、必ずデータベースへのアクセス権を付与し、ID の読み取り/書き込みアクセス権をインストールパスの [!DNL logs] フォルダーに付与します。

>[!NOTE]
>
>データベースの接続文字列を変更する必要がある場合は、**[!UICONTROL IIS Management Console]** を使用して値を編集します。
