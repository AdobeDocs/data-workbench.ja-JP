---
description: マスターInsightサーバー上のクラスターの設定、クラスターのアクセス制御ファイルの更新などに関する情報です。
title: マスター Insight サーバーのクラスタリング用の設定
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# マスター Insight サーバーのクラスタリング用の設定{#configuring-the-master-insight-server-for-clustering}

マスターInsightサーバー上のクラスターの設定、クラスターのアクセス制御ファイルの更新などに関する情報です。

クラスターを構成するには、マスター[!DNL Insight Server]で次の手順を実行します。

* アド追加レスファイルに対する[!DNL Insight Servers’]共通名とアドレスの処理。
* 追加[!DNL Access Control.cfg]ファイル内のCluster Serversグループに対するすべての[!DNL Insight Servers]。

* Components for Processing Serversディレクトリの[!DNL Synchronize.cfg]ファイルを更新して、マスター[!DNL Insight Server]を指すようにします。

* 必要に応じて、Components for Processing Serversディレクトリの[!DNL Disk Files.cfg]ファイルを変更し、処理[!DNL Insight Servers]上の[!DNL temp.db]ファイルの場所を指定します。

これらの手順を実行するには、（個々の[!DNL Insight Server]のデジタル証明書で指定された）共通名と、クラスター内の各[!DNL Insight Server]のIPアドレスを把握しておく必要があります。 この情報がまだない場合は、取得してから先に進んでください。

>[!NOTE]
>
>この節で説明する手順には[!DNL Insight]が必要です。 [!DNL Insight]をインストールしていない場合は、先に進む前に、『**[!DNL Insight]ユーザガイド**』の説明に従ってください。

## 処理インサイトサーバーのアドレスファイルへの追加{#section-2fe5298180164e8dbaa59ea6b6ff682d}

次の手順を使用して、処理[!DNL Insight Servers’]の共通名とIPアドレスをマスター[!DNL Insight Server]のアドレスファイルに追加します。 （アドレスファイルはマスター[!DNL Insight Server]上で管理され、管理されますが、クラスター内のすべての[!DNL Insight Servers]で使用されます）。

>[!NOTE]
>
>次の例では、アドレスファイルが既にマスター[!DNL Insight Server]用に構成されていることを前提としています。 マスター[!DNL Insight Server’s] IPアドレスをアドレスファイルにまだ追加していない場合は、開始する前に、[サーバーのネットワークの場所を定義する](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)の手順を実行してください。

**処理をアドレスファイル [!DNL Insight Servers] に追加するには**

1. 開始[!DNL Insight]を開き、（まだ開いていない場合は）タイトルバーを右クリックし、**[!UICONTROL Switch Profile]**/**[!UICONTROL Configuration]**&#x200B;をクリックして、設定プロファイルを読み込みます。

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。

1. マスター&#x200B;**[!UICONTROL Insight Server]**&#x200B;のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。

1. [!DNL Server Files Manager]で、Addressesディレクトリを開き、次の手順を実行して[!DNL Insight Server’s]アドレスファイルを開きます。

   1. *server name*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

   1. [!DNL Temp]列のチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。

1. [!DNL Locations]構造の内容を展開し、NetworkLocation 0、Addresses、およびAddressDefinitionを展開します。
1. 次の手順を実行して、クラスター内の各処理[!DNL Insight Server]のNetworkLocation 0にAddressDefinitionを追加します。

   1. **[!UICONTROL AddressDefinition]**&#x200B;を右クリックし、**[!UICONTROL Add New]**/**[!UICONTROL Address Definition]**&#x200B;をクリックします。

   1. Nameパラメーターで、処理[!DNL Insight Server’s]の共通名を指定します。
   1. Addressパラメーターで、処理[!DNL Insight Server’s]のIPアドレスを指定します。

      「アドレス」フィールドでは、ワイルドカードとしてアスタリスク（10.10.116など）を使用できます。*)を使用して、クラスタリングを簡略化できます。 [アクセスレベルについて](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a)を参照してください。

      次の例では、2つの[!DNL Insight Servers]を含むクラスターを定義します。

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. サーバーが複数のネットワークに接続されている場合は、手順6を繰り返して、処理[!DNL Insight Servers]をそれらのネットワークのNetworkLocationsに追加します。

   次の例は、2つのネットワーク（「企業イントラネット」と「インターネット」）に接続された4つの[!DNL Insight Servers]のクラスタを示しています。

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL server name]***&#x200B;を選択します。

## クラスターのアクセス制御ファイルの更新{#section-fce1367d92a445168c35e9ca506e7d6b}

クラスター内で[!DNL Insight Servers]を使用するには、クラスター内の各[!DNL Insight Server]（マスター[!DNL Insight Server]を含む）がCluster Serversアクセス制御グループに属している必要があります。 Cluster Serversグループは、クラスターに参加できるサーバーを（IPアドレスで）識別します。 このファイルはマスター[!DNL Insight Server]上で管理され、管理されますが、クラスター内のすべての[!DNL Insight Servers]で使用されます。

**アクセス制御ファイルを編集するには**

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。

1. マスター[!DNL Insight Server]のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。

