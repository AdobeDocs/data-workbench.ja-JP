---
description: レポートポータルは、global.asaという設定ファイルの情報を使用してユーザセッションを初期化します。
solution: Analytics
title: セッション設定ファイルの編集
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# セッション設定ファイルの編集{#edit-the-session-configuration-file}

レポートポータルは、global.asaという設定ファイルの情報を使用してユーザセッションを初期化します。

をインストールする際 [!DNL Report Portal]は、このファイルを指定どおりに編集する必要があります。 このフ [!DNL global.asa] ァイルは\*PortalName*\PortalASP\ folderディレクトリに存在します。

>[!NOTE]
>
>この設定ファイル内の他のパラメーターは変更しないでください。

1. IISが実行されているマシン上で、メモ帳などのテキ [!DNL global.asa] ストエディターでファイルを開きます。
1. (オプション)ユーザーが認証なしで [!DNL Report Portal] アクセスできるようにするには、Session(&quot;In&quot;)パラメーターの値をtrueに変更します。 デフォルト値はfalseで、アクセスを試みたすべてのユーザーを認証しま [!DNL Report Portal]す。
1. がCドラ [!DNL Report Portal] イブ以外のドライブにインストールされている場合は、Session(&quot;Drive&quot;)パラメータの値を正しいドライブの場所に変更します。
1. Session(&quot;DBPath&quot;)パラメーターの値を変更し、ユーザーの認証に必要な情報を含むデータベースへのパスを反映し [!DNL Report Portal] ます。 ドライブ文字は含めないでくださいが、末尾にスラッシュを含めてください。

   例：[!DNL /Inetpub/wwwroot/Portal/data/]

1. ファイルを保存します。
1. ファイルが正しくインスト [!DNL Report Portal] ールされ、指定された仮想ディレクトリからアクセスできることを確認するには、ブラウザーで次のページを開きます。

   http://*YourServerAddress*/*YourPortalName*

   例：[!DNL http://localhost/VisualReportPortal]

   ASPが正しくイ [!DNL Report Portal] ンストールされている場合は、ポータルのログインページが表示されます。 このページが表示されない場合は、IISでASPが有効になっていることを確認し、仮想ディレクトリのマッピングを再度確認してください。

