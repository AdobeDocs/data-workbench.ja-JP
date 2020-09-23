---
description: マスターInsightサーバー上のクラスターの設定、クラスターのアクセス制御ファイルの更新などに関する情報です。
solution: Analytics
title: マスター Insight サーバーのクラスタリング用の設定
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---


# マスター Insight サーバーのクラスタリング用の設定{#configuring-the-master-insight-server-for-clustering}

マスターInsightサーバー上のクラスターの設定、クラスターのアクセス制御ファイルの更新などに関する情報です。

クラスターを設定するには、マスターで次の手順を実行し [!DNL Insight Server]ます。

* アド追加レスファイルに対する処理 [!DNL Insight Servers’] 共通名とアドレス。
* フ追加ァイル内のCluster Serversグループ [!DNL Insight Servers] に対するすべての [!DNL Access Control.cfg] もの。

* Components for Processing Serversディレクトリ内の [!DNL Synchronize.cfg] ファイルを更新して、マスターを指定し [!DNL Insight Server]ます。

* 必要に応じて、Components for Processing Serversディレクトリの [!DNL Disk Files.cfg] ファイルを変更し、処理上の [!DNL temp.db] ファイルの場所を指定 [!DNL Insight Servers]します。

これらの手順を実行するには、(個々のデジタル証明書で指定された [!DNL Insight Server])共通名と、クラスター内の各IPアドレス [!DNL Insight Server] を把握しておく必要があります。 この情報がまだない場合は、取得してから先に進んでください。

>[!NOTE]
>
>この節で説明する手順は必須で [!DNL Insight]す。 をインストールしていない場合は [!DNL Insight]、「 **[!DNL Insight]ユーザガイド** 」の指示に従って操作を続行します。

## 処理インサイトサーバーのアドレスファイルへの追加 {#section-2fe5298180164e8dbaa59ea6b6ff682d}

処理の [!DNL Insight Servers’] 共通名とIPアドレスをマスター上のアドレスファイルに追加するには、次の手順を実行し [!DNL Insight Server]ます。 (アドレスファイルはマスター上で管理および管理されますが [!DNL Insight Server]、クラスター内のすべて [!DNL Insight Servers] のユーザーが使用します)。

>[!NOTE]
>
>次の例では、アドレスファイルが既にマスター用に構成されていることを前提としてい [!DNL Insight Server]ます。 マスター [!DNL Insight Server’s] IPアドレスをアドレスファイルにまだ追加していない場合は、開始する前に、「サーバーのネットワーク位置の [定義](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) 」で説明されている手順を実行します。

**処理をアドレスファイル[!DNL Insight Servers]に追加するには**

1. タイトルバーを右クリックし、 [!DNL Insight] /をクリックして、設定プロファイルを開始して読み込みます（まだ開いていない場合） **[!UICONTROL Switch Profile]****[!UICONTROL Configuration]**。

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。

1. マスターのアイコンを右クリックし、 **[!UICONTROL Insight Server]** をクリックし **[!UICONTROL Server Files]**&#x200B;ます。

1. で、Addressesディレクトリ [!DNL Server Files Manager]を開き、次の手順を実行して [!DNL Insight Server’s] アドレスファイルを開きます。

   1. サー *バー名* 列のチェックマークを右クリックし、をクリックし **[!UICONTROL Make Local]**&#x200B;ます。

   1. 列のチェックマークを右クリックし、 [!DNL Temp] 「>」をクリックし **[!UICONTROL Open]** ま **[!UICONTROL in Insight]**&#x200B;す。

