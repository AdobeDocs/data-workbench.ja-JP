---
description: Report Portal は、global.asa という設定ファイル内の情報を使用して、ユーザーセッションを初期化します。
title: セッション設定ファイルの編集
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# セッション設定ファイルの編集{#edit-the-session-configuration-file}

{{eol}}

Report Portal は、global.asa という設定ファイル内の情報を使用して、ユーザーセッションを初期化します。

インストール時 [!DNL Report Portal]に設定する場合は、このファイルを指定どおりに編集する必要があります。 この [!DNL global.asa] ファイルは\*PortalName*\PortalASP\フォルダ内に存在します。

>[!NOTE]
>
>この設定ファイル内の他のパラメーターは変更しないでください。

1. IIS が実行されているマシンで、 [!DNL global.asa] ファイルをメモ帳などのテキストエディターで作成します。
1. （オプション）。ユーザーが [!DNL Report Portal] 認証を行わない場合は、Session(&quot;In&quot;) パラメーターの値を true に変更します。 デフォルトは false で、アクセスを試みたすべてのユーザーを認証します。 [!DNL Report Portal].
1. 次に、 [!DNL Report Portal] が C ドライブ以外のドライブにインストールされている場合は、Session(&quot;Drive&quot;) パラメータの値を正しいドライブの場所に変更します。
1. Session(&quot;DBPath&quot;) パラメーターの値を変更し、認証に必要な情報が格納されているデータベースへのパスを反映します [!DNL Report Portal] ユーザー。 ドライブ文字は含めないで、末尾にスラッシュを含めてください。

   例：[!DNL /Inetpub/wwwroot/Portal/data/]

1. ファイルを保存します。
1. 次の手順で [!DNL Report Portal] ファイルは正しくインストールされ、指定された仮想ディレクトリを通じてアクセスできるようになりました。ブラウザーで次のページを開きます。

   https://*YourServerAddress*/*YourPortalName*

   例：[!DNL https://localhost/VisualReportPortal]

   この [!DNL Report Portal] ASP が正しくインストールされている場合は、ポータルのログインページが表示されます。 このページが表示されない場合は、IIS で ASP が有効になっていることを確認し、仮想ディレクトリのマッピングを再度確認してください。
