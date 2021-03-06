---
description: ユーザーがReport Portalにアクセスするには、有効なアカウントを持ち、アカウント名とパスワードを入力する必要があります。
title: 追加アカウントの定義
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# 追加アカウントの定義

ユーザーがReport Portalにアクセスするには、有効なアカウントを持ち、アカウント名とパスワードを入力する必要があります。

デフォルトでは、[!DNL Report Portal]でユーザー認証が有効になっています。

[!DNL Report Portal]の有効なアカウントのリストは、データベースファイル[!DNL portal.mdb]に保持されます。 [!DNL Report Portal] は、1つのアカウントで管理権限を持つとインストールされます。

* アカウント名：テスト
* パスワード：ユーザー

>[!NOTE]
>
>セキュリティ上の理由から、Adobeでは、[!DNL Report Portal]をインストールした後にこのアカウントのパスワードを変更することをお勧めします。

ユーザーアカウントを[!DNL Report Portal]に追加したり、既存のアカウントに関する情報を変更したりするには、[!DNL Report Portal]ユーザーインターフェイスの「[!DNL Admin]」タブを使用します。

新しいアカウントを追加したり、既存のアカウントを編集したりするたびに、\*PortalName*\PortalASPフォルダーの[!DNL email.asp]ファイルに指定された確認電子メールが送信されます。 詳しくは、[Email.aspファイルの編集](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)を参照してください。

ユーザーを追加する手順については、[アカウントの操作](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)を参照してください。

>[!NOTE]
>
>オプションで、ユーザー認証を無効にし、[!DNL Report Portal]への匿名アクセスを許可できます。 その手順については、[セッション設定ファイルの編集](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)のSession(&quot;In&quot;)パラメーターに関する情報を参照してください。
