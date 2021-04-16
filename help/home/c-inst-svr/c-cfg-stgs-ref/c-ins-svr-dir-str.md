---
description: Insight Serverと共にインストールされ、登録後に存在し、初めて実行されるファイルのリスト。
title: Insight サーバーのディレクトリ構造
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Insight サーバーのディレクトリ構造{#insight-server-directory-structure}

Insight Serverと共にインストールされ、登録後に存在し、初めて実行されるファイルのリスト。

## インストールパッケージに含まれているファイル {#section-daec17dab3e34c3c9e1ef65842cb91f1}

[!DNL Insight Server]インストールパッケージには、次のディレクトリが含まれています。

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディレクトリ </th> 
   <th colname="col2" class="entry"> 説明 ディレクトリの内容 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> アクセス制御 </td> 
   <td colname="col2"> <span class="keyword"> アクセスグループのリストを指定するInsightサーバー </span> 設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 住所 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span>との通信に使用するアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 監査 </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバー</span>へのすべての接続試行に関する詳細を含む毎日のアクセスログです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insight Serverの </span> 実行可能なプログラムファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificates </td> 
   <td colname="col2"> SSLデジタル証明書。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバー </span> コンポーネント設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーを処理するコンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバー </span> クラスター <span class="keyword"> 内の </span> Insight Serverを処理するためのInsightサーバー <span class="keyword">  </span> コンポーネント設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> エラーメッセージを含む詳細なイベントステータスメッセージを含む毎日のイベントログ。 <span class="keyword"> Insight Server </span>によってキャプチャおよびログに記録されたイベントも、Windowsイベントビューアに表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログ </td> 
   <td colname="col2"> <p><span class="wintitle"> Sensor </span>(s)によって生成されたログファイルです。 </p> <p>"Logs"はデフォルトのログディレクトリですが、<span class="filepath"> communications.cfg </span>ファイルに別のディレクトリが指定されている場合があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照 </td> 
   <td colname="col2"> ロボットや検索エンジンのリストなどの参照ファイル。 <span class="keyword"> Insightサーバーでは、すべての参照ファイルをメモリに読み込む </span> 必要があります。コンポーネント構成ファイルで参照されるすべての参照ファイルの合計サイズとオーバーヘッド（例えば、<span class="filepath"> FlatFileLookup </span>ファイルの1行あたり12バイト）は、他のすべてのソフトウェアアプリケーションの読み込み後に使用可能な物理メモリまたは仮想メモリを超えてはなりません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイル </td> 
   <td colname="col2"> <p>各プロファイルに関連するファイル（設定、ワークスペースおよびビジュアライゼーションファイル）。 プロファイルは、データセットのデータによって入力されます。 データセットにはイベントデータ（「ログデータ」）が含まれます。このようなデータは、インストールされた<span class="wintitle">センサー</span>によって取り込まれ、ウェブビーコンやページタグで送信されるか、またはデータウェアハウスからの入力によって取り込まれます。 <span class="keyword"> 特定のプロファイルにアクセスできるInsight </span> ユーザーは、そのプロファイル用に処理済みデータのセット、およびそのプロファイル内で定義されたワークスペースとビジュアライゼーションを使用できます。 </p> <p>ワークスペースは、システム管理や分析のための作業領域です。 Workspaceには、システムのパフォーマンスに関する異なる詳細を示す複数のインターフェイスを含めることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ソフトウェア </td> 
   <td colname="col2"> <span class="keyword"> Insight </span> ソフトウェアの更新。レポートソフトウェアの更新もここに保存されます。 </td> 
  </tr> 
 </tbody> 
</table>

## 起動後に作成されたディレクトリとファイル{#section-ef7408e8fae64454b326ec07453d4628}

以下に示すディレクトリは、[!DNL Insight Server]が登録され、初めて実行された後に作成されます。

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
   <td colname="col2"> <span class="keyword"> Insightサーバー</span>によって生成された処理情報です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p><span class="keyword"> Insight Server </span>が再処理と操作中に使用する一時ファイルの場所です。 通常、物理ドライブ1つにつき<span class="filepath"> temp.db </span>という名前のファイルが1つあります。 </p> <p> <span class="keyword"> Insightサーバー </span> は、このディレクトリに書き込むように設定する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トレース </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span>に関するログとイベントのデータです。 トラブルシューティングに役立ちます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ユーザー </td> 
   <td colname="col2"> サーバー上のプロファイルにアクセスできる名前付き(<span class="keyword"> Insight </span>)ユーザー。 ユーザーが<span class="keyword"> Insight </span>を介して<span class="keyword"> Insight Server </span>に最初にアクセスしたとき、権限のある名前の付いた各ユーザーのディレクトリがUsers\ディレクトリ内に作成されます。 指定された各ユーザーのディレクトリには、その<span class="keyword"> Insight Server </span>上でユーザーがアクセスしたすべてのプロファイルに対応するディレクトリと、そのローカルアドレスファイルが含まれます。 </td> 
  </tr> 
 </tbody> 
</table>
