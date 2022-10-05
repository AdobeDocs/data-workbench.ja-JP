---
description: クライアントとサーバー間の通信において、パスワードやその他の文字列を暗号化します。
title: 文字列の暗号化
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
exl-id: 43696ff1-3153-4d85-b9a9-c2752dd2c29a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 75%

---

# 文字列の暗号化{#string-encryption}

{{eol}}

クライアントとサーバー間の通信において、パスワードやその他の文字列を暗号化します。

Data Workbench のクライアント（ワークステーション）とサーバー間の通信においては、Value パラメーター（パスワードなど）を *EncryptedString* タイプで保存することができます。これにより、パラメーターが非表示になり、文字列が *Windows 資格情報ストア* を返します。 この機能は、主としてエクスポート内に資格情報を格納するとき使用しますが、任意のパラメーターの暗号化に使用することもできます。

* 新しいフォルダがサーバに追加されました\**EncryptStrings**.

   これは、文字列を暗号化するための設定ファイルを指定する場所です。

* 新しい設定ファイルが Server\Component\*に追加されました&#x200B;*EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   このファイルは、 *サーバー*&#x200B;暗号化設定ファイル用の\*EncryptStrings*フォルダー。

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

1. 保存する **EncryptedStrings.cfg** ファイルをサーバに送信します\**EncryptStrings**フォルダー。

**出力ファイル**

入力ファイルと同じ名前に拡張子を付加した、&lt;*filename*>.*encrypted* という名前の出力ファイルが生成されます。例えば、入力ファイルの名前が *sample.cfg* であれば、出力ファイルの名前は *sample.cfg.encrypted* になります。
