---
description: 最後の手順は、ダッシュボードの初期化を許可するために、初めて実行することです。
title: ダッシュボードの初期化
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# ダッシュボードの初期化{#initializing-the-dashboard}

最後の手順は、ダッシュボードの初期化を許可するために、初めて実行することです。

1. Webブラウザーを開き、新しくデプロイしたサイトのURLを入力します(例：http://localhost/dashboard)。
1. 初めて接続すると、データベーステーブルがセットアップされるので、若干の遅延が発生する場合があります。
1. 初期ログオン資格情報は次のとおりです。

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. 最初のログイン時に、**[!UICONTROL User]** > **[!UICONTROL Account Settings]**&#x200B;に移動し、**[!UICONTROL Change Password]**&#x200B;を選択して管理者パスワードを変更します。

これで、ダッシュボードのインストールは完了です。 まだData Workbenchサーバーとの通信を設定したり、Data Workbenchおよびグループを管理したりするには、このガイドの「サーバーの準備」の節に説明されている手順に従います。

>[!NOTE]
>
>ダッシュボードエラーと監査ログは、インストールパス内の[!DNL logs]ディレクトリにあります。

>[!NOTE]
>
>アプリケーションプールのIDを別のアカウントに変更する必要がある場合は、データベースへのアクセスを許可し、IDの読み取り/書き込みアクセス権をインストールパスの[!DNL logs]フォルダーに付与します。

>[!NOTE]
>
>データベースの接続文字列を変更する必要が生じた場合は、**[!UICONTROL IIS Management Console]**&#x200B;を使って値を編集します。