1. [!DNL Server Files Manager]で、アクセス制御ディレクトリを開きます。
1. 次の手順を実行して[!DNL Access Control.cfg]ファイルを開きます。

   1. *server name*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

   1. [!DNL Temp]列のチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。

1. 「アクセス制御グループ」構造を展開し、「AccessGroup (Cluster Servers)」を展開します。
1. クラスター内の各[!DNL Insight Server]（マスター[!DNL Insight Server]を含む）に対して、次の操作を行います。

   1. **[!UICONTROL Members]**&#x200B;を右クリックし、**[!UICONTROL Add New]**/**[!UICONTROL New Member]**&#x200B;をクリックします。

   1. [!DNL Insight Server’s] IPアドレス（名前ではなく数値のIPアドレス）を指定します。 [!DNL Insight Servers]が複数のネットワークに接続されている場合、このAccessGroupには、[!DNL Insight Servers]がクラスター内のサーバー間通信に使用する内部アドレスのみを含める必要があります。

      次に、4つの[!DNL Insight Servers]のクラスタのAccessGroup（クラスタサーバ）を示します。

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL server name]***&#x200B;をクリックします。

## 同期ファイルの設定{#section-d23e751771c84da6bab6a34a8db867bc}

[!DNL Synchronize.cfg]ファイルの中央コピーを構成するには、次の手順を実行します。 このファイルの中央コピーはマスター[!DNL Insight Server]に保持されます。 クラスター内の処理[!DNL Insight Servers]は、マスター[!DNL Insight Server]との通信を開始し、このファイルの更新されたコピーを取得します。

[!DNL Synchronize.cfg]ファイルは、マスター[!DNL Insight Server]の場所を指定します。 また、クラスター内の各処理[!DNL Insight Servers]がマスター[!DNL Insight Server]から取得した管理ファイルのセットも識別します。 処理[!DNL Insight Servers]は、開始時にこれらのファイルをマスター[!DNL Insight Server]から自動的にダウンロードします。 また、これらのファイルが変更されると、マスター[!DNL Insight Server]からこれらのファイルの更新済みコピーも動的に取得されます。

>[!NOTE]
>
>マスター[!DNL Insight Server]に[!DNL Synchronize.cfg]ファイルを設定しても、マスター[!DNL Insight Server]自体はこのファイルを使用しません。 このファイルをマスター[!DNL Insight Server]上で更新し、[!DNL Insight Servers]の処理でファイルを取得する際に正しく設定されるようにします。

**マスター上のSynchronize.cfgファイルを更新するには[!DNL Insight Server]**

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。

1. マスター[!DNL Insight Server]のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。

1. [!DNL Server Files Manager]で、「処理サーバー」ディレクトリの&#x200B;**[!UICONTROL Components]**&#x200B;を開きます。

1. [!DNL Synchronize.cfg]を開くには、次の手順を実行します。

   1. *server name*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

   1. [!DNL Temp]チェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。

1. コンポーネント構造を展開します。
1. Cluster Server Addressパラメーターで、マスター（プライマリ） **[!UICONTROL Insight Server]**&#x200B;のIPアドレスを指定します。

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   マスター[!DNL Insight Server]と処理[!DNL Insight Servers]の間で同期が発生するたびに記録するログを作成するには、Enable Synchronization Logパラメーターが「true」に設定されていることを確認します。

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/*&lt;**[!UICONTROL server name]**>*&#x200B;をクリックします。

## データセット（temp.db）の場所の設定{#section-5ec257a4b4c64fb58baec1f12119a822}

[!DNL Insight Servers]処理を[!DNL temp.db] （データセット）をデフォルトの場所とは異なるディレクトリまたはドライブに維持する場合、または[!DNL temp.db]を複数のドライブに分散する場合は、次の手順を実行します。

>[!NOTE]
>
>処理[!DNL Insight Servers]はすべて同じ[!DNL Disk Files.cfg]を共有するので、すべての処理がこのファイルで指定するファイルの場所をサポートしている必要があります。 例えば、Eに[!DNL temp.db]を割り当てる場合：ドライブの場合、クラスター内のすべての処理[!DNL Insight Server]にE:ドライブ。

**temp.dbの場所を設定するには**

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。

1. マスター[!DNL Insight Server]のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。

1. [!DNL Server Files Manager]の&#x200B;**[!UICONTROL Components for Processing Servers]**&#x200B;ディレクトリを開きます。

1. [!DNL Disk Files.cfg]を開くには、次の手順を実行します。

   1. *server name*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

   1. [!DNL Temp]列のチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。

1. DiskSpaceManagerComponent構造を展開し、[ディスクファイル]リストを展開します。
1. エントリ0を編集して[!DNL temp.db]ファイルの場所を変更します。
1. 複数のドライブに[!DNL temp.db]を配布する場合は、次の手順を使用して追加の各ドライブに追加のエントリを作成します。

   1. **[!UICONTROL Disk Files]**&#x200B;を右クリックし、**[!UICONTROL Add New]**/**[!UICONTROL Disk File]**&#x200B;をクリックします。

   1. 新しいエントリで、[!DNL temp.db]を書き込む場所を指定します。
   次の図は、4台のドライブに書き込まれた[!DNL temp.db]を示しています。

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/*&lt;**[!UICONTROL server name]**>*&#x200B;をクリックします。
