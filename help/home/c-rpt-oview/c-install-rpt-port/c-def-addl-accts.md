---
description: ユーザーがレポートポータルにアクセスするには、有効なアカウントを持ち、アカウント名とパスワードを入力する必要があります。
solution: Analytics
title: 追加のアカウントの定義
topic: Data workbench
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
translation-type: tm+mt
source-git-commit: e4f2c653c00c21180b14bf67cc116d832bddd028

---


# 追加のアカウントの定義

ユーザーがレポートポータルにアクセスするには、有効なアカウントを持ち、アカウント名とパスワードを入力する必要があります。

デフォルトでは、ではユーザー認証が有効になっていま [!DNL Report Portal]す。

の有効なアカウントのリストは、 [!DNL Report Portal] データベースファイルに保持されま [!DNL portal.mdb]す。 [!DNL Report Portal] は、1つのアカウントに管理権限を持つユーザーと共にインストールされます。

* アカウント名：テスト
* パスワード：user

>[!NOTE]
>
>セキュリティ上の理由から、インストール後にこのアカウントのパスワードを変更することをお勧めしま [!DNL Report Portal]す。

既存のアカウントに関する情 [!DNL Report Portal] 報を追加または変更するには、ユーザーインターフェイスの [!DNL Admin] タブを使用 [!DNL Report Portal] します。

新しいアカウントを追加したり、既存のアカウントを編集したりするたびに、\*PortalName*\PortalASPフォルダー内のファイルで指定され [!DNL email.asp] た確認の電子メールが送信されます。 詳しくは、「Email.aspファ [イルの編集」を参照してください](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)。

追加のユーザーを追加する手順については、「アカウントの [操作」を参照してくださ](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)い。

>[!NOTE]
>
>オプションで、ユーザー認証を無効にし、匿名アクセスを許可することができま [!DNL Report Portal]す。 その手順については、「セッション設定ファイルの編集」のSession(&quot;In&quot;)パラメーターに関する情 [報を参照してください](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)。

