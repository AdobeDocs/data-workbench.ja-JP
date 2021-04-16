---
description: レポートポータルは、global.asaという設定ファイルの情報を使用してユーザセッションを初期化します。
title: セッション設定ファイルの編集
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# セッション設定ファイルの編集{#edit-the-session-configuration-file}

レポートポータルは、global.asaという設定ファイルの情報を使用してユーザセッションを初期化します。

[!DNL Report Portal]をインストールする際は、このファイルを指示どおりに編集する必要があります。 [!DNL global.asa]ファイルは\*PortalName*\PortalASP\ folderにあります。

>[!NOTE]
>
>この設定ファイル内の他のパラメーターは変更しないでください。

1. IISが実行されているマシン上で、[!DNL global.asa]ファイルをメモ帳などのテキストエディターで開きます。
1. （オプション）ユーザーが認証なしで[!DNL Report Portal]にアクセスできるようにするには、Session(&quot;In&quot;)パラメーターの値をtrueに変更します。 デフォルト値はfalseで、[!DNL Report Portal]へのアクセスを試みたすべてのユーザーを認証します。
1. [!DNL Report Portal]がCドライブ以外のドライブにインストールされている場合は、Session(&quot;Drive&quot;)パラメーターの値を正しいドライブの場所に変更します。
1. Session(&quot;DBPath&quot;)パラメーターの値を変更し、[!DNL Report Portal]ユーザーの認証に必要な情報を含むデータベースへのパスを反映します。 ドライブ文字は含めないでください。末尾にはスラッシュを含めてください。

   例：[!DNL /Inetpub/wwwroot/Portal/data/]

1. ファイルを保存します。
1. [!DNL Report Portal]ファイルが正しくインストールされ、指定された仮想ディレクトリからアクセスできることを確認するには、ブラウザで次のページを開きます。

   http://*YourServerAddress*/*YourPortalName*

   例：[!DNL http://localhost/VisualReportPortal]

   [!DNL Report Portal] ASPが正しくインストールされている場合は、ポータルのログインページが表示されます。 このページが表示されない場合は、IISでASPが有効になっていることを確認し、仮想ディレクトリのマッピングを重複確認してください。
