---
description: Report Portal は、global.asa という設定ファイルに含まれる情報を使用して、ユーザーセッションを初期化します。
title: セッション設定ファイルの編集
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# セッション設定ファイルの編集{#edit-the-session-configuration-file}

Report Portal は、global.asa という設定ファイルに含まれる情報を使用して、ユーザーセッションを初期化します。

[!DNL Report Portal] をインストールする場合は、このファイルを指示に従って編集する必要があります。 [!DNL global.asa] ファイルは\*PortalName*\PortalASP\ folderディレクトリにあります。

>[!NOTE]
>
>この設定ファイル内の他のパラメーターは変更しないでください。

1. IIS を実行しているマシン上で、[!DNL global.asa] ファイルをメモ帳などのテキストエディターで開きます。
1. （オプション。ユーザーが認証を行わずに [!DNL Report Portal] にアクセスできるようにするには、Session(&quot;In&quot;) パラメータ値を true に変更します。 デフォルト値は false で、[!DNL Report Portal] へのアクセスを試みたすべてのユーザーを認証します。
1. [!DNL Report Portal] が C ドライブ以外のドライブにインストールされている場合は、Session(&quot;Drive&quot;) パラメータの値を正しいドライブの場所に変更します。
1. Session(&quot;DBPath&quot;) パラメーターの値を変更して、[!DNL Report Portal] ユーザーの認証に必要な情報が格納されているデータベースへのパスを反映します。 ドライブ文字は含めないでください。ただし、末尾にスラッシュを含めてください。

   例：[!DNL /Inetpub/wwwroot/Portal/data/]

1. ファイルを保存します。
1. [!DNL Report Portal] ファイルが正しくインストールされ、指定された仮想ディレクトリを通じてアクセスできることを確認するには、ブラウザーで次のページを開きます。

   https://*YourServerAddress*/*YourPortalName*

   例：[!DNL https://localhost/VisualReportPortal]

   [!DNL Report Portal] ASP が正しくインストールされている場合は、ポータルのログインページが表示されます。 このページが表示されない場合は、IIS で ASP が有効になっていることを確認し、仮想ディレクトリのマッピングを再度確認してください。
