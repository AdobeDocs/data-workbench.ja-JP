---
description: システム管理者が使用する主要ツールはサーバーマネージャーです。
title: サーバーマネージャー
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 41%

---

# サーバーマネージャー{#servers-manager}

システム管理者が使用する主要ツールはサーバーマネージャーです。

サーバーマネージャーは、システム全体のステータスを決定し、システム設定、ファイル管理、エラー監視機能を実行するためのメインインターフェイスです。

サーバーマネージャーには、システム内の各Data Workbenchサーバーと[!DNL Sensor]インストールに対して色付きの点（ノード）が表示され、各インストールのシステムステータスが一目でわかります。 また、インストールに使用するData Workbenchも表示されます。

緑のノードはアクティブな接続を表し、赤のノードは無効またはアクセス不可の接続を表し、灰色のノードはステータスが未確定の接続を表します。

![](assets/vis_SysStat_RedGreenDots.png)

ノードを右クリックすると、接続しているコンポーネントに関する情報が表示され、関連メニューにアクセスできます。

次の表に、Data Workbench、Data Workbench・サーバ(クラスタ内のマスター・Data Workbench・サーバを含む)、[!DNL Sensor]のノードを右クリックしたときに表示される情報を示します。

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>製品             </p> </td> 
   <td colname="col2"> <p>製品名、バージョン、ビルド番号。 </p> <p>例：Data Workbench5.3(00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Address </p> </td> 
   <td colname="col2"> <p>コンピュータのIPData Workbench。 </p> <p>例：100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定 </p> </td> 
   <td colname="col2"> <p><span class="keyword">Data Workbenchの</span>設定ファイルへのリンク。 <span class="uicontrol">設定</span> / <span class="uicontrol"> Insight.cfg </span>をクリックして、Data Workbench設定ウィンドウを表示します。 このウィンドウで行った変更は、Data Workbenchのインストールディレクトリ内の<span class="filepath"> Insight.cfg </span>ファイルに反映されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>製品             </p> </td> 
   <td colname="col2"> <p>製品名、バージョン、ビルド番号。 </p> <p>例：Data Workbenchサーバー5.3(00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Data Workbench・サーバー・コンピュータの共通名。 </p> <p>例：<span class="filepath">myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アドレス </p> </td> 
   <td colname="col2"> <p>コンピューター上のアドレスファイルや、<span class="filepath">Insight.cfg</span> ファイルの Network Location パラメーターに設定されるサーバーの IP アドレスまたは完全修飾ドメイン名。 </p> <p>例：100.0.0.1 </p> <p>アドレスファイルについて詳しくは、『<i>サーバー製品のインストールと管理ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ステータス </p> </td> 
   <td colname="col2"> <p>Data Workbench・サーバの現在のステータス。 このフィールドは、Data Workbench・サーバが正常に動作している場合は「OK」と表示されます。 エラーが発生し、Data Workbenchサーバーノードが赤の場合は、フィールドにエラーが表示されます（例：「403 Forbidden」）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>詳細なステータス </p> </td> 
   <td colname="col2"> <p><span class="keyword">Data Workbenchサーバー</span> <span class="wintitle">詳細ステータス</span>インターフェイスへのリンク。Data Workbenchサーバーのエラーやその他の問題のトラブルシューティングに役立ちます。 </p> <p>詳しくは、「<a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md">詳細なステータスインターフェイス</a>」を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リモートデスクトップ </p> </td> 
   <td colname="col2"> <p><span class="wintitle">リモートデスクトップ</span>セッションをData Workbench・サーバ・コンピュータに開きます。 </p> <p>詳しくは、 <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef">リモートデスクトップオプション</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバーファイル </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Server Files Manager </span>へのリンク。Data Workbenchサーバーのインストールディレクトリ内のディレクトリとファイルが表示されます。 </p> <p>詳しくは、「<a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4">サーバーファイルマネージャー</a>」を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバーモニター </p> </td> 
   <td colname="col2"> <p><span class="wintitle">サーバーモニター</span>インターフェイスへのリンク。このインターフェイスは、トラブルシューティングやパフォーマンスパラメーターの追跡に役立ちます。 </p> <p>詳細については、「<a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> The Server Monitor Interface </a> 」を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>関連サーバー </p> </td> 
   <td colname="col2"> <p>Data Workbench・サーバ・クラスタの場合のみ。 </p> <p>マスター<span class="filepath">Data Workbench・サーバーの*.address </span>ファイルにリストされているコンピューターの共通名をリストするメニュー。 このリストには通常、クラスター内のすべての処理<span class="keyword">Data Workbenchサーバー</span>が含まれます。 このメニューは、Data Workbenchにマスター<span class="filepath">Data Workbenchサーバーの*.address </span>ファイルのコピーがある場合にのみ表示されます。 </p> <p>「<span class="uicontrol">関連サーバー</span>」をクリックすると、次のどちらかをクリックできます。 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol">サーバーモニターリスト</span>：すべての関連サーバーの詳細を一覧表示する<span class="wintitle">サーバーモニター</span>インターフェイスが表示されます。 </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">任意のData Workbench・サーバの共通名。コンテキスト・メニューが表示され、その特定のサーバに対して次のいずれかを開くことができます。 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol">詳細なステータス</span>。<a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md">詳細なステータスインターフェイス</a>を参照してください。 </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol">リモートデスクトップ</span>。<a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef">リモートデスクトップオプション</a>を参照してください。 </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> サーバーファイルマネージャー </span>. <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4">サーバーファイルマネージャー</a>を参照してください。 </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol">サーバーモニター</span>。<a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> The Server Monitor Interface </a>を参照してください。 </li> 
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
   <td colname="col1"> <p>製品             </p> </td> 
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
   <td colname="col2"> <p><span class="wintitle">センサー</span>とData WorkbenchサーバーがSSLを使用して通信するかどうか。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>時間 </p> </td> 
   <td colname="col2"> <p>時間 (HH:MM:SS)<span class="wintitle">センサー</span>が最後にData Workbench・サーバーとの接続を確立しました。 </p> </td> 
  </tr> 
 </tbody> 
</table>
