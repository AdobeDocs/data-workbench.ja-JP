---
description: 'null'
solution: Analytics
title: ユーザーアカウントの追加
topic: Data workbench
uuid: c322eeaa-a3f4-41e8-b38c-dd892ec29a87
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ユーザーアカウントの追加{#adding-a-user-account}

1. をクリッ **[!UICONTROL Add User]** クして、プロンプトを表 **[!UICONTROL New User]** 示します。

   ![](assets/add_user_account.png)

1. 必要なフィールドに入力し、フォームに入力します。
   1. **[!UICONTROL Username]**:ユーザー名を入力します。
   1. **[!UICONTROL Password]**:長さが6文字を超えるパスワードを入力してください。
   1. **[!UICONTROL Confirm Password]**:パスワードを再入力します。
   1. **[!UICONTROL Authentication Method]**:ドロップダウンリストからオプションを選択します。

      | **フォーム** | デフォルトでは、ダッシュボードにはユーザーアカウントが保存され、内部で認証されます。 |
      |---|---|
      | **LDAP** | ユーザーをLDAP経由で認証する場合は、このオプションを選択します。 （ユーザーは既にディレクトリ内に存在する必要があります）。 |
      | **Windows** | ユーザーをWindows認証を使用して認証する場合に選択します（ユーザーがWindowsディレクトリに既に存在している必要があります）。 |

1. **[!UICONTROL Assigned Groups]**:デフォルトのAdministratorsグループと、作成済みの他のグループから選択します。 現時点ではグループは不要で、ユーザーのグループメンバーシップはいつでも変更できます。
1. フォームが適切に設定されたら、をクリックし **[!UICONTROL Add User]** てユーザーをシステムに追加します。

   操作が正常に完了すると、ユーザーが作成されたことを示すプロンプトが表示されます。