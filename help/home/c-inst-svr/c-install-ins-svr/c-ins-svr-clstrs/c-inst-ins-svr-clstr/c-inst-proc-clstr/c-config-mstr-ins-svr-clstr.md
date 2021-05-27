---
description: Insightサーバー上でのマスターの設定、クラスターのアクセス制御ファイルの更新などに関する情報です。
title: マスター Insight サーバーのクラスタリング用の設定
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# マスター Insight サーバーのクラスタリング用の設定{#configuring-the-master-insight-server-for-clustering}

Insightサーバー上でのマスターの設定、クラスターのアクセス制御ファイルの更新などに関する情報です。

クラスターを構成するには、マスター[!DNL Insight Server]で次の手順を実行します。

* 処理[!DNL Insight Servers’]の共通名とアドレスをアドレスファイルに追加します。
* [!DNL Insight Servers]を[!DNL Access Control.cfg]ファイル内のCluster Serversグループにすべて追加します。

* マスター[!DNL Insight Server]を指すように、処理サーバー用コンポーネントディレクトリの[!DNL Synchronize.cfg]ファイルを更新します。

* 必要に応じて、Components for Processing Serversディレクトリの[!DNL Disk Files.cfg]ファイルを変更し、処理[!DNL Insight Servers]上の[!DNL temp.db]ファイルの場所を指定します。

これらの手順を完了するには、（個々の[!DNL Insight Server]の電子証明書で指定された）共通名と、クラスター内の各[!DNL Insight Server]のIPアドレスを把握しておく必要があります。 この情報をまだ持っていない場合は、先に進む前に入手してください。

>[!NOTE]
>
>この節で説明する手順には[!DNL Insight]が必要です。 [!DNL Insight]をまだインストールしていない場合は、先に進む前に、『**[!DNL Insight]ユーザーガイド**』の手順に従ってください。

## アドレスファイル{#section-2fe5298180164e8dbaa59ea6b6ff682d}への処理インサイトサーバーの追加

次の手順を実行して、マスター[!DNL Insight Server]のアドレスファイルに処理[!DNL Insight Servers’]の共通名とIPアドレスを追加します。 （アドレスファイルはマスター[!DNL Insight Server]上で管理されますが、クラスター内のすべての[!DNL Insight Servers]で使用されます）。

>[!NOTE]
>
>次の例では、アドレスファイルがマスター[!DNL Insight Server]用に既に設定されていることを前提としています。 マスターの[!DNL Insight Server’s] IPアドレスをアドレスファイルにまだ追加していない場合は、[サーバーのネットワーク位置の定義](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)で説明されている手順を実行してから、作業を開始してください。

**アドレスファイルに処 [!DNL Insight Servers] 理を追加するには**

1. [!DNL Insight]を起動し、タイトルバーを右クリックして&#x200B;**[!UICONTROL Switch Profile]** / **[!UICONTROL Configuration]**&#x200B;をクリックし、設定プロファイルを読み込みます（まだ開いていない場合）。

1. [!DNL Insight]の「[!DNL Admin] > [!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして「サーバーマネージャー」ワークスペースを開きます。

1. マスター&#x200B;**[!UICONTROL Insight Server]**&#x200B;のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。

1. [!DNL Server Files Manager]で、 Addressesディレクトリを開き、次の手順を実行して[!DNL Insight Server’s]アドレスファイルを開きます。

   1. *server name*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

   1. [!DNL Temp]列のチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。

1. [!DNL Locations]構造の内容を展開し、NetworkLocation 0、Addresses、およびAddressDefinitionを展開します。
1. 次の手順を実行して、クラスタ内の各処理[!DNL Insight Server]のNetworkLocation 0にAddressDefinitionを追加します。

   1. **[!UICONTROL AddressDefinition]**&#x200B;を右クリックし、**[!UICONTROL Add New]** / **[!UICONTROL Address Definition]**&#x200B;をクリックします。

   1. 「名前」パラメーターで、処理の[!DNL Insight Server’s]共通名を指定します。
   1. Addressパラメーターに、処理の[!DNL Insight Server’s] IPアドレスを指定します。

      「アドレス」フィールドでは、ワイルドカードとしてアスタリスク(10.10.116など)を使用できます。*：クラスタリングを簡略化します。 [アクセスレベル](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a)についてを参照してください。

      次の例では、2つの[!DNL Insight Servers]を含むクラスターを定義しています。

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. サーバーが複数のネットワークに接続されている場合は、手順6を繰り返して、それらのネットワークのNetworkLocationsに処理[!DNL Insight Servers]を追加します。

   次の例は、2つのネットワーク（「企業イントラネット」と「インターネット」）に接続された4つの[!DNL Insight Servers]のクラスターを示しています。

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]***&#x200B;を選択します。

## クラスター{#section-fce1367d92a445168c35e9ca506e7d6b}のアクセス制御ファイルの更新

クラスターで[!DNL Insight Servers]を使用するには、クラスター内の各[!DNL Insight Server]（マスター[!DNL Insight Server]を含む）がCluster Serversのアクセス制御グループに属している必要があります。 Cluster Serversグループは、クラスターに参加できるサーバーを（IPアドレスで）特定します。 このファイルはマスター[!DNL Insight Server]上で管理されますが、クラスター内のすべての[!DNL Insight Servers]で使用されます。

**アクセス制御ファイルを編集するには**

