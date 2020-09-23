---
description: アクセス制御.cfgファイルは、Insightサーバーの特定の機能へのアクセスを管理します。
solution: Analytics
title: アクセス制御ファイルの更新
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 4%

---


# アクセス制御ファイルの更新{#updating-the-access-control-file}

アクセス制御.cfgファイルは、Insightサーバーの特定の機能へのアクセスを管理します。

AccessGroupsと呼ばれるエンティティを定義します。 AccessGroupは、サーバーの特定の機能を使用する権限を持つユーザーのグループを識別します。

に接続する前に、Administrators AccessGroupを更新して、組織に対してAdobeが発行した [!DNL Insight Server][!DNL Insight][!DNL Insight] ライセンスの1つを含める必要があります。 このAccessGroupは、を通じて管理機能を実行できるユーザーを識別し [!DNL Insight]ます。

次の手順では、Administrators AccessGroupにライセンスを追加する方法を説明します。 このタスクを完了するには、組織の管理者権限を持つ [!DNL Insight] ライセンスを指定する必要があります。 (初回のセットアップおよび設定では、1つのライセンスに管理者権限を付与すれば十分です。 後で追加のライセンスに管理者権限を付与できます)。 また、このライセンスに割り当てられている「共通名」も必要です。 この値を取得するには、https://aap.adobe.comでアカウントのライセンス証明書を確認し [ます](https://aap.adobe.com)。

この手順の目的は、ライセンスを取得したコピーを特定するこ [!DNL Insight] とです。このコピーは、最初に設定および設定に使用でき [!DNL Insight Server]ます。 このライセンスを特定したら、のライセンス済みコピーを使用して、以降のすべてのサーバ設定（追加のAccessGroup設定を含む）を実行でき [!DNL Insight]ます。 AccessGroupsを使用してアクセス制御へのアクセスを制御する方法について詳しくは、サーバーの [設定を参照してください](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)。

**アクセス制御ファイルを更新するには**

1. インストールしたディレクトリ内の [!DNL Access Control] フォルダーに移動し [!DNL Insight Server]ます。

   例：[!DNL C:\Adobe\Server\Access Control]

1. メモ帳などのテキストエディターで [!DNL Access Control.cfg] ファイルを開きます。
1. Administrators AccessGroup内のCNエントリを探し、このエントリの既存の値を、最初に設定および管理する際に使用する共通名 [!DNL Insight] に置き換え [!DNL Insight Server]ます。 次のファイルフラグメントは、フ [!DNL Access Control.cfg] ァイル内の共通名を挿入する場所を示しています。

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

   秘密鍵証明書ベースの認証を使用している場合は、設定用にいくつかの追加のエントリを使用できます。 次のエントリがあります。

   * O（組織ID）:このエントリは、組織のIDを表します。 例： `1 = string: O:46F582D4582596B40A45491@ExampleOrg`。このIDはAdmin Consoleにあります。
   * PLC — このエントリを使用すると、特定の製品設定に対してプロビジョニングされたユーザにアクセスできます。 形式で使用でき `Organization_Id-PLC`ます。 例： `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。PLCを使用してData Workbench用にプロビジョニングされたユーザは、自分のサーバでアクセス `DataworkbenchAdminUsers` できます。
   * 電子メール — このエントリを使用すると、任意の個々のユーザーにアクセスできます。 この値は、プロビジョニングされたユーザーの電子メールアドレスにする必要があります。 例：`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * エントリでは大文字と小文字が区別されます。 O、PLC、電子メールに指定した値が、Admin Consoleに表示されている値と完全に同じであることを確認する必要があります。
   >    * 共通名は、証明書に表示されるとおりに入力します。
   >    * ファイル(またはAdobeコンポーネント用の他の設定ファイル)内で、Tabキーを使用して [!DNL Access Control.cfg] 空白を生成しないでください。 空白文字を作成するには、スペースのみを使用します。 タブ文字を使用すると、システムはファイルを正しく読み取れません。


1. ファイルを保存して閉じます。

