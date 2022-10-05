---
description: Access Control.cfg ファイルは、Insight サーバーの特定の機能へのアクセスを管理します。
title: アクセス制御ファイルの更新
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 4%

---

# アクセス制御ファイルの更新{#updating-the-access-control-file}

{{eol}}

Access Control.cfg ファイルは、Insight サーバーの特定の機能へのアクセスを管理します。

AccessGroups と呼ばれるエンティティを定義します。 AccessGroup は、サーバーの特定の機能を使用する権限を持つユーザーのグループを識別します。

接続する前に [!DNL Insight Server] と [!DNL Insight]の場合は、管理者 AccessGroup を更新して、 [!DNL Insight] 組織に対してAdobeが発行したライセンス。 この AccessGroup は、 [!DNL Insight].

次の手順では、Administrators AccessGroup にライセンスを追加する方法を説明します。 このタスクを完了するには、次のタスクを決定する必要があります [!DNL Insight] ライセンスには、組織の管理者権限があります。 ( 初期のセットアップおよび設定の場合、1 つのライセンスに管理者権限を付与するだけで十分です。 追加のライセンスには、後で管理権限を付与することができます )。 また、このライセンスに割り当てられている「共通名」を知る必要があります。 この値を取得するには、次の場所でアカウントのライセンス証明書を確認します。 [https://aap.adobe.com](https://aap.adobe.com).

この手順の目的は、単にのライセンスが必要なコピーを特定することです。 [!DNL Insight] を使用して、最初にをセットアップおよび設定できます。 [!DNL Insight Server]. このライセンスを特定したら、のライセンスコピーを使用して、以降のすべてのサーバ設定（追加の AccessGroup 設定を含む）を実行できます。 [!DNL Insight]. AccessGroups を使用したサーバーへのアクセス制御の詳細については、 [アクセス制御の設定](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**アクセス制御ファイルを更新するには**

1. 次に移動： [!DNL Access Control] をインストールしたディレクトリ内のフォルダー [!DNL Insight Server].

   例：[!DNL C:\Adobe\Server\Access Control]

1. を開きます。 [!DNL Access Control.cfg] ファイルをメモ帳などのテキストエディターで作成します。
1. Administrators AccessGroup で CN エントリを探し、このエントリの既存の値を、 [!DNL Insight] を使用して、最初にを設定および管理します。 [!DNL Insight Server]. 次のファイルフラグメントは、 [!DNL Access Control.cfg] ファイル。

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

   資格情報ベースの認証を使用している場合は、設定用に追加のエントリがいくつか使用できます。 次のエントリが含まれます。

   * O（組織 ID）:このエントリは、組織の ID を表します。 例：`1 = string: O:46F582D4582596B40A45491@ExampleOrg`。この ID は、Admin Consoleにあります。
   * PLC — このエントリを使用すると、特定の製品設定用にプロビジョニングされたユーザーにアクセスできます。 形式で使用できます `Organization_Id-PLC`. 例：`1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`。PLC を使用したData Workbench用にプロビジョニングされたユーザ `DataworkbenchAdminUsers` が自分のサーバーでアクセスできるようになります。
   * 電子メール — 個々のユーザーにアクセスできます。 値は、プロビジョニングされたユーザーの電子メールアドレスにする必要があります。 例：`1 = string: Email:kim@exampleorg.com`。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * エントリでは大文字と小文字が区別されます。 O、PLC、電子メールに指定した値が、Admin Consoleに表示される値と完全に同じであることを確認する必要があります。
   >    * 証明書に表示されるとおりに、共通名を入力します。
   >    * Tab キーを使用して [!DNL Access Control.cfg] ファイル ( またはAdobe・コンポーネントの他の設定ファイル内 ) スペースのみを使用して、空白を作成します。 タブ文字を使用すると、システムがファイルを正しく読み取れなくなります。


1. ファイルを保存して閉じます。