1. [!DNL Insight]の「[!DNL Admin] > [!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして「サーバーマネージャー」ワークスペースを開きます。

1. マスター[!DNL Insight Server]のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。

1. [!DNL Server Files Manager]で、アクセス制御ディレクトリを開きます。
1. [!DNL Access Control.cfg]ファイルを開くには、次の操作を行います。

   1. *server name*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

   1. [!DNL Temp]列のチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。

1. 「アクセス制御グループ」構造を展開し、「アクセスグループ（クラスターサーバー） 」を展開します。
1. クラスター内の[!DNL Insight Server]（マスター[!DNL Insight Server]を含む）ごとに、次の操作を実行します。

   1. **[!UICONTROL Members]**&#x200B;を右クリックし、**[!UICONTROL Add New]** / **[!UICONTROL New Member]**&#x200B;をクリックします。

   1. [!DNL Insight Server’s] IPアドレス（名前ではなく数値のIPアドレス）を指定します。 [!DNL Insight Servers]が複数のネットワークに接続されている場合、このAccessGroupには、クラスター内のサーバー間通信に[!DNL Insight Servers]が使用する内部アドレスのみを含める必要があります。

      次に、4つの[!DNL Insight Servers]のクラスタのAccessGroup（クラスタサーバ）を示します。

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]***&#x200B;をクリックします。

## 同期ファイルの設定{#section-d23e751771c84da6bab6a34a8db867bc}

次の手順を使用して、[!DNL Synchronize.cfg]ファイルの中央コピーを設定できます。 このファイルの中央コピーは、マスター[!DNL Insight Server]上に保持されます。 クラスター内の処理[!DNL Insight Servers]は、マスター[!DNL Insight Server]との通信を開始し、このファイルの更新されたコピーを取得します。

[!DNL Synchronize.cfg]ファイルは、マスター[!DNL Insight Server]の場所を指定します。 また、クラスタ内の各処理[!DNL Insight Servers]がマスター[!DNL Insight Server]から取得する管理ファイルのセットも識別します。 処理[!DNL Insight Servers]は、これらのファイルが起動すると、マスター[!DNL Insight Server]から自動的にダウンロードします。 また、ファイルが変更されると、マスター[!DNL Insight Server]からこれらのファイルの更新されたコピーが動的に取得されます。

>[!NOTE]
>
>マスター[!DNL Insight Server]に[!DNL Synchronize.cfg]ファイルを設定しても、マスター[!DNL Insight Server]自体はこのファイルを使用しません。 このファイルは、[!DNL Insight Servers]処理でファイルを取得する際に適切に設定されるように、マスター[!DNL Insight Server]で更新します。

**マスター上のSynchronize.cfgファイルを更新するには[!DNL Insight Server]**

1. [!DNL Insight]の「[!DNL Admin] > [!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして「サーバーマネージャー」ワークスペースを開きます。

1. マスター[!DNL Insight Server]のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。

1. [!DNL Server Files Manager]で、「処理サーバー」ディレクトリの&#x200B;**[!UICONTROL Components]**&#x200B;を開きます。

1. [!DNL Synchronize.cfg]を開くには、次の操作を行います。

   1. *server name*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

   1. [!DNL Temp]チェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。

1. コンポーネント構造を展開します。
1. 「Cluster Server Address」パラメーターで、マスター（プライマリ）のIPアドレス(**[!UICONTROL Insight Server]**)を指定します。

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   マスター[!DNL Insight Server]と処理[!DNL Insight Servers]の間で同期がおこなわれるたびに記録するログを作成するには、 Enable Synchronization Logパラメーターが「true」に設定されていることを確認します。

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*&#x200B;をクリックします。

## データセット（temp.db）の場所の設定{#section-5ec257a4b4c64fb58baec1f12119a822}

処理[!DNL Insight Servers]で[!DNL temp.db]（データセット）をデフォルトの場所とは異なるディレクトリまたはドライブに維持する場合、または[!DNL temp.db]を複数のドライブに分散させる場合は、次の手順を実行します。

>[!NOTE]
>
>処理[!DNL Insight Servers]はすべて同じ[!DNL Disk Files.cfg]を共有するので、すべてがこのファイルで指定するファイルの場所をサポートする必要があります。 例えば、Eに[!DNL temp.db]を割り当てると、次のようになります。ドライブに接続する場合、クラスター内のすべての処理[!DNL Insight Server]にEが必要です。ドライブ。

**temp.dbの場所を設定するには**

1. [!DNL Insight]の「[!DNL Admin] > [!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして「サーバーマネージャー」ワークスペースを開きます。

1. マスター[!DNL Insight Server]のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。

1. [!DNL Server Files Manager]で、**[!UICONTROL Components for Processing Servers]**&#x200B;ディレクトリを開きます。

1. [!DNL Disk Files.cfg]を開くには、次の操作を行います。

   1. *server name*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

   1. [!DNL Temp]列のチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。

1. DiskSpaceManagerComponent構造を展開し、[ディスクファイル]リストを展開します。
1. エントリ0を編集して、[!DNL temp.db]ファイルの場所を変更します。
1. 複数のドライブに[!DNL temp.db]を配布する場合は、以下の手順を使用して、追加の各ドライブに対して追加のエントリを作成します。

   1. **[!UICONTROL Disk Files]**&#x200B;を右クリックし、**[!UICONTROL Add New]** / **[!UICONTROL Disk File]**&#x200B;をクリックします。

   1. 新しいエントリで、[!DNL temp.db]を書き込む場所を指定します。
   次の図は、4台のドライブに書き込まれた[!DNL temp.db]を示しています。

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*&#x200B;をクリックします。
