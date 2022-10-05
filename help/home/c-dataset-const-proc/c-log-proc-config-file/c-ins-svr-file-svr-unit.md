---
description: Insight サーバーのファイルサーバーユニットとファイルサーバー設定プロセスについて取り上げます。
title: Data Workbench サーバーのファイルサーバーユニットの設定
uuid: ccb65952-f017-4434-b2f8-74c274450834
exl-id: 19b8c08a-e9f2-47ab-ad9f-1fddfbd9d249
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 66%

---

# Data Workbench サーバーのファイルサーバーユニットの設定{#configuring-a-data-workbench-server-file-server-unit}

{{eol}}

Insight サーバーのファイルサーバーユニットとファイルサーバー設定プロセスについて取り上げます。

<!--
c_abt_file_svr_units.xml
-->

Data Workbench サーバー (InsightServer64.exe) をファイルサーバーユニット (FSU) として実行するように設定するには、 **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** ノード [!DNL Log Processing.cfg] ファイル。 Data Workbench サーバーが FSU として実行するように設定されている場合は、ソースファイル ( [!DNL .vsl] 複数の処理サーバー (DPU) からすばやくアクセスできるファイル、テキストファイル、XML ファイル )。 Data Workbench サーバークラスター内の複数の DPU が FSU にアクセスしてログファイルを読み取るとき、DPU 間でログファイルが分割され、同じファイルが複数回処理されることはありません。

>[!NOTE]
>
>5 ～ 10 個の DPU で構成される Data Workbench サーバークラスターを提供する FSU を設定する場合は、クラスターのマスターサーバーを FSU にする必要があります。

Data Workbench サーバークラスターをインストールする方法について詳しくは、『*サーバー製品のインストールと管理に関するガイド*』を参照してください。

<!--
c_file_svr_config_proc.xml
-->

データセットのログソースが離れた場所にある場合、そのデータを処理する Data Workbench サーバーコンピューターは、指定されたリモートコンピューターに接続してログを読み取ります。

FSU として実行するように指定された Data Workbench サーバーコンピューターは、[!DNL Access Control.cfg] ファイルによって DPU からの接続を受け入れるとともに、[!DNL Communications.cfg] ファイルによってリモートデータファイルの場所をマッピングします。FSU を設定するための作業手順を次に示します。

1. マスター Data Workbench サーバー上の [!DNL Log Processing.cfg] ファイルに、データソースのタイプと場所を指定します。[データソースの指定](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383)を参照してください。

1. FSU 上の [!DNL Access Control.cfg] ファイルで権限を編集し、ログデータを読み取る DPU からの接続を許可します。[ファイルサーバーユニット上の権限の編集](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef)を参照してください。

1. FSU 上の [!DNL Communications.cfg] ファイルで [!DNL LoggingServer] エントリと [!DNL FileServer] エントリの設定を編集し、ログファイルの場所を指定します。[ログファイルの場所の指定](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0)を参照してください。

1. Data Workbench サーバークラスター上で実行するようにデータセットプロファイルを設定する場合はさらに、クラスターの FSU が、そのプロファイルのすべてのディメンションを構築するサーバーとなるように設定する必要があります。（Data Workbench サーバークラスターのみ）FSU 上の [!DNL Communications.cfg] ファイルと [!DNL cluster.cfg] ファイルに「normalize server」のエントリを追加し、すべてのディメンションが構築されるクラスター内のサーバーとして、その FSU を指定します。[クラスターにおける中央の正規化サーバーの作成](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28)を参照してください。

Data Workbench サーバークラスターで処理されるデータセットプロファイルを設定する手順については、『*サーバー製品のインストールと管理に関するガイド*』を参照してください。

>[!NOTE]
>
>次の手順では、すべてのログファイルがデフォルトのディレクトリに存在することを前提としています。 別のディレクトリにログを保管する場合やログのパスを複数設ける必要がある場合は、具体的な設定内容をアドビ システムズ社コンサルティングサービスにご相談ください。

