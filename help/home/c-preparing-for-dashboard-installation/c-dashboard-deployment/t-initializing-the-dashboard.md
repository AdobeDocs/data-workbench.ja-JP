---
description: 最後の手順は、ダッシュボードの初期化を許可するために、初めて実行することです。
solution: Analytics
title: ダッシュボードの初期化
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: 4b39a42285c39e26f097b91309c269c05a9475bd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ダッシュボードの初期化{#initializing-the-dashboard}

最後の手順は、ダッシュボードの初期化を許可するために、初めて実行することです。

1. Webブラウザーを開き、新しくデプロイしたサイトのURLを入力します(例：http://localhost/dashboard)。
1. 初めて接続すると、データベーステーブルがセットアップされるので、若干の遅延が発生する場合があります。
1. 初期ログオン資格情報は次のとおりです。

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. 初回ログイン時に、 **[!UICONTROL User]** >に移動し、 **[!UICONTROL Account Settings]** を選択して管理者パスワード **[!UICONTROL Change Password]** を変更します。

これで、ダッシュボードのインストールは完了です。 まだData Workbenchサーバーとの通信を設定したり、ユーザーやグループを管理したりするには、このガイドの「Data Workbenchの準備」の節に説明されている手順を使用します。

>[!NOTE]
>
>ダッシュボードエラーと監査ログは、インストールパス内の [!DNL logs] ディレクトリにあります。

>[!NOTE]
>
>アプリケーションプールのIDを別のアカウントに変更する必要がある場合は、データベースへのアクセスを許可し、IDの読み取り/書き込みアクセス権をインストールパスの [!DNL logs] フォルダーに付与します。

>[!NOTE]
>
>データベースの接続文字列を変更する必要が生じた場合は、を使用して値を編集し **[!UICONTROL IIS Management Console]**&#x200B;ます。
