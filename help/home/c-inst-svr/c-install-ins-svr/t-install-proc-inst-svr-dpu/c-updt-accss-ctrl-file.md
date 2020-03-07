---
description: Access Control.cfgファイルは、Insightサーバーの特定の機能へのアクセスを管理します。
solution: Insight
title: アクセス制御ファイルの更新
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# アクセス制御ファイルの更新{#updating-the-access-control-file}

Access Control.cfgファイルは、Insightサーバーの特定の機能へのアクセスを管理します。

AccessGroupsと呼ばれるエンティティを定義します。 AccessGroupは、サーバーの特定の機能を使用する権限を持つユーザーのグループを識別します。

に接続する前に、Adobeが組織に発 [!DNL Insight Server] 行し [!DNL Insight]たライセンスの1つを含めるように、Administrators AccessGroupを更新する [!DNL Insight] 必要があります。 このAccessGroupは、を通じて管理機能を実行する権限を持つユーザーを識別しま [!DNL Insight]す。

次の手順では、Administrators AccessGroupにライセンスを追加する方法を説明します。 このタスクを完了するには、組織の管理者権限を持つラ [!DNL Insight] イセンスを決定する必要があります。 (初期のセットアップと設定では、1つのライセンスに管理者権限を付与すれば十分です。 後で追加のライセンスに管理者権限を付与できます)。また、このライセンスに割り当てられている「共通名」も知っている必要があります。 この値を取得するには、https://aap.adobe.comでアカウントのライセンス証明書を確認し [ます](https://aap.adobe.com)。

この手順の目的は、最初に設定および設定に使用できるのライセンス [!DNL Insight] 済みのコピーを特定することにありま [!DNL Insight Server]す。 このライセンスを特定したら、のライセンスされたコピーを使用して、以降のすべてのサーバー設定（追加のAccessGroup設定を含む）を実行できま [!DNL Insight]す。 AccessGroupsを使用してサーバーへのアクセスを制御する方法の詳細については、「アクセス制御の設定」 [を参照してくださ](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)い。

**アクセス制御ファイルを更新するには**

1. インストールしたデ [!DNL Access Control] ィレクトリ内のフォルダに移動しま [!DNL Insight Server]す。

   例：[!DNL C:\Adobe\Server\Access Control]

1. ファイルをメモ [!DNL Access Control.cfg] 帳などのテキストエディターで開きます。
1. Administrators AccessGroupでCNエントリを探し、このエントリの既存の値を、最初に設定および管理に使用するCNを識別する共通名 [!DNL Insight] で置き換えます [!DNL Insight Server]。 次のファイルフラグメントは、ファイル内の共通名の挿入場所を示し [!DNL Access Control.cfg] ています。

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   ```

   秘密鍵証明書ベースの認証を使用している場合は、設定に追加のエントリがいくつか使用できます。 次のエントリが含まれます。

   * O（組織ID）:このエントリは、組織のIDを表します。 例：`1 = string: O:46F582D4582596B40A45491@ExampleOrg`。このIDは、管理コンソールで確認できます。
   * PLC — このエントリを使用すると、特定の製品設定用にプロビジョニングされたユーザにアクセスできます。 形式で使用できます `Organization_Id-PLC`。 例：`1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。PLCを使用してData Workbench用にプロビジョニングされたユーザーは、自 `DataworkbenchAdminUsers` 分のサーバー上でアクセスできます。
   * 電子メール — このエントリを使用すると、任意の個々のユーザーにアクセスできます。 この値は、プロビジョニングされたユーザーの電子メールアドレスである必要があります。 例：`1 = string: Email:kim@exampleorg.com`。
   >[!NOTE]
   >
   >
   >    
   >    
   >    * エントリでは大文字と小文字が区別されます。 [O]、[PLC]、[電子メール]に指定した値が、管理コンソールに表示される値と完全に同じであることを確認する必要があります。
   >    * 共通名は、証明書に表示されるとおりに入力します。
   >    * Tabキーを使用して、ファイル(またはアドビのコンポーネ [!DNL Access Control.cfg] ント用の他の設定ファイル)に空白を生成しないでください。 空白文字を作成するには、スペースのみを使用します。 タブ文字を使用すると、システムがファイルを正しく読み取れなくなります。


1. ファイルを保存して閉じます。

