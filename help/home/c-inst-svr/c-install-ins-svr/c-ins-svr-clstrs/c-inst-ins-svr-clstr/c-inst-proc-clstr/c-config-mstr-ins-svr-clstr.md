---
description: マスターInsight サーバー上のクラスターの設定、クラスターのアクセス制御ファイルの更新などに関する情報です。
title: マスター Insight サーバーのクラスタリング用の設定
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# マスター Insight サーバーのクラスタリング用の設定{#configuring-the-master-insight-server-for-clustering}

{{eol}}

マスターInsight サーバー上のクラスターの設定、クラスターのアクセス制御ファイルの更新などに関する情報です。

クラスターを構成するには、マスターで次の手順を実行します [!DNL Insight Server]:

* 処理の追加 [!DNL Insight Servers’] 共通名とアドレスをアドレスファイルに追加します。
* すべての [!DNL Insight Servers] を [!DNL Access Control.cfg] ファイル。

* を更新します。 [!DNL Synchronize.cfg] ファイル（「処理サーバー用コンポーネント」ディレクトリ内）で、マスターを指すように設定します。 [!DNL Insight Server].

* 必要に応じて、 [!DNL Disk Files.cfg] ファイルを作成し、 [!DNL temp.db] 処理中のファイル [!DNL Insight Servers].

これらの手順を完了するには、個々の証明書の電子証明書で指定されている共通名を把握しておく必要があります [!DNL Insight Server]) および各 [!DNL Insight Server] クラスター内で使用します。 この情報がまだない場合は、先に進む前に取得してください。

>[!NOTE]
>
>この項で説明する手順には、が必要です。 [!DNL Insight]. をまだインストールしていない場合 [!DNL Insight]を使用する場合は、 **[!DNL Insight]ユーザーガイド** 先に進む前に

## アドレスファイルへの処理 Insight サーバーの追加 {#section-2fe5298180164e8dbaa59ea6b6ff682d}

