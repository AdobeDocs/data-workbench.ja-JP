---
description: アクセス制御.cfgファイルは、Insightサーバーの特定の機能へのアクセスを管理します。
title: アクセス制御ファイルの更新
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 4%

---

# アクセス制御ファイルの更新{#updating-the-access-control-file}

アクセス制御.cfgファイルは、Insightサーバーの特定の機能へのアクセスを管理します。

AccessGroupsと呼ばれるエンティティを定義します。 AccessGroupは、サーバーの特定の機能を使用する権限を持つユーザーのグループを識別します。

[!DNL Insight]を使用して[!DNL Insight Server]に接続する前に、Adobeが組織に発行した[!DNL Insight]ライセンスの1つを含めるようにAdministrators AccessGroupを更新する必要があります。 このAccessGroupは、[!DNL Insight]を介した管理機能の実行を許可されているユーザーを識別します。

次の手順では、Administrators AccessGroupにライセンスを追加する方法を説明します。 このタスクを完了するには、組織の管理者権限を持つ[!DNL Insight]ライセンスを決定する必要があります。 (初回のセットアップおよび設定では、1つのライセンスに管理者権限を付与すれば十分です。 後で追加のライセンスに管理者権限を付与できます)。 また、このライセンスに割り当てられている「共通名」も必要です。 この値を取得するには、[https://aap.adobe.com](https://aap.adobe.com)でアカウントのライセンス証明書を確認します。

この手順の目的は、[!DNL Insight]のライセンスを取得し、[!DNL Insight Server]を最初にセットアップして設定する際に使用できるコピーを特定することです。 このライセンスを特定したら、[!DNL Insight]のライセンスコピーを使用して、以降のすべてのサーバ設定（追加のAccessGroup設定を含む）を実行できます。 AccessGroupsを使用してサーバーへのアクセスを制御する方法について詳しくは、[アクセス制御](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)の設定を参照してください。

**アクセス制御ファイルを更新するには**

1. [!DNL Insight Server]をインストールしたディレクトリの[!DNL Access Control]フォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Access Control]

1. [!DNL Access Control.cfg]ファイルをメモ帳などのテキストエディターで開きます。
1. Administrators AccessGroup内のCNエントリを探し、このエントリの既存の値を、[!DNL Insight Server]の初期設定と管理に使用する[!DNL Insight]を識別する共通名に置き換えます。 次のファイルフラグメントは、[!DNL Access Control.cfg]ファイル内の共通名を挿入する場所を示しています。

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
   * PLC — このエントリを使用すると、特定の製品設定に対してプロビジョニングされたユーザにアクセスできます。 `Organization_Id-PLC`の形式で使用できます。 例： `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。PLC `DataworkbenchAdminUsers`を使用してData Workbench用にプロビジョニングされたユーザーは、自分のサーバーでアクセスできます。
   * 電子メール — このエントリを使用すると、任意の個々のユーザーにアクセスできます。 この値は、プロビジョニングされたユーザーの電子メールアドレスにする必要があります。 例：`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * エントリでは大文字と小文字が区別されます。 O、PLC、電子メールに指定した値が、Admin Consoleに表示されている値と完全に同じであることを確認する必要があります。
   >    * 共通名は、証明書に表示されるとおりに入力します。
   >    * [!DNL Access Control.cfg]ファイル(またはAdobeコンポーネント用の他の設定ファイル)では、Tabキーを使用して空白を生成しないでください。 空白文字を作成するには、スペースのみを使用します。 タブ文字を使用すると、システムはファイルを正しく読み取れません。


1. ファイルを保存して閉じます。
