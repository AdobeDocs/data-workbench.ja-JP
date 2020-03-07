---
description: ワークトップは、すべてのワークスペースとレポートを構成し、それらにアクセスする場所です。
solution: Analytics
title: ワークトップ
topic: Data workbench
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ワークトップ{#worktops}

ワークトップは、すべてのワークスペースとレポートを構成し、それらにアクセスする場所です。

In most cases, the [!DNL Worktop] is displayed immediately after you open Data Workbench. The features of the [!DNL Worktop] include the sidebar and tabbed interface. さらに、サイドバーによりビジュアライゼーションを追加したり、定期的に使用する機能にアクセスしたりできます。

**ワークトップ**

![](assets/client-wktp.png)

The [!DNL Worktop] also enables you to create and save new and updated workspaces and reports, as well as publish workspaces and reports to the Data Workbench server for others to access.

The [!DNL Worktop] elements table below describes each element of the [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> サイドバー </td> 
   <td colname="col2"> <p>サイドバーでは、ワークスペースのコンテキストとコントロールが提供されます。また、ワークスペースの現在の状態を確認し、定期的に使用する機能にアクセスできます。サイドバーでは次の機能が利用できます。 </p> <p> <b>接続：</b>オンラインステータスを示すステータスインジケーター。「<span class="wintitle">オンラインで作業</span>」を有効または無効にするには、接続ステータスをクリックします。See <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Working Offline and Online</a>. </p> <p> <b>プロファイル：</b>現在使用中のプロファイルのインジケーター。 </p> <p> <b>基準日：</b>プロファイルのデータセットの中のデータがどのくらい最新かを示すステータスインジケーター。このデータは DPU サーバーからダウンロードされ、処理されます。ダウンロードと処理は、オンラインで作業している場合のみ発生します。 </p> <p> <b>オフラインサンプルの信頼度：</b>クエリー完了のインジケーター。ステータスのクエリーが 100 ％になったとき、すべてのデータのクエリーが完了しています。 </p> <p> <b>追加：</b>パネル、凡例、テーブルなどのビジュアライゼーションをサイドバーに追加できます。詳しくは、「<a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06">サイドバーへのビジュアライゼーションの追加</a>」を参照してください。 </p> <p> <b>オプション：</b>前のサイドバー設定に戻したり、自動的にサイドバーを非表示にしたりできます。 </p> <p>Sidebar settings are saved in the <span class="filepath"> sidebar.vw</span> file when you close Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>タブとサブタブまたはドロップダウンサブディレクトリ（図にはありません） </p> </td> 
   <td colname="col2"> <p>Each tab that appears on the <span class="wintitle"> Worktop</span> corresponds to the tab’s <i>working profile name</i>\Workspaces\<i>tab name</i> folder within the Data Workbench installation directory and represents a particular type of information, such as Dashboards, Activity, Acquisition, Visitors, and so on. tab name フォルダー内のサブフォルダーは、デフォルトでサブタブとして表示されますが、サブディレクトリとして表示することもできます。詳しくは、「 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> ワークトップタブのカスタマイズ</a>. </p> <p> <p>注意： 各Data Workbenchプロファイルは、標準のタブセットと共に提供されます。 実装は完全にカスタマイズできるので、実際に表示されるワークスペース（およびタブ）は、このガイドに記載されるものと異なる場合があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイルステータス </td> 
   <td colname="col2"> Data Workbenchサーバーへの接続ステータスと、現在読み込まれているプロファイルの名前を示します。 プロファイルのデータセット内のデータの基準日の日時が、オンラインインジケーターの下に表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小化、最大化、閉じる </td> 
   <td colname="col2"> 標準の Windows 機能。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サムネール </td> 
   <td colname="col2"> <p>サムネールは、<span class="wintitle">ワークトップ</span>に表示されるワークスペースのスナップショットです。ワークスペースを保存するたびに、新しいスナップショットが作成されます。サムネールにより、<span class="wintitle">ワークトップ</span>上の特定のワークスペースをすばやく識別できます。 </p> <p>ワークスペースを開くには、サムネールをクリックします。 </p> <p> <p>注意： 各Data Workbenchプロファイルは、標準的な一連のワークスペースと共に提供されます。 実装は十分にカスタマイズできるので、表示されるワークスペースは（したがって、サムネールも）、このガイドに記載されたものと異なる場合があります。 </p> </p> <p>ワークスペースについて詳しくは、「<a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6">サイドバーの設定</a>」を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラーメッセージ </td> 
   <td colname="col2"> <p>エラーメッセージは、ステータスの下に赤で表示されます。ステータスコードの説明については、<a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external">http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a> を参照してください。 </p> <p>例：403_Forbidden </p> </td> 
  </tr> 
 </tbody> 
</table>

