---
description: Access Control.cfgファイルは、Insightサーバーの特定の機能へのアクセスを管理します。
title: アクセス制御ファイルの更新
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 4%

---

# アクセス制御ファイルの更新{#updating-the-access-control-file}

Access Control.cfgファイルは、Insightサーバーの特定の機能へのアクセスを管理します。

AccessGroupsと呼ばれるエンティティを定義します。 AccessGroupは、サーバーの特定の機能を使用する権限を持つユーザーのグループを識別します。

[!DNL Insight]を使用して[!DNL Insight Server]に接続する前に、AdobeAccessGroupを更新して、組織に対して発行した[!DNL Insight]ライセンスの1つを含める必要があります。 このAccessGroupは、[!DNL Insight]を介して管理機能を実行する権限を持つユーザーを識別します。

次の手順では、管理者アクセスグループにライセンスを追加する方法を説明します。 このタスクを完了するには、組織の管理者権限を持つ[!DNL Insight]ライセンスを決定する必要があります。 (初期設定と設定を初期化する場合は、1つのライセンスに管理者権限を付与すれば十分です。 後で追加のライセンスに管理者権限を付与することができます)。 また、このライセンスに割り当てられている「共通名」も知っておく必要があります。 この値を取得するには、[https://aap.adobe.com](https://aap.adobe.com)で、アカウントのライセンス証明書を確認します。

この手順の目的は、[!DNL Insight]のライセンスが必要なコピーを特定し、最初に[!DNL Insight Server]を設定して設定することです。 このライセンスを特定したら、[!DNL Insight]のライセンスコピーを使用して、以降のすべてのサーバー設定（追加のAccessGroup設定を含む）を実行できます。 AccessGroupsを使用したサーバーへのアクセス制御の詳細については、[Configuring Access Control](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)を参照してください。

**アクセス制御ファイルを更新するには**

1. [!DNL Insight Server]をインストールしたディレクトリ内の[!DNL Access Control]フォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Access Control]

1. [!DNL Access Control.cfg]ファイルをメモ帳などのテキストエディターで開きます。
1. Administrators AccessGroupでCNエントリを探し、このエントリの既存の値を、最初に[!DNL Insight Server]を設定および管理するために使用する[!DNL Insight]を識別する共通名に置き換えます。 次のファイルフラグメントは、[!DNL Access Control.cfg]ファイル内の共通名を挿入する場所を示しています。

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

   資格情報ベースの認証を使用している場合は、設定用に追加のエントリがいくつか使用できます。 次のエントリがあります。

   * O（組織ID）:このエントリは、組織のIDを表します。 例： `1 = string: O:46F582D4582596B40A45491@ExampleOrg`。このIDは、Admin Consoleで確認できます。
   * PLC — このエントリを使用すると、特定の製品構成用にプロビジョニングされたユーザーにアクセスできます。 形式`Organization_Id-PLC`で使用できます。 例： `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。PLC `DataworkbenchAdminUsers`を使用してData Workbench用にプロビジョニングされたユーザーは、サーバーにアクセスできます。
   * 電子メール — 個々のユーザーにアクセスできます。 値は、プロビジョニングされたユーザーの電子メールアドレスにする必要があります。 例：`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * これらのエントリでは大文字と小文字が区別されます。 [O]、[PLC]、および[電子メール]に指定した値が、Admin Consoleに表示される値と完全に同じであることを確認する必要があります。
   >    * 共通名を、証明書に表示されるとおりに入力します。
   >    * [!DNL Access Control.cfg]ファイル(またはAdobeコンポーネント用の他の設定ファイル)に空白を生成する場合は、Tabキーを使用しないでください。 空白のみを使用して、空白を作成します。 タブ文字は、システムがファイルを正しく読み取るのを防ぎます。


1. ファイルを保存して閉じます。
