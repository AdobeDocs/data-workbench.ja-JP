---
description: Insight ソフトウェアと電子証明書をインストールしたら、Insight を起動し、Insight サーバーへの接続を設定する必要があります。
title: Insight サーバーへの接続の設定
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
exl-id: 6a87e972-069a-435c-9bac-23b20f165ebb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 36%

---

# Insight サーバーへの接続の設定{#configuring-the-connection-to-insight-server}

{{eol}}

Insight ソフトウェアと電子証明書をインストールしたら、Insight を起動し、Insight サーバーへの接続を設定する必要があります。

>[!NOTE]
>
>場合によっては、Insight サーバーへの接続が、Adobeコンサルティングサービスまたはシステム管理者によって事前に設定されている可能性があります。 その場合は、このタスクを実行する必要はありません。

初めて Insight を起動すると、電子証明書を登録するために、Adobeライセンスサーバーに自動的に接続します。 登録プロセスを正常に完了するには、以下の手順を実行するときに、コンピューターがインターネットに接続できる必要があります。

>[!NOTE]
>
>事前ロック済み証明書を既に要求、ダウンロード、インストールしている場合 ( [電子証明書のダウンロードとインストール](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9)を指定した場合、Insight はライセンスサーバーへの接続を試みず、エラーは表示されません。

**Insight サーバーへの接続を設定するには**

クラスター環境で作業する場合は、同期の問題を回避するために、マスター Insight サーバーにアクセスするように Insight を設定する必要があります。 Insight では、処理に関する情報を表示できます [!DNL Insight Servers] を使用してクラスター内で [!DNL Related Servers] メニュー項目 [サーバーマネージャー](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-svrs-mgr.html).

1. Insight を起動します。
1. の [!DNL Worktop]をクリックし、 **[!UICONTROL Admin]**&#x200B;を、 **[!UICONTROL First Steps]**.

1. 次をクリック： **[!UICONTROL Configure Connection to Servers]** サムネール。

   この [!DNL Servers Manager]、 [!DNL Insight.cfg] ファイル、および [!DNL Insight.cfg]ファイルが表示されます。

1. 内 [!DNL Insight.cfg] ウィンドウ、右クリック **[!UICONTROL Servers]** をクリックし、 **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddChild.png)

1. サーバーのパラメーターを入力または変更して、Insight がマスター Insight サーバーにアクセスできるようにします。 Insight.cfg ファイル内のパラメーターについて詳しくは、 [設定パラメーター](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-insght-config-param.html).

   ![](assets/cfg_Workstation_AddServer.png)

1. 接続を設定する Insight サーバーごとに、手順 4 と手順 5 を繰り返します。
1. 設定の変更を保存するには、右クリックします。 **[!UICONTROL Insight.cfg (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save as Insight.cfg]**.

   Insight が [!DNL Insight Server(s)] 指定した設定を使用する。 接続が確立されると、緑のノードが [!DNL Servers Manager] を次のページに示します。

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **緑：** Insight サーバーへの接続がアクティブであることを示します。
   * **薄赤色：**&#x200B;サーバー処理のドレイン、メモリ使用量が高い、ディスク容量が少ないなど、サーバーの潜在的な問題を示しています。
   * **赤：** Insight サーバーへの接続がアクティブでないことを示します。

   指定した設定で接続できない場合は、赤いノードが [!DNL Servers Manager]. この場合は、 [接続のトラブルシューティング](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b).

<!--
c_dir_crt_setup.xml
-->

使用するプロファイルを選択すると、（関連するデータとプロファイルに定義されている特定のワークスペースまたはビジュアライゼーションを含む）プロファイル情報がコンピューターにダウンロードされます。各プロファイルをダウンロードすると、Insight はプロファイル名を使用してインストールディレクトリ内にフォルダーを作成します。

例えば、Sales という名前のプロファイルを選択すると、Sales という名前のフォルダーが Insight ディレクトリに表示されます。 このフォルダーには、Sales プロファイルで定義されている指標、ディメンション、ワークスペースおよびビジュアライゼーションが含まれています。プロファイルの初期読み込みの後で、オフラインで作業するときにプロファイルを使用できます。詳しくは、 [オフラインおよびオンラインでの作業](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-off-on.html).

また、Insight から初めて Insight サーバーに接続すると、Insight サーバーは Insight インストールディレクトリに次のディレクトリを作成します。

* **[!DNL Trace]ディレクトリ：** 内 [!DNL Trace] ディレクトリは Insight ログファイル ( [!DNL insight.log]) をクリックします。 ( [!DNL Insight.log] ファイルが 100 MB に達すると、ファイルの名前が「 」に変更されます。 [!DNL insight-1.log]. ファイル名が [!DNL insight-1.log] は既に存在します。 [!DNL insight-1.log] の名前がに変更されました。 [!DNL insight-2.log]など、最大 [!DNL insight-9.log]. [!DNL insight.log] ファイルには、常に最新のログ情報が含まれ、[!DNL insight-max.log] には最も古いログ情報が含まれます。

* **[!DNL User]ディレクトリ：** 内 [!DNL User] ディレクトリは、これまでに使用された各プロファイルに対応するフォルダーで、各プロファイルフォルダー内にはという名前のフォルダーがあります。 [!DNL Work] および [!DNL Workspaces]. ディレクトリ `User\*profile name*\Workspaces` は、Insight のワークスペースファイルを保存するデフォルトの場所です。 `User\*profile name*\Work` は、Insight ユーザーが実行した Insight のビジュアライゼーションおよびその他のカスタム作業を保存するデフォルトの場所です。

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
   <td colname="col1"> <p>保存済み <span class="wintitle"> Workspaces</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>profile name</i>\Workspaces\<i>tab name</i>\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>保存された <span class="filepath">.png</span> ファイル </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>プロファイル名</i>\Work\ </p> </td> 
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

また、 [!DNL Search] フィールドに入力します。 例えば、次の re を使用できます。 [!DNL *zip.*] を検索します。

検索をクリアするには、**[!UICONTROL Escape]** キーを押します。
