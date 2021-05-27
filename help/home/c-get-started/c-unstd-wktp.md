---
description: ワークトップは、すべてのワークスペースとレポートを構成し、それらにアクセスする場所です。
title: ワークトップ
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
exl-id: e714ca25-5e94-408a-9d4e-6e1c13e2a3ef
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 68%

---

# ワークトップ{#worktops}

ワークトップは、すべてのワークスペースとレポートを構成し、それらにアクセスする場所です。

ほとんどの場合、Data Workbenchを開くとすぐに[!DNL Worktop]が表示されます。 [!DNL Worktop]の機能には、サイドバーとタブ付きのインターフェイスが含まれます。 さらに、サイドバーによりビジュアライゼーションを追加したり、定期的に使用する機能にアクセスしたりできます。

**ワークトップ**

![](assets/client-wktp.png)

[!DNL Worktop]では、新しいワークスペースと更新されたレポートを作成して保存したり、他のユーザーがアクセスできるようにワークスペースとレポートをData Workbenchサーバーに公開したりすることもできます。

以下の[!DNL Worktop]要素の表では、[!DNL Worktop]の各要素について説明します。

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> サイドバー </td> 
   <td colname="col2"> <p>サイドバーでは、ワークスペースのコンテキストとコントロールが提供されます。また、ワークスペースの現在の状態を確認し、定期的に使用する機能にアクセスできます。サイドバーでは次の機能が利用できます。 </p> <p> <b>接続：</b>オンラインステータスを示すステータスインジケーター。「<span class="wintitle">オンラインで作業</span>」を有効または無効にするには、接続ステータスをクリックします。<a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54">オフラインでの作業とオンラインでの作業</a>を参照してください。 </p> <p> <b>プロファイル：</b>現在使用中のプロファイルのインジケーター。 </p> <p> <b>基準日：</b>プロファイルのデータセットの中のデータがどのくらい最新かを示すステータスインジケーター。このデータは DPU サーバーからダウンロードされ、処理されます。ダウンロードと処理は、オンラインで作業している場合のみ発生します。 </p> <p> <b>オフラインサンプルの信頼度：</b>クエリー完了のインジケーター。ステータスのクエリーが 100 ％になったとき、すべてのデータのクエリーが完了しています。 </p> <p> <b>追加：</b>パネル、凡例、テーブルなどのビジュアライゼーションをサイドバーに追加できます。詳しくは、「<a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06">サイドバーへのビジュアライゼーションの追加</a>」を参照してください。 </p> <p> <b>オプション：</b>前のサイドバー設定に戻したり、自動的にサイドバーを非表示にしたりできます。 </p> <p>Data Workbenchを閉じると、サイドバー設定は<span class="filepath"> sidebar.vw</span>ファイルに保存されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>タブとサブタブまたはドロップダウンサブディレクトリ（図にはありません） </p> </td> 
   <td colname="col2"> <p><span class="wintitle">ワークトップ</span>に表示される各タブは、Data Workbenchインストールディレクトリ内のタブの<i>working profile name</i>\Workspaces\<i>tab name</i>フォルダーに対応し、ダッシュボード、アクティビティ、獲得、訪問者などの特定の種類の情報を表します。 tab name フォルダー内のサブフォルダーは、デフォルトでサブタブとして表示されますが、サブディレクトリとして表示することもできます。詳しくは、「 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> ワークトップタブのカスタマイズ</a>. </p> <p> <p>注意： 各Data Workbenchプロファイルは、標準のタブセットと共に提供されます。 実装は完全にカスタマイズできるので、実際に表示されるワークスペース（およびタブ）は、このガイドに記載されるものと異なる場合があります。 </p> </p> </td> 
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
   <td colname="col2"> <p>サムネールは、<span class="wintitle">ワークトップ</span>に表示されるワークスペースのスナップショットです。ワークスペースを保存するたびに、新しいスナップショットが作成されます。サムネールにより、<span class="wintitle">ワークトップ</span>上の特定のワークスペースをすばやく識別できます。 </p> <p>ワークスペースを開くには、サムネールをクリックします。 </p> <p> <p>注意： 各Data Workbenchプロファイルは、標準のワークスペースセットと共に提供されます。 実装は十分にカスタマイズできるので、表示されるワークスペースは（したがって、サムネールも）、このガイドに記載されたものと異なる場合があります。 </p> </p> <p>ワークスペースについて詳しくは、「<a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6">サイドバーの設定</a>」を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラーメッセージ </td> 
   <td colname="col2"> <p>エラーメッセージは、ステータスの下に赤で表示されます。ステータスコードの説明については、<a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external">http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a> を参照してください。 </p> <p>例：403_Forbidden </p> </td> 
  </tr> 
 </tbody> 
</table>