## データソースの指定 {#section-d2b545db7ab142ffb4be32e040395383}

データセットに使用するリモートデータソースを指定するときは、マスター Data Workbench サーバーでデータソースのタイプとログファイルの場所を指定する必要があります。

**データソースとその場所を指定するには**

1. を開きます。 [!DNL Log Processing.cfg] ファイル。 詳しくは、 [ログ処理設定ファイルの編集](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

1. [!DNL Sensor]、ログファイルまたは XML データソースを追加します。詳しくは、 [ログファイル](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Log Paths パラメーターを設定します。詳しくは、 [Sensor ファイル](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009), [ログファイル](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)または [XML ログソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887). 有効な URI を必ず指定してください。

1. 次の表に記載した Log Server のパラメーターを設定します。

<table id="table_5881B8DEFF984BC7A620CEEA3A637912"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> リモートファイルサーバーを識別する名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Server Common Name </td> 
   <td colname="col2"> <p> ファイルサーバーの SSL 証明書にリストされている<span class="wintitle">サーバー共通名</span>。 </p> <p> <span class="wintitle">Use SSL</span> が false に設定されている場合、このパラメーターは省略可能です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> <p>ファイルサーバーコンピューターのアドレス。<span class="wintitle">Name</span> が <span class="wintitle">SSL Server Common Name</span> と同じである場合は空欄で構いません。 </p> <p> 例：<span class="filepath">visual.mycompany.com</span>、192.168.1.90 など </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Data Workbench サーバーコンピューターがファイルサーバーとの通信に使用するポート。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> Data Workbench サーバーに使用する <span class="wintitle">SSL 証明書</span>ファイルの名前（<span class="filepath">server_cert.pem</span>）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use SSL </td> 
   <td colname="col2"> true または false。true は、ファイルサーバーで <span class="wintitle">SSL</span> が使用されていることを示します。 </td> 
  </tr> 
 </tbody> 
</table>

DPU から FSU に接続するためにプロキシサーバーが必要な場合は、次のパラメーターも設定する必要があります。

| パラメーター | 説明 |
|---|---|
| Proxy Address | Data Workbench サーバーがファイルサーバーにアクセスするときに使用するプロキシサーバーのアドレス。 |
| Proxy Password | （オプション）。プロキシサーバーへのパスワード。 |
| Proxy Port | プロキシサーバーのポート。デフォルトは 8080 です。 |
| Proxy User Name | （オプション）。プロキシサーバーのユーザー名。 |

次に、定義済みの [!DNL Log Server] 内 [!DNL Log Processing.cfg] ファイル。 Log Source 1 は LogFile ソースです。その場所として、FSU01 というコンピューター上の Logs というディレクトリ（Log Paths パラメーターに指定された URI に注目）が指定されています。

![](assets/cfg_LogProcessing_LogServer.png)

## ファイルサーバーユニット上の権限の編集 {#section-b4a54b591b4e4435a728a67f194057ef}

従来は、FSU からログファイルを読み取るように特定のデータセットのプロファイルを設定していました。今後は、FSU 上の権限を編集して、プロファイルを実行している DPU からの接続を許可する必要があります。以下の手順で、権限ファイルである [!DNL Access Control.cfg] の編集方法を説明します。

**FSU 上の権限を編集するには**

1. を開きます。 [!DNL Server Files Manager] FSU として設定する data workbench サーバーマシンの場合は、 **[!UICONTROL Access Control]** 内容を表示する。

   を開き、使用する方法については、 [!DNL Server Files Manager]を参照し、 *Data Workbenchユーザーガイド*.

1. 内 [!DNL Server Files Manager] ウィンドウ、クリック **[!UICONTROL Access Control]** 内容を表示する。 [!DNL Access Control.cfg] ファイルは、このディレクトリ内に格納されています。

1. 次のサーバー名列のチェックマークを右クリック [!DNL Access Control.cfg]を選択し、「 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Access Control.cfg].

1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. 内 [!DNL Access Control] ウィンドウ、クリック **[!UICONTROL Access Control Groups]** 内容を表示する。

1. 最後の [!DNL AccessGroup] リスト内で、 **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. を入力します。 [!DNL Name] 新しい [!DNL AccessGroup]. （例：Connecting Servers）。

1. 右クリック **[!UICONTROL Member]** 新しい [!DNL AccessGroup]を選択し、「 **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. このファイルサーバーに接続する、Data Workbench サーバーの DPU の IP アドレスを入力します。
1. ログファイルへのアクセスが必要となるクラスター内の Data Workbench サーバー DPU を含め、この FSU に接続する他の Data Workbench サーバー DPU についても、手順 4 と手順 5 を繰り返します。
1. 右クリック **[!UICONTROL Read-Only Access]** 新しい [!DNL AccessGroup]を選択し、「 **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. ファイルサーバーコンピューター上に保存されるログファイルの場所を入力します。パスの指定にはスラッシュ（/）を使用してください。デフォルトの場所は /Logs/ です。
1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部で、「 **[!UICONTROL Save]**.

1. 内 [!DNL Server Files Manager] ウィンドウで、次のチェックマークを右クリック： [!DNL Access Control.cfg] 内 [!DNL Temp] 列、「 **[!UICONTROL Save to]** > **[!UICONTROL server name]** をクリックして、data workbench サーバーの FSU に対してローカルで行った変更を保存します。

## ログファイルの場所の指定 {#section-f9a649bf1b2544feb10ad8820384edb0}

ログファイルの場所を指定するには、FSU 上の [!DNL Communications.cfg] ファイルを編集する必要があります。

**ログファイルの場所を指定するには**

1. 内 [!DNL Server Files Manager] ウィンドウ、クリック **[!UICONTROL Components]** 内容を表示する。 [!DNL Communications.cfg] ファイルは、このディレクトリ内に格納されています。

1. 次のサーバー名列のチェックマークを右クリック [!DNL Communications.cfg]を選択し、「 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Communications.cfg].

