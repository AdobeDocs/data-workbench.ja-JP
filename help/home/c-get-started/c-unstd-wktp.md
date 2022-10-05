---
description: ワークトップは、すべてのワークスペースとレポートを構成し、それらにアクセスする場所です。
title: ワークトップ
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
exl-id: e714ca25-5e94-408a-9d4e-6e1c13e2a3ef
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 66%

---

# ワークトップ{#worktops}

{{eol}}

ワークトップは、すべてのワークスペースとレポートを構成し、それらにアクセスする場所です。

ほとんどの場合、 [!DNL Worktop] は、Data Workbenchを開いた直後に表示されます。 の機能 [!DNL Worktop] サイドバーとタブ付きのインターフェイスを含めます。 さらに、サイドバーによりビジュアライゼーションを追加したり、定期的に使用する機能にアクセスしたりできます。

**ワークトップ**

![](assets/client-wktp.png)

この [!DNL Worktop] また、新規および更新済みのワークスペースとレポートを作成して保存したり、他のユーザーがアクセスできるようにワークスペースとレポートをData Workbenchサーバーに公開したりできます。

この [!DNL Worktop] 次の表に、 [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689">
 <tbody>
  <tr>
   <td colname="col1"> サイドバー </td>
   <td colname="col2"> <p>サイドバーでは、ワークスペースのコンテキストとコントロールが提供されます。また、ワークスペースの現在の状態を確認し、定期的に使用する機能にアクセスできます。サイドバーでは次の機能が利用できます。 </p> <p> <b>接続：</b>オンラインステータスを示すステータスインジケーター。「<span class="wintitle">オンラインで作業</span>」を有効または無効にするには、接続ステータスをクリックします。詳しくは、 <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> オフラインおよびオンラインでの作業</a>. </p> <p> <b>プロファイル：</b>現在使用中のプロファイルのインジケーター。 </p> <p> <b>基準日：</b>プロファイルのデータセットの中のデータがどのくらい最新かを示すステータスインジケーター。このデータは DPU サーバーからダウンロードされ、処理されます。ダウンロードと処理は、オンラインで作業している場合のみ発生します。 </p> <p> <b>オフラインサンプルの信頼度：</b>クエリー完了のインジケーター。ステータスのクエリーが 100 ％になったとき、すべてのデータのクエリーが完了しています。 </p> <p> <b>追加：</b>パネル、凡例、テーブルなどのビジュアライゼーションをサイドバーに追加できます。詳しくは、「<a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06">サイドバーへのビジュアライゼーションの追加</a>」を参照してください。 </p> <p> <b>オプション：</b>前のサイドバー設定に戻したり、自動的にサイドバーを非表示にしたりできます。 </p> <p>サイドバー設定は、 <span class="filepath"> sidebar.vw</span> ファイルを閉じるときのData Workbench。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>タブとサブタブまたはドロップダウンサブディレクトリ（図にはありません） </p> </td>
   <td colname="col2"> <p>各タブが <span class="wintitle"> ワークトップ</span> タブの <i>作業プロファイル名</i>\Workspaces\<i>タブ名</i> フォルダー内に含まれ、Data Workbench、アクティビティ、獲得、訪問者など、特定の種類の情報を表します。 tab name フォルダー内のサブフォルダーは、デフォルトでサブタブとして表示されますが、サブディレクトリとして表示することもできます。詳しくは、「 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> ワークトップタブのカスタマイズ</a>. </p> <p> <p>注意：各Data Workbenchプロファイルは、標準のタブセットと共に提供されます。 実装は完全にカスタマイズできるので、実際に表示されるワークスペース（およびタブ）は、このガイドに記載されるものと異なる場合があります。 </p> </p> </td>
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
   <td colname="col2"> <p>サムネールは、<span class="wintitle">ワークトップ</span>に表示されるワークスペースのスナップショットです。ワークスペースを保存するたびに、新しいスナップショットが作成されます。サムネールにより、<span class="wintitle">ワークトップ</span>上の特定のワークスペースをすばやく識別できます。 </p> <p>ワークスペースを開くには、サムネールをクリックします。 </p> <p> <p>注意：各Data Workbenchプロファイルは、ワークスペースの標準セットと共に提供されます。 実装は十分にカスタマイズできるので、表示されるワークスペースは（したがって、サムネールも）、このガイドに記載されたものと異なる場合があります。 </p> </p> <p>ワークスペースについて詳しくは、「<a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6">サイドバーの設定</a>」を参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> エラーメッセージ </td>
   <td colname="col2"> <p>エラーメッセージは、ステータスの下に赤で表示されます。ステータスコードの説明については、 <a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>例：403_Forbidden </p> </td>
  </tr>
 </tbody>
</table>