1. 構造の内容を展開し、NetworkLocation 0、Addresses、およびAddressDefinitionを展開し [!DNL Locations] ます。
1. 次の手順を実行して、クラスター内の各処理のNetworkLocation 0にAddressDefinitionを追加 [!DNL Insight Server] します。

   1. 右クリック **[!UICONTROL AddressDefinition]** し、「>」をクリックし **[!UICONTROL Add New]** ま **[!UICONTROL Address Definition]**&#x200B;す。

   1. Nameパラメーターで、処理の [!DNL Insight Server’s] 共通名を指定します。
   1. Addressパラメーターで、処理 [!DNL Insight Server’s] IPアドレスを指定します。

      「アドレス」フィールドでは、ワイルドカードとしてアスタリスク（10.10.116など）を使用できます。*)を使用して、クラスタリングを簡略化できます。 See [Understanding Access Levels](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      次の例では、2つのクラスターを定義し [!DNL Insight Servers]ます。

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. サーバーが複数のネットワークに接続されている場合は、手順6を繰り返して、それらのネットワークのNetworkLocations [!DNL Insight Servers] に処理を追加します。

   次の例は、2つのネットワーク（「企業イントラネット」と「インターネット」）に4つのクラスタが [!DNL Insight Servers] 接続されている状態を示しています。

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. で、列内 [!DNL Server Files Manager]のファイルのチェックマークを右クリックし、 [!DNL Temp] / **[!UICONTROL Save to]** &lt; *>を選択します&#x200B;**[!UICONTROL server name]***。

## クラスターのアクセス制御ファイルの更新 {#section-fce1367d92a445168c35e9ca506e7d6b}

クラスター [!DNL Insight Servers] で使用するには、クラスター [!DNL Insight Server] 内の各（マスターを含む）がCluster Serversアクセス制御グループに属している必要があ [!DNL Insight Server]ります。 Cluster Serversグループは、クラスターに参加できるサーバーを（IPアドレスで）識別します。 このファイルはマスター上で管理および管理されますが [!DNL Insight Server]、クラスター内のすべてのユーザー [!DNL Insight Servers] が使用します。

**アクセス制御ファイルを編集するには**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。

1. マスターのアイコンを右クリックし、 [!DNL Insight Server] をクリックし **[!UICONTROL Server Files]**&#x200B;ます。

1. で、アクセス制御ディレクトリ [!DNL Server Files Manager]を開きます。
1. 次の手順を実行して [!DNL Access Control.cfg] ファイルを開きます。

   1. サー *バー名* 列のチェックマークを右クリックし、をクリックし **[!UICONTROL Make Local]**&#x200B;ます。

   1. 列のチェックマークを右クリックし、 [!DNL Temp] 「>」をクリックし **[!UICONTROL Open]** ま **[!UICONTROL in Insight]**&#x200B;す。

1. 「アクセス制御グループ」構造を展開し、「AccessGroup (Cluster Servers)」を展開します。
1. クラスター [!DNL Insight Server] 内の（マスターを含む）それぞれに対して、次の操作を [!DNL Insight Server]行います。

   1. 右クリック **[!UICONTROL Members]** し、「>」をクリックし **[!UICONTROL Add New]** ま **[!UICONTROL New Member]**&#x200B;す。

   1. IPアドレス（名前ではなく数値のIPアドレス）を指定します。 [!DNL Insight Server’s] 複数のネットワーク [!DNL Insight Servers] に接続されている場合、このAccessGroupには、クラスター内のサーバー間通信に [!DNL Insight Servers] 使用する内部アドレスのみが含まれている必要があります。

      次に、4つのクラスタのAccessGroup（クラスタサーバ）を示 [!DNL Insight Servers]します。

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. In the [!DNL Server Files Manager], right-click the check mark for the file in the [!DNL Temp] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 同期ファイルの設定 {#section-d23e751771c84da6bab6a34a8db867bc}

次の手順を使用して、 [!DNL Synchronize.cfg] ファイルの中央コピーを設定できます。 このファイルの中央コピーはマスター上に保持され [!DNL Insight Server]ます。 クラスタ [!DNL Insight Servers] ー内の処理によって、マスターとの通信が開始され、このファイルの更新されたコピー [!DNL Insight Server] が取得されます。

マスターの場所は [!DNL Synchronize.cfg] ファイルで指定し [!DNL Insight Server]ます。 また、クラスター内の各処理がマスターから取得した管理ファイル [!DNL Insight Servers] のセットも識別 [!DNL Insight Server]します。 これらのファイルは、開始時にマスターから [!DNL Insight Servers] 自動的にダウンロード [!DNL Insight Server] されます。 また、これらのファイルが変更された場合に、これらのファイルの更新済みコピーをマスターから動的に取得 [!DNL Insight Server] します。

>[!NOTE]
>
>マスターに対して [!DNL Synchronize.cfg] ファイルを設定する場合 [!DNL Insight Server]は、マスター [!DNL Insight Server] 自体はこのファイルを使用しません。 このファイルは、処理でファイルを取得する際に正しく設定さ [!DNL Insight Server] れるように、マスター上で更新 [!DNL Insight Servers] します。

**マスター上のSynchronize.cfgファイルを更新するには[!DNL Insight Server]**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。

1. マスターのアイコンを右クリックし、 [!DNL Insight Server] をクリックし **[!UICONTROL Server Files]**&#x200B;ます。

1. で、For Processing Serversディレクトリ [!DNL Server Files Manager]**[!UICONTROL Components]** を開きます。

1. 次の操作を行って開きま [!DNL Synchronize.cfg]す。

   1. サー *バー名* 列のチェックマークを右クリックし、をクリックし **[!UICONTROL Make Local]**&#x200B;ます。

   1. チェックマークを右クリックし、 [!DNL Temp] 「>」をクリックし **[!UICONTROL Open]** ま **[!UICONTROL in Insight]**&#x200B;す。

1. コンポーネント構造を展開します。
1. Cluster Server Addressパラメーターで、マスター（プライマリ）のIPアドレスを指定し **[!UICONTROL Insight Server]**&#x200B;ます。

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   マスターと処理の間で同期が発生するたびに記録するログを作成するに [!DNL Insight Server][!DNL Insight Servers]は、Enable Synchronization Logパラメーターが「true」に設定されていることを確認します。

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. In [!DNL Server Files Manager], right-click the check mark for the file in the [!DNL Temp] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## データセット（temp.db）の場所の設定{#section-5ec257a4b4c64fb58baec1f12119a822}

デフォルトの場所と異なるディレクトリまたはドライブ内 [!DNL Insight Servers] で処理 [!DNL temp.db] （データセット）を維持する場合、または複数のドライブに分布する場合は、次の手順を実行 [!DNL temp.db] します。

>[!NOTE]
>
>処理はす [!DNL Insight Servers][!DNL Disk Files.cfg]べて同じなので、すべての処理がこのファイルで指定するファイルの場所をサポートしている必要があります。 例えば、Eに [!DNL temp.db] ドライブの場合、クラスター [!DNL Insight Server] 内のすべての処理にE:ドライブ。

**temp.dbの場所を設定するには**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。

1. マスターのアイコンを右クリックし、 [!DNL Insight Server] をクリックし **[!UICONTROL Server Files]**&#x200B;ます。

1. で、ディレクトリ [!DNL Server Files Manager]を開き **[!UICONTROL Components for Processing Servers]** ます。

1. 次の操作を行って開きま [!DNL Disk Files.cfg]す。

   1. サー *バー名* 列のチェックマークを右クリックし、をクリックし **[!UICONTROL Make Local]**&#x200B;ます。

   1. [!DNL Temp]列のチェックマークを右クリックし、「/」をクリックし **[!UICONTROL Open]** ま **[!UICONTROL in Insight]**&#x200B;す。

1. DiskSpaceManagerComponent構造を展開し、[ディスクファイル]リストを展開します。
1. エントリ0を編集して、 [!DNL temp.db] ファイルの場所を変更します。
1. 複数のドライブに分散する場合は、次の手順を使用して追加の各ドライブに追加のエントリを作成します。 [!DNL temp.db]

   1. 右クリック **[!UICONTROL Disk Files]** し、「>」をクリックし **[!UICONTROL Add New]** ま **[!UICONTROL Disk File]**&#x200B;す。

   1. 新しいエントリで、書き込む場所を指定し [!DNL temp.db] ます。
   次の図は、4台のドライブに [!DNL temp.db] 書き込まれています。

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. In [!DNL Server Files Manager], right-click the check mark for the file in the [!DNL Temp] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