1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. 内 [!DNL Communications.cfg] ウィンドウ、クリック **[!UICONTROL component]** 内容を表示する。

1. 内 [!DNL Communications.cfg] ウィンドウ、クリック **[!UICONTROL Servers]** 内容を表示する。 場合によっては、FileServer、LoggingServer、InitServer、StatusServer、SendServer、ReplicateServer など、複数のサーバーが表示されます。

1. （[!DNL Sensor] ログソースのみ）[!DNL LoggingServer]（Data Workbench サーバーによって処理される [!DNL Sensor] のログファイルが書き込まれる場所）を探し、その番号をクリックしてメニューを表示します。Log Directory パラメーターを編集して、ログファイルの適切な場所を反映します。デフォルトのログディレクトリは、Data Workbench サーバーのインストールディレクトリにある Logs フォルダーです。

   [!DNL LoggingServer] のパラメーター以外は編集しないでください。

   ![](assets/cfg_Communications_LoggingServer.png)

1. ログファイルの場所を指定する FileServer を探します。Servers に複数の FileServer が列挙される場合があるので、目的のサーバーを見つけるには、その内容を順に（サーバー番号をクリックして）確認する必要があります。
1. FileServer の [!DNL Local Path] パラメーターと URI パラメーターを編集して、ログファイルの場所を反映します。次の例では、Data Workbench サーバーのインストールディレクトリ内の Logs フォルダーにログファイルが存在します。

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >この [!DNL Local Path] と URI パラメーターは、図のように入力されます。URI パラメーターは、 [!DNL Logs] 内 [!DNL Server Files Manager].

