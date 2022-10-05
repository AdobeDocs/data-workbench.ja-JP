---
description: FTP プロトコルおよび SFTP プロトコルを使用して、CSV、TSV、セグメントエクスポート、セグメントのヘッダー付きエクスポートで、セグメントファイルをクライアント（ワークステーション）からサーバーにエクスポートできます。
title: S/FTP 配信を使用したセグメントのエクスポート
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
exl-id: 0f1dc0a1-f376-47fb-887c-612a654ed0f0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 80%

---

# S/FTP 配信を使用したセグメントのエクスポート{#export-a-segment-using-s-ftp-delivery}

{{eol}}

FTP プロトコルおよび SFTP プロトコルを使用して、CSV、TSV、セグメントエクスポート、セグメントのヘッダー付きエクスポートで、セグメントファイルをクライアント（ワークステーション）からサーバーにエクスポートできます。

**SFTP/FTP エクスポート設定ファイルの設定**

エクスポート設定を行うため、FTP 接続または SFTP 接続を設定するための 2 つの新しいエクスポート設定ファイルが追加され、サーバーの詳細を FTPServerInfo.cfg ** ファイルから選択したり、資格情報を FTPUserCredentials ** フォルダー（コマンド引数で指定された Server Name に対応）から選択したりできるようになりました。

* **FTPServerInfo.cfg** ファイルを設定します。

   FTP サーバー情報を入力し、ワークステーションから許可される接続リトライ回数を設定します。ワークステーションまたはサーバー ( ) から編集&#x200B; [!DNL Server\Addresses\Export\] **[!DNL FTPServerInfo.cfg]**ファイル。

   ```
   FTP Servers = vector: 1 items 
     0 = ftpServerInfo:  
       Address = string:  
       Name = string:  
       Port = int: 21 
   Connect Retries = vector: 1 items 
     0 = connectServerRetries:  
       Retries = int: 0 
       Server Name = string:
   ```

* **FTPUserCredentials.cfg** ファイルを設定します。

   を使用してサーバーに接続するためのユーザー資格情報を入力&#x200B; [!DNL Server\Admin\Export\] **[!DNL FTPUserCredentials.cfg]**ファイル。 このファイルには、サーバーに接続するために必要なユーザー資格情報が格納されていて、ワークステーション（クライアント）からではなくサーバーからのみ編集できます。

   ```
   FTP User Credentials = vector: 1 items 
     0 = ftpUserCredInfo: 
       User Name = string:  
       User Password = EncryptedString:  
       Server Name = string:  
       Public Key Path = string:  
       Private Key Path = string:  
       Passphrase = EncryptedString:
   ```

   >[!NOTE]
   >
   >認証用に生成する SSH キーの形式が、SSH Keygen コマンドを使用したときに生成される形式と同じであることを確認します。
   >
   >keygen を使用して SSH キーを生成する例は次のとおりです。
   >
   >
   ```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   **FTPUserCredentials.cfg** ファイルには、各種 FTP または SFTP 転送に必要な 6 つのパラメーターがあります。

   1. *ユーザー名*
   1. User Password **
   1. *Server Name*
   1. *Public Key Path*
   1. Private Key Path **
   1. *Passphrase*

   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Protocol </th> 
      <th colname="col2" class="entry"> パラメーター </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>FTP </p> </td> 
      <td colname="col2"> <p>パラメーター 1、2、3 を設定します。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>パスワード認証を使用する SFTP </p> </td> 
      <td colname="col2"> <p>転送でパスワード認証を使用する（コマンド引数に -p）場合は、パラメーター 1、2、3 を設定します。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>鍵認証を使用する SFTP </p> </td> 
      <td colname="col2"> <p>転送で鍵認証を使用する（コマンド引数に -k）場合は、パラメーター 1、2、3、4、5、6 を設定します。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

**FTP および SFTP エクスポートコマンドの設定**

1. エクスポートテーブルを開きます。

   ワークステーションから、詳細テーブル&#x200B;**&#x200B;を右クリックし、CSV、TSV、セグメントエクスポートまたはセグメントのヘッダー付きエクスポートのいずれかのエクスポートタイプを選択します。または、 [!DNL .export] ファイルをコマンドプロンプトから編集します ( [エクスポートするセグメントの設定](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372)) をクリックします。

1. Command ** フィールドを、エクスポート実行形式ファイルを指すように設定します。

   ```
   ExportIntegration.exe
   ```

1. 必要とされるプロトコルと認証に応じて、Command Arguments ** フィールドを以下のように設定します。

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP**（認証にパスワードを使用する場合）

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -p>
   ```

   **SFTP**（認証に鍵を使用する場合）

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -k>
   ```

   ![](assets/SFTP_command_arguments.png)

すべての Command Arguments は必須であり、図のように入力する必要があります。

## 秘密鍵/公開鍵を使用した S/FTP エクスポート {#section-0534424d79a54a47b82594cfa7b3c17f}

秘密鍵および公開鍵を使用して FTP および SFTP エクスポートを実装するには、次のフォルダーに設定ファイルを配置します。

* 場所 **FTPServerInfo.cfg** 内 [!DNL Server/Addresses/Export/] フォルダー。
* 場所 **FTPUserCredentials.cfg** 内 [!DNL Server/Admin/Export/] フォルダー。

次の 6 つのパラメーターが **FTPServerInfo.cfg** に含まれています。

1. *ユーザー名*
1. User Password **
1. *サーバー名*
1. *公開鍵のパス*
1. *Private Key Path --* 次の例のとおり、拡張子なしで設定ファイルに秘密鍵のパスを配置できます。

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *パスフレーズ*

FTP では、パラメータ 1、2、3 を使用します。

転送でパスワード認証が使用される場合、SFTP はパラメーター 1、2、3 を使用します。

キー認証を使用して転送が完了すると、SFTP はすべての 6 つのパラメーターを使用します。認証にキーを使用している場合は次のとおりです。

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

設定ファイルは正しい場所に配置する必要があります。

>[!NOTE]
>
>公開鍵は、 **.pem** ファイルです。フォルダーの場所ではありません。 Cygwin などのアプリケーションから SSH キー生成機能を使用してキーを作成できます（Putty は、サポートされていない .ppk 形式でキーを生成します）。
