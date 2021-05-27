---
description: Insight Serverと共にインストールされるファイルと、登録後に存在し、初めて実行されるファイルのリストです。
title: Insight サーバーのディレクトリ構造
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Insight サーバーのディレクトリ構造{#insight-server-directory-structure}

Insight Serverと共にインストールされるファイルと、登録後に存在し、初めて実行されるファイルのリストです。

## インストールパッケージに含まれているファイル {#section-daec17dab3e34c3c9e1ef65842cb91f1}

[!DNL Insight Server]インストールパッケージには、次のディレクトリが含まれています。

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディレクトリ </th> 
   <th colname="col2" class="entry"> 説明 ディレクトリ内容の </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> アクセス制御 </td> 
   <td colname="col2"> <span class="keyword"> アクセスグル </span> ープのリストを指定するInsightサーバー設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アドレス </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバー</span>との通信に使用されるアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 監査 </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバー</span>へのすべての接続試行に関する詳細が含まれる毎日のアクセスログ。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバーの実行 </span> 可能なプログラムファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificates </td> 
   <td colname="col2"> SSL電子証明書。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバーコンポ </span> ーネント設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 処理サーバーのコンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバーク </span> ラスター内でInsightサーバーを処理す <span class="keyword"> るためのInsightサ </span> ーバーコンポ <span class="keyword"> ーネン </span> ト設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> エラーメッセージを含む詳細なイベントステータスメッセージを含む毎日のイベントログ。 <span class="keyword"> Insightサーバー</span>によってキャプチャおよびログに記録されるイベントも、Windowsイベントビューアに表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログ </td> 
   <td colname="col2"> <p><span class="wintitle"> Sensor </span>(s)によって生成されたログファイル。 </p> <p>"Logs"はデフォルトのログディレクトリですが、代替ディレクトリが<span class="filepath"> communications.cfg </span>ファイルで指定されている場合があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索 </td> 
   <td colname="col2"> ロボットや検索エンジンのリストなどの参照ファイル。 <span class="keyword"> Insightサーバーは、す </span> べての参照ファイルをメモリに読み込む必要があります。コンポーネント構成ファイルで参照されるすべての参照ファイルの合計サイズと、オーバーヘッド（<span class="filepath"> FlatFileLookup </span>ファイルの1行あたり12バイト）は、他のすべてのソフトウェアアプリケーションが読み込まれた後に使用可能な物理メモリまたは仮想メモリを超えてはなりません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイル </td> 
   <td colname="col2"> <p>各プロファイルに関連するファイル（設定、ワークスペース、ビジュアライゼーションファイル）。 プロファイルは、データセットのデータによって設定されます。 データセットにはイベントデータ（「ログデータ」）が含まれます。このようなデータは、インストールされた<span class="wintitle">センサー</span>によって取り込まれ、Webビーコンやページタグで送信されたり、データウェアハウスから入力されたりする場合があります。 <span class="keyword"> 特定のプ </span> ロファイルにアクセスできるInsightユーザーは、そのプロファイルに対して処理されたデータのセット、およびそのプロファイル内で定義されたワークスペースとビジュアライゼーションを使用できます。 </p> <p>ワークスペースは、システムの管理や分析を行う作業領域です。 Workspaceには、システムパフォーマンスに関する様々な詳細を示す複数のインターフェイスを含めることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ソフトウェア </td> 
   <td colname="col2"> <span class="keyword"> Insightソフト </span> ウェアのアップデート。また、レポートソフトウェアの更新もここに保存されます。 </td> 
  </tr> 
 </tbody> 
</table>

## 起動後に作成されたディレクトリとファイル{#section-ef7408e8fae64454b326ec07453d4628}

以下に示すディレクトリは、[!DNL Insight Server]の登録後に作成され、初めて実行されます。

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディレクトリ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 都道府県 </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバー</span>によって生成された処理情報。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p><span class="keyword"> Insightサーバー</span>が再処理および操作中に使用する一時ファイルの場所。 通常、物理ドライブ1台につき<span class="filepath"> temp.db </span>という名前のファイルが1つあります。 </p> <p> <span class="keyword"> Insightサーバー </span> は、このディレクトリに書き込むように設定する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トレース </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバー</span>に関するログとイベントのデータ。 トラブルシューティングに役立ちます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ユーザー </td> 
   <td colname="col2"> サーバー上のプロファイルにアクセスできる名前付き( <span class="keyword"> Insight </span> )ユーザー。 ユーザーが<span class="keyword"> Insight </span>を介して<span class="keyword"> Insightサーバー</span>に最初にアクセスすると、許可された各名前付きユーザーのディレクトリがUsers\ディレクトリ内に作成されます。 各名前付きユーザーのディレクトリには、その<span class="keyword"> Insightサーバー</span>上でユーザーがアクセスしたすべてのプロファイルと、そのローカルアドレスファイルに対応するディレクトリが含まれます。 </td> 
  </tr> 
 </tbody> 
</table>