1. 右クリック **[!UICONTROL (modified)]** 設定ウィンドウの上部にある、「 **[!UICONTROL Save]**.

1. 内 [!DNL Server Files Manager] ウィンドウで、次のチェックマークを右クリック： [!DNL Communications.cfg] 内 [!DNL Temp] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* をクリックして、data workbench サーバーの FSU に対してローカルで行った変更を保存します。

## クラスターにおける中央の正規化サーバーの作成 {#section-2c1f57b683f94cc193bc069e886bba28}

Data Workbench サーバークラスター上で実行するようにデータセットプロファイルを設定する場合は、そのプロファイルのすべてのディメンションを構築するサーバーとして、クラスターの FSU を設定する必要があります。

クラスターの FSU をクラスターのマスターサーバーおよび中央の正規化サーバーとして使用することを強くお勧めします。

FSU を中央の正規化サーバーとして使用するには、その FSU 上の [!DNL Communications.cfg] ファイルと [!DNL Cluster.cfg] ファイルを開いて編集する必要があります。

**FSU を中央の正規化サーバーとして設定するには**

1. を追加します。 [!DNL NormalizeServer] エントリ [!DNL Communications.cfg] ファイルを FSU に貼り付けます。

   >[!NOTE]
   >
   >data workbench サーバー v5.0 以降の完全なリリースパッケージをインストールしている場合は、 [!DNL Communications.cfg] FSU 上のファイルには [!DNL NormalizeServer] エントリは既に存在します。 該当するエントリが存在するかどうかは、以下の手順で確認できます。

   1. [!DNL Communications.cfg]ログファイルの場所の指定[の説明に従い、Data Workbench で ](#section-f9a649bf1b2544feb10ad8820384edb0) ファイルを開きます。

   1. **[!UICONTROL component]** をクリックしてその内容を表示します。
   1. 右クリック **[!UICONTROL Servers]** をクリックし、 **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. の URI パラメーター内 [!DNL NormalizeServer], type [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部で、をクリックします。 **[!UICONTROL Save]**.

   1. 内 [!DNL Server Files Manager] ウィンドウで、次のチェックマークを右クリック： [!DNL Communications.cfg] 内 [!DNL Temp] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>* 名前： data workbench サーバーの FSU に対してローカルに加えた変更を保存します。

1. Data Workbench サーバークラスターのマスターサーバー上にある [!DNL Cluster.cfg] ファイルで中央の正規化サーバーを定義します。

   >[!NOTE]
   >
   >中央の正規化サーバーを設定する FSU が、クラスター内のマスター Data Workbench サーバーではない場合は、クラスター内の DPU の IP アドレスをに追加する必要があります [!DNL Cluster Servers] FSU のアクセスグループ [!DNL Access Control.cfg] ファイル。 [!DNL Cluster Servers] グループにサーバーを追加する手順については、『*サーバー製品のインストールと管理に関するガイド*』の「クラスターのアクセス制御ファイルの更新」の節を参照してください。

   1. を開きます。 [!DNL Profile Manager] データセットプロファイル内で、 **[!UICONTROL Dataset]** 内容を表示する。 [!DNL Cluster.cfg] ファイルは、このディレクトリ内に格納されています。

   1. の横のチェックマークを右クリックします。 [!DNL Cluster.cfg]を選択し、「 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.

   1. 次のファイルフラグメントでハイライトされているテキストを追加します。

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >SSL Server Common Name パラメーターに FSU の共通名を入力すると、FSU はその [!DNL .address] ファイルを参照してください。 詳しくは、 [!DNL .address] ファイルを参照し、 *サーバー製品のインストールおよび管理ガイド*.

   1. ファイルを保存します。
   1. 内 [!DNL Profile Manager]、次のチェックマークを右クリック： [!DNL Cluster.cfg] 内 [!DNL User] 列、「 **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** をクリックして、データセットプロファイルに対してローカルに加えた変更を保存します。
