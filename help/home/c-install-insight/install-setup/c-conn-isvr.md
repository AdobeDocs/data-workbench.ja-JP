---
description: Insightソフトウェアとデジタル証明書をインストールしたら、Insightを起動し、Insightサーバーへの接続を設定する必要があります。
title: Insightサーバーへの接続の設定
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Configuring the Connection to Insight Server{#configuring-the-connection-to-insight-server}

Insightソフトウェアとデジタル証明書をインストールしたら、Insightを起動し、Insightサーバーへの接続を設定する必要があります。

>[!NOTE]
>
>場合によっては、Insightサーバーへの接続がアドビのコンサルティングサービスまたはシステム管理者によって事前に設定されていることがあります。 その場合は、このタスクを実行する必要はありません。

初めてInsightを起動すると、デジタル証明書を登録するためにAdobe License Serverに自動的に接続されます。 登録プロセスを正常に完了するには、以下の手順を実行するときに、コンピューターがインターネットに接続できる必要があります。

>[!NOTE]
>
>「デジタル証明書のダウンロードとインストール」の説明に従って、事前にロックされた証明書を要求、ダウンロード、インストールした場合 [](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9)、InsightはLicense Serverへの接続を試みず、エラーは表示されません。

**Insightサーバーへの接続を設定するには**

クラスター環境で作業する場合は、同期の問題を回避するために、マスターInsightサーバーにアクセスするようにInsightを設定する必要があります。 In Insight you can view information about the processing [!DNL Insight Servers] in your cluster using the [!DNL Related Servers] menu item in the [Servers Manager](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-svrs-mgr.html).

1. Insightを起動します。
1. で、をク [!DNL Worktop]リックし、 **[!UICONTROL Admin]**&#x200B;次にをクリックしま **[!UICONTROL First Steps]**&#x200B;す。

1. サムネールをクリ **[!UICONTROL Configure Connection to Servers]** ックします。

   The [!DNL Servers Manager], the [!DNL Insight.cfg] file, and instructions for configuring your [!DNL Insight.cfg]file are displayed.

1. ウィンドウ [!DNL Insight.cfg] で右クリックし、「>」 **[!UICONTROL Servers]** をクリッ **[!UICONTROL Add new child]** クしま **[!UICONTROL Server]**&#x200B;す。

   ![](assets/cfg_Workstation_AddChild.png)

1. InsightでマスターInsightサーバーへのアクセスを提供するために、サーバーのパラメーターを入力または変更します。 For detailed descriptions of the parameters in the Insight.cfg file, see [Configuration parameters](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-insght-config-param.html).

   ![](assets/cfg_Workstation_AddServer.png)

1. 接続を設定する各Insightサーバーに対して、手順4と手順5を繰り返します。
1. To save your configuration changes, right-click **[!UICONTROL Insight.cfg (modified)]** at the top of the window and click **[!UICONTROL Save as Insight.cfg]**.

   Insight attempts to connect to the [!DNL Insight Server(s)] using the settings that you have specified. If a connection is established, a green node appears in the [!DNL Servers Manager] as shown on the following page.

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **緑：** Insightサーバーへの接続がアクティブであることを示します。
   * **薄赤色：**&#x200B;サーバー処理のドレイン、メモリ使用量が高い、ディスク容量が少ないなど、サーバーの潜在的な問題を示しています。
   * **赤：** Insightサーバーへの接続がアクティブでないことを示します。
   If Insight cannot connect using the specified settings, a red node appears in the [!DNL Servers Manager]. この場合は、接続のトラブルシューティングを [参照してくださ](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b)い。

<!--
c_dir_crt_setup.xml
-->

使用するプロファイルを選択すると、（関連するデータとプロファイルに定義されている特定のワークスペースまたはビジュアライゼーションを含む）プロファイル情報がコンピューターにダウンロードされます。各プロファイルをダウンロードすると、Insightによって、プロファイル名を使用してインストールディレクトリ内にフォルダーが作成されます。

例えば、Salesという名前のプロファイルを選択すると、Salesという名前のフォルダーがInsightディレクトリに表示されます。 このフォルダーには、Sales プロファイルで定義されている指標、ディメンション、ワークスペースおよびビジュアライゼーションが含まれています。プロファイルの初期読み込みの後で、オフラインで作業するときにプロファイルを使用できます。See [Working offline and online](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-off-on.html).

また、Insightから初めてInsightサーバーに接続すると、InsightサーバーはInsightのインストールディレクトリに次のディレクトリを作成します。

* **[!DNL Trace]ディレクトリ：**ディレクトリ[!DNL Trace]内には、Insightのログファイル([!DNL insight.log])が含まれます。 When the size of the[!DNL Insight.log]file reaches 100 MB, the file is renamed to[!DNL insight-1.log]. If a file of the name[!DNL insight-1.log]already exists, then[!DNL insight-1.log]is renamed to[!DNL insight-2.log], and so forth, with a maximum of[!DNL insight-9.log].[!DNL insight.log]ファイルには、常に最新のログ情報が含まれ、[!DNL insight-max.log]には最も古いログ情報が含まれます。

* **[!DNL User]ディレクトリ：**ディレクトリ内[!DNL User]には、これまでに使用された各プロファイルに対応するフォルダーが含まれ、各プロファイルフォルダー内には、とという名前のフォルダーが[!DNL Work]含まれま[!DNL Workspaces]す。 The directory`User\*profile name*\Workspaces`is the default location in which Insight workspace files are saved.`User\*profile name*\Work`は、InsightのビジュアライゼーションおよびInsightユーザーが実行した他のカスタム作業が保存されるデフォルトの場所です。

次の表は、よくアクセスされるコンポーネントのデフォルトの場所のリストを示しています。

<table id="table_0254A8C25AF5400F89F87A242746D07E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コンポーネント </th> 
   <th colname="col2" class="entry"> ディレクトリの場所 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>保存されたビジュアライゼーション </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>profile name</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Saved <span class="wintitle"> Workspaces</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>profile name</i>\Workspaces\<i>tab name</i>\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>保存された <span class="filepath">.png</span> ファイル </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>profile name</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>データキャッシュ </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Insight.log</span> ファイル </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

キー名、キータイプまたは値で検索して、エントリをすばやく見つけることができるので、大きなファイル全体をスクロールしてネストされた情報を探す必要がありません。ディメンション名やサーバー名などを検索できます。次の例は、フレーズマップでの検索の一致を示しています。

![](assets/cfg_search.PNG)

このフィールドに検索語句を入力して、データを見つけます。一致が見つかったかどうかによって、フィールドの色が変化します。一致はハイライト表示され、不一致は暗く表示されます。一致がない場合は、検索フィールドの背景が赤くなります。Enter キーを押すと、設定ツリーの一致があるすべての箇所が展開され、一致がない箇所は折りたたまれます。

You can also use regular expressions in the [!DNL Search] field. For example, you can use re: [!DNL *zip.*]を検索します。

検索をクリアするには、**[!UICONTROL Escape]** キーを押します。