次の手順を実行して、処理を追加します。 [!DNL Insight Servers’] マスター上のアドレスファイルに対する共通名と IP アドレス [!DNL Insight Server]. ( ただし、アドレスファイルはマスター上で維持および管理されます。 [!DNL Insight Server]、すべての [!DNL Insight Servers] （クラスタ内）。

>[!NOTE]
>
>次の例では、アドレスファイルが既にマスター用に設定されていることを前提としています [!DNL Insight Server]. マスターをまだ追加していない場合は、 [!DNL Insight Server’s] アドレスファイルへの IP アドレス。 [サーバーのネットワーク位置の定義](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) 始める前に

**処理を追加するには [!DNL Insight Servers] アドレスファイルに**

1. 開始 [!DNL Insight] をクリックし、（まだ開いていない場合は）設定プロファイルを読み込むには、タイトルバーを右クリックし、 **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。

1. マスターのアイコンを右クリックします。 **[!UICONTROL Insight Server]** をクリックし、 **[!UICONTROL Server Files]**.

1. 内 [!DNL Server Files Manager]を開き、 Addresses ディレクトリを開き、以下の操作を実行して、 [!DNL Insight Server’s] アドレスファイル：

   1. チェックマーク ( *サーバー名* 列とクリック **[!UICONTROL Make Local]**.

   1. チェックマーク ( [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. のコンテンツを展開します。 [!DNL Locations] 構造体を展開し、NetworkLocation 0、Addresses、および AddressDefinition を展開します。
1. NetworkLocation 0 に AddressDefinition を処理ごとに追加するには、次の手順を実行します [!DNL Insight Server] クラスター内：

   1. 右クリック **[!UICONTROL AddressDefinition]** をクリックし、 **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. 「名前」パラメーターで、処理を指定します。 [!DNL Insight Server’s] 共通名。
   1. 「アドレス」パラメーターで、処理を指定します [!DNL Insight Server’s] IP アドレス。

      「アドレス」フィールドでは、ワイルドカードとしてアスタリスク ( 例：10.10.116) を使用できます。&#42;を使用して、クラスタリングを簡略化できます。 詳しくは、 [アクセスレベルについて](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      次の例では、2 つの [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. サーバーが複数のネットワークに接続されている場合は、手順 6 を繰り返して処理を追加します [!DNL Insight Servers] を NetworkLocations に追加します。

   次の例は、4 つの [!DNL Insight Servers] 2 つのネットワーク（「企業イントラネット」と「インターネット」）に接続されている。

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列と選択 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## クラスタのアクセス制御ファイルの更新 {#section-fce1367d92a445168c35e9ca506e7d6b}

使用する [!DNL Insight Servers] クラスター内で、 [!DNL Insight Server] クラスター内（マスターを含む） [!DNL Insight Server]) は、Cluster Servers アクセス制御グループに属している必要があります。 Cluster Servers グループは、クラスタへの参加を許可されているサーバを（IP アドレスで）特定します。 このファイルはマスター上で維持および管理されますが、 [!DNL Insight Server]、すべての [!DNL Insight Servers] クラスター内で使用します。

**アクセス制御ファイルを編集するには**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。

1. マスターのアイコンを右クリックします。 [!DNL Insight Server] をクリックし、 **[!UICONTROL Server Files]**.

1. 内 [!DNL Server Files Manager]で、アクセス制御ディレクトリを開きます。
1. 次の操作を実行して、 [!DNL Access Control.cfg] ファイル：

   1. チェックマーク ( *サーバー名* 列とクリック **[!UICONTROL Make Local]**.

   1. チェックマーク ( [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. 「アクセス制御グループ」構造を展開し、「アクセスグループ」(Cluster Servers) を展開します。
1. 各 [!DNL Insight Server] クラスター内（マスターを含む） [!DNL Insight Server])、次の操作を実行します。

   1. 右クリック **[!UICONTROL Members]** をクリックし、 **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. 次を指定： [!DNL Insight Server’s] IP アドレス（名前ではなく数値 IP アドレス）。 この [!DNL Insight Servers] は複数のネットワークに接続されているので、この AccessGroup には、 [!DNL Insight Servers] クラスタ内のサーバー間通信に使用します。

      次に、4 つのクラスタの AccessGroup（クラスタサーバ）を示します [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列とクリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 同期ファイルの設定 {#section-d23e751771c84da6bab6a34a8db867bc}

次の手順を使用して、 [!DNL Synchronize.cfg] ファイル。 このファイルの中央コピーはマスター上に保持されます [!DNL Insight Server]. 処理 [!DNL Insight Servers] クラスタ内でマスターとの通信を開始 [!DNL Insight Server] をクリックして、このファイルの更新されたコピーを取得します。

この [!DNL Synchronize.cfg] ファイルは、マスターの場所を指定します [!DNL Insight Server]. また、各処理で使用される管理ファイルのセットも識別されます [!DNL Insight Servers] クラスター内でマスターから取得します [!DNL Insight Server]. 処理 [!DNL Insight Servers] マスターからこれらのファイルを自動的にダウンロード [!DNL Insight Server] 彼らが始まった時 また、これらのファイルの更新されたコピーをマスターから動的に取得します [!DNL Insight Server] ファイルが変更されたとき。

>[!NOTE]
>
>ただし、 [!DNL Synchronize.cfg] マスター上のファイル [!DNL Insight Server]、マスター [!DNL Insight Server] 自体はこのファイルを使用しません。 このファイルはマスターで更新します [!DNL Insight Server] 処理時に適切に設定されるように [!DNL Insight Servers] ファイルを取得します。

**マスター上の Synchronize.cfg ファイルを更新するには[!DNL Insight Server]**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。

1. マスターのアイコンを右クリックします。 [!DNL Insight Server] をクリックし、 **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager]、 **[!UICONTROL Components]** をクリックします。

1. 次の操作を実行してを開きます。 [!DNL Synchronize.cfg]:

   1. チェックマーク ( *サーバー名* 列とクリック **[!UICONTROL Make Local]**.

   1. を右クリックします。 [!DNL Temp] チェックマークを付け、 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. コンポーネント構造を展開します。
1. Cluster Server Address パラメータで、マスター（プライマリ）の IP アドレスを指定します。 **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   マスター間で同期が実行されるたびに記録するログを作成するには [!DNL Insight Server] および処理 [!DNL Insight Servers]に設定した場合は、Enable Synchronization Log パラメーターが「true」に設定されていることを確認します。

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列とクリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## データセット（temp.db）の場所の設定 {#section-5ec257a4b4c64fb58baec1f12119a822}

処理が必要な場合は、次の手順を実行します [!DNL Insight Servers] 維持する [!DNL temp.db] （データセット）デフォルトの場所とは異なるディレクトリまたはドライブ内の、または配布する場合は [!DNL temp.db] 複数のドライブにまたがる

>[!NOTE]
>
>処理のため [!DNL Insight Servers] すべて同じものを共有する [!DNL Disk Files.cfg]の場合、すべてがこのファイルで指定するファイルの場所をサポートする必要があります。 例えば、 [!DNL temp.db] E:ドライブ、すべての処理 [!DNL Insight Server] クラスター内には E が必要です。ドライブ。

**temp.db の場所を設定するには**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。

1. マスターのアイコンを右クリックします。 [!DNL Insight Server] をクリックし、 **[!UICONTROL Server Files]**.

1. 内 [!DNL Server Files Manager]、 **[!UICONTROL Components for Processing Servers]** ディレクトリ。

1. 次の操作を実行してを開きます。 [!DNL Disk Files.cfg]:

   1. チェックマーク ( *サーバー名* 列とクリック **[!UICONTROL Make Local]**.

   1. チェックマーク ( [!DNL Temp]列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. DiskSpaceManagerComponent 構造を展開し、[ ディスクファイル ] リストを展開します。
1. エントリ 0 を編集して、 [!DNL temp.db] ファイル。
1. 配分する場合 [!DNL temp.db] 複数のドライブにまたがって、以下の手順を使用して、各追加ドライブに追加のエントリを作成します。

   1. 右クリック **[!UICONTROL Disk Files]** をクリックし、 **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. 新しいエントリで、目的の場所を指定します [!DNL temp.db] 書き込まれました。
   以下に示します。 [!DNL temp.db] 4 台のドライブに書き込まれます。

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列とクリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
