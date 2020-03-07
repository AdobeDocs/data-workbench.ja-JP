---
description: システム管理者が使用する主要ツールはサーバーマネージャーです。
solution: Analytics
title: サーバーマネージャー
topic: Data workbench
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# サーバーマネージャー{#servers-manager}

システム管理者が使用する主要ツールはサーバーマネージャーです。

サーバーマネージャーは、システム全体のステータスを決定し、システム設定、ファイル管理、エラー監視機能を実行するためのメインインターフェイスです。

The Servers Manager displays a colored dot (node) for each Data Workbench server and [!DNL Sensor] installation in your system and provides at-a-glance system status for each installation. また、Data Workbenchのインストール用のノードも表示されます。

緑のノードはアクティブな接続を表し、赤のノードは無効またはアクセス不可の接続を表し、灰色のノードはステータスが未確定の接続を表します。

![](assets/vis_SysStat_RedGreenDots.png)

ノードを右クリックすると、接続しているコンポーネントに関する情報が表示され、関連メニューにアクセスできます。

The following tables describe the information provided when you right-click a node for Data Workbench, Data Workbench server (including a master Data Workbench server in a cluster), or [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>製品         </p> </td> 
   <td colname="col2"> <p>製品名、バージョン、ビルド番号。 </p> <p>例：Data Workbench 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Address </p> </td> 
   <td colname="col2"> <p>Data WorkbenchコンピューターのIPアドレス。 </p> <p>例：100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定 </p> </td> 
   <td colname="col2"> <p>A link to your <span class="keyword"> Data Workbench’s </span> configuration file. Click <span class="uicontrol"> Configure </span> &gt; <span class="uicontrol"> Insight.cfg </span> to display the Data Workbench configuration window. Any changes that you make and save in this window are reflected in the <span class="filepath"> Insight.cfg </span> file in your Data Workbench installation directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>製品         </p> </td> 
   <td colname="col2"> <p>製品名、バージョン、ビルド番号。 </p> <p>例：Data Workbenchサーバー5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Data Workbenchサーバーコンピューターの共通名。 </p> <p>例：<span class="filepath">myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Address </p> </td> 
   <td colname="col2"> <p>コンピューター上のアドレスファイルや、<span class="filepath">Insight.cfg</span> ファイルの Network Location パラメーターに設定されるサーバーの IP アドレスまたは完全修飾ドメイン名。 </p> <p>例：100.0.0.1 </p> <p>アドレスファイルについて詳しくは、『<i>サーバー製品のインストールと管理ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ステータス </p> </td> 
   <td colname="col2"> <p>Data Workbenchサーバーの現在のステータス。 Data Workbenchサーバーが正常に実行されている場合、このフィールドには「OK」が表示されます。 エラーが発生し、Data Workbenchサーバーノードが赤の場合は、エラー（例：「403 Forbidden」）が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>詳細なステータス </p> </td> 
   <td colname="col2"> <p>A link to the <span class="keyword"> Data Workbench server </span> <span class="wintitle"> Detailed Status </span> interface, which is useful for troubleshooting errors or other issues with the Data Workbench server. </p> <p>詳しくは、「詳細なステータスインタ <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> ーフェイス」を参照してくださ</a>い。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リモートデスクトップ </p> </td> 
   <td colname="col2"> <p>Opens a <span class="wintitle"> Remote Desktop </span> session to the Data Workbench server computer. </p> <p>詳しくは、「リモートデスクトッ <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> プオプション」を参照してくださ </a>い。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバーファイル </p> </td> 
   <td colname="col2"> <p>A link to the <span class="wintitle"> Server Files Manager </span>, which displays the directories and files in the Data Workbench server installation directory. </p> <p>詳しくは、サーバーファイルマネージ <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> ャーを参照してくださ </a>い。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバーモニター </p> </td> 
   <td colname="col2"> <p><span class="wintitle">サーバーモニター</span>インターフェイスへのリンク。このインターフェイスは、トラブルシューティングやパフォーマンスパラメーターの追跡に役立ちます。 </p> <p>詳しくは、「サーバーモニターイン <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> ターフェイス」を参照してくださ </a>い。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>関連サーバー </p> </td> 
   <td colname="col2"> <p>Data Workbenchサーバークラスターの場合のみ。 </p> <p>A menu that lists the common names of the computers listed in the master <span class="filepath"> Data Workbench server’s *.address </span> file. This list usually includes all of the processing <span class="keyword"> Data Workbench servers </span> in the cluster. This menu appears only if Data Workbench has a copy of the master <span class="filepath"> Data Workbench server’s *.address </span> file. </p> <p>「<span class="uicontrol">関連サーバー</span>」をクリックすると、次のどちらかをクリックできます。 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol">サーバーモニターリスト</span>：すべての関連サーバーの詳細を一覧表示する<span class="wintitle">サーバーモニター</span>インターフェイスが表示されます。 </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">任意のData Workbenchサーバーの共通名。特定のサーバーに関する次のいずれかを開くためのコンテキストメニューが表示されます。 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol">詳細なステータス</span>。See <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> The Detailed Status Interface </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol">リモートデスクトップ</span>。See <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> The Remote Desktop Option </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol">サーバーファイルマネージャー</span>。サーバーフ <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> ァイルマネージャーを参照してくだ </a>さい。 </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol">サーバーモニター</span>。See <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> The Server Monitor Interface </a>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>製品         </p> </td> 
   <td colname="col2"> <p>製品名、バージョン、ビルド番号。 </p> <p>例：Sensor 3.76; J3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> このインストールの<span class="wintitle">センサー</span>設定ファイルで指定されている<span class="wintitle">センサー</span> ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p><span class="wintitle">センサー</span>がインストールされている Web サーバーまたはアプリケーションサーバーの IP アドレス。 </p> <p>例：100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>オペレーティングシステムによって割り当てられたプロセス ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Whether <span class="wintitle"> Sensor </span> and the Data Workbench server communicate using SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>時間 </p> </td> 
   <td colname="col2"> <p>時間 (HH:MM:SS) that the <span class="wintitle"> Sensor </span> last established a connection with the Data Workbench server. </p> </td> 
  </tr> 
 </tbody> 
</table>
