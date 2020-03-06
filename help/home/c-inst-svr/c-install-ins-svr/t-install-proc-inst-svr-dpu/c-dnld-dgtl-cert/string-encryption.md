---
description: クライアントとサーバー間の通信において、パスワードやその他の文字列を暗号化します。
title: 文字列の暗号化
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 文字列の暗号化{#string-encryption}

クライアントとサーバー間の通信において、パスワードやその他の文字列を暗号化します。

Data Workbench のクライアント（ワークステーション）とサーバー間の通信においては、Value パラメーター（パスワードなど）を *EncryptedString* タイプで保存することができます。This hides the parameter and saves the string to the *Windows Credential Store* on the server with the corresponding key returned. この機能は、主としてエクスポート内に資格情報を格納するとき使用しますが、任意のパラメーターの暗号化に使用することもできます。

* A new folder was added at Server\**EncryptStrings**.

   これは、文字列を暗号化するための設定ファイルを指定する場所です。

* A new configuration file was added at Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   This file polls the *Server*\*EncryptStrings* folder for encryption configuration files.

**文字列を暗号化するには**：

1. 暗号化する文字列のために、次のフィールドを含んだ **EncryptedStrings.cfg** 設定ファイルを作成します。

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Value* - このフィールドに、暗号化が必要とされる平文の文字列を格納します。

      これはサーバー側での暗号化専用です。*Value* 設定値の暗号化はサーバーコンピューター上でのみ実行されます。

   * *Name* - このフィールドに、暗号化された文字列を識別するための値を格納します。
   * *EncryptValue* - 入力の設定ファイルでは、このフィールドの値を空のままにしておきます。暗号化済みの値がこのフィールドに返されます。
   複数のフィールドを暗号化するには、フィールドごとに別々の **NameEncryptValuePair** 値を追加します。

   >[!NOTE]
   >
   >すべての空の値フィールドが削除されます。

1. Save the **EncryptedStrings.cfg** file to the Server\**EncryptStrings** folder.

**出力ファイル**

入力ファイルと同じ名前に拡張子を付加した、&lt;*filename*>.*encrypted* という名前の出力ファイルが生成されます。例えば、入力ファイルの名前が *sample.cfg* であれば、出力ファイルの名前は *sample.cfg.encrypted* になります。
