---
description: ユーザーが Report Portal にアクセスするには、有効なアカウントを持ち、アカウント名とパスワードを入力する必要があります。
title: 追加アカウントの定義
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# 追加アカウントの定義

{{eol}}

ユーザーが Report Portal にアクセスするには、有効なアカウントを持ち、アカウント名とパスワードを入力する必要があります。

デフォルトでは、ユーザー認証は [!DNL Report Portal].

有効なアカウントのリスト： [!DNL Report Portal] は、データベースファイル内に保持されます。 [!DNL portal.mdb]. [!DNL Report Portal] は、1 つのアカウントで管理者権限を持つようにインストールされます。

* アカウント名：テスト
* パスワード：ユーザー

>[!NOTE]
>
>セキュリティ上の理由から、Adobeでは、をインストールした後にこのアカウントのパスワードを変更することをお勧めします [!DNL Report Portal].

ユーザーアカウントをに追加するには [!DNL Report Portal] 既存のアカウントに関する情報を変更する場合は、 [!DNL Admin] タブ [!DNL Report Portal] ユーザーインターフェイス。

新しいアカウントを追加したり、既存のアカウントを編集したりするたびに、 [!DNL email.asp] ファイルを\*PortalName*\PortalASP フォルダーに保存します。 詳しくは、 [Email.asp ファイルの編集](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

ユーザーを追加する手順については、 [アカウントの操作](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>オプションで、ユーザー認証を無効にし、への匿名アクセスを許可できます。 [!DNL Report Portal]. その手順については、 [セッション構成ファイルの編集](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
