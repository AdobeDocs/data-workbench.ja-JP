---
description: ユーザーアカウントの追加
title: ユーザーアカウントの追加
uuid: c322eeaa-a3f4-41e8-b38c-dd892ec29a87
exl-id: c99f3189-4d89-443a-be5b-84352c4ec6e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 8%

---

# ユーザーアカウントの追加{#adding-a-user-account}

1. **[!UICONTROL Add User]**&#x200B;をクリックして、**[!UICONTROL New User]**&#x200B;プロンプトを表示します。

   ![](assets/add_user_account.png)

1. 必要なフィールドに入力し、フォームに入力します。
   1. **[!UICONTROL Username]**:ユーザー名を入力します。
   1. **[!UICONTROL Password]**:6文字を超えるパスワードを入力してください。
   1. **[!UICONTROL Confirm Password]**:パスワードを再入力します。
   1. **[!UICONTROL Authentication Method]**:ドロップダウンリストからオプションを選択します。

      | **フォーム** | デフォルトでは、ダッシュボードにはユーザーアカウントが格納され、内部で認証されます。 |
      |---|---|
      | **LDAP** | ユーザーをLDAPで認証する場合は、このオプションを選択します。 （ユーザーは、ディレクトリ内に既に存在する必要があります）。 |
      | **Windows** | ユーザーをWindows認証を使用して認証する場合に選択します（ユーザーはWindowsディレクトリに既に存在する必要があります）。 |

1. **[!UICONTROL Assigned Groups]**:デフォルトの「管理者」グループと、作成済みのその他のグループから選択します。現時点ではグループは不要で、ユーザーのグループメンバーシップはいつでも変更できます。
1. フォームを適切に設定したら、「**[!UICONTROL Add User]**」をクリックしてユーザーをシステムに追加します。

   操作が成功した場合は、ユーザーが作成されたことを示すプロンプトが表示されます。
