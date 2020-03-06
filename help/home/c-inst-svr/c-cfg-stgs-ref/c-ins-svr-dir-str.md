---
description: Insightサーバーと共にインストールされ、登録後に存在し、初めて実行されるファイルのリストです。
solution: Insight
title: Insightサーバーのディレクトリ構造
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insightサーバーのディレクトリ構造{#insight-server-directory-structure}

Insightサーバーと共にインストールされ、登録後に存在し、初めて実行されるファイルのリストです。

## インストールパッケージに含まれているファイル {#section-daec17dab3e34c3c9e1ef65842cb91f1}

インストールパッケージには、次のディレクトリ [!DNL Insight Server] が含まれます。

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
   <td colname="col2"> <span class="keyword"> アクセスグル </span> ープのリストを指定するInsightサーバー設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 住所 </td> 
   <td colname="col2"> Insightサーバーとの通信に使用するアド <span class="keyword"> レスです </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 監査 </td> 
   <td colname="col2"> Insightサーバーへのすべての接続試行に関する詳細を含む毎日のアクセス <span class="keyword"> ログで </span>す。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insight Server実行可能プ </span> ログラムファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificates </td> 
   <td colname="col2"> SSLデジタル証明書。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insight Serverコンポーネ </span> ント設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーを処理するコンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insight Serverクラス </span> ター内のInsight Serverを処理するためのInsight Serverコンポ <span class="keyword"> ーネント </span> 設定ファ <span class="keyword"></span> イル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> エラーメッセージを含む、詳細なイベントステータスメッセージを含む日別イベントログ。 Insight Serverでキャプチャおよびログに記録さ <span class="keyword"> れるイベ </span> ントは、Windowsイベントビューアにも表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログ </td> 
   <td colname="col2"> <p>Sensorによって生成さ <span class="wintitle"> れた </span>ログファイル。 </p> <p>"Logs"はデフォルトのログディレクトリですが、代替ディレクトリがcommunications.cfgファイルで指定されてい <span class="filepath"> る可能性があ </span> ります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照 </td> 
   <td colname="col2"> ロボットや検索エンジンのリストなどの参照ファイル。 <span class="keyword"> Insightサーバーは、す </span> べての参照ファイルをメモリに読み込む必要があります。 コンポーネント構成ファイルで参照されるすべての参照ファイルの合計サイズとオーバーヘッド( <span class="filepath"> FlatFileLookupファイルの場合は1行あたり12バイト </span> )は、他のすべてのソフトウェアアプリケーションの読み込み後に使用可能な物理メモリまたは仮想メモリを超えてはなりません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイル </td> 
   <td colname="col2"> <p>各プロファイルに関連するファイル（設定、ワークスペースおよびビジュアライゼーションファイル）。 プロファイルは、データセットのデータによって入力されます。 データセットにはイベントデータ（「ログデータ」）が含まれます。このようなデータは、インストール済みのセンサーによ <span class="wintitle"> って取り込ま </span>れ、ウェブビーコンやページタグによって送信されたり、データウェアハウスからの入力によって取り込まれたりします。 <span class="keyword"> 特定のプ </span> ロファイルにアクセスできるInsightユーザーは、そのプロファイルの処理済みデータのセットと、そのプロファイル内で定義されたワークスペースおよびビジュアライゼーションを使用できます。 </p> <p>ワークスペースは、システム管理または分析のための作業領域です。 Workspaceには、システムのパフォーマンスに関する異なる詳細を示す複数のインターフェイスを含めることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ソフトウェア </td> 
   <td colname="col2"> <span class="keyword"> Insightソフトウ </span> ェアの更新。 レポートソフトウェアの更新もここに保存されます。 </td> 
  </tr> 
 </tbody> 
</table>

## Directories and Files Created after Startup {#section-ef7408e8fae64454b326ec07453d4628}

次に示すディレクトリは、が初めて登録 [!DNL Insight Server] され、実行された後に作成されます。

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
   <td colname="col2"> Insightサーバーによって生成される <span class="keyword"> 情報の処 </span>理。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>再処理および操作中に <span class="keyword"> Insightサーバーが使用 </span> する一時ファイルの場所。 通常、物理ドライブごとに1つのフ <span class="filepath"> ァイル(デ </span> フォルトではtemp.db)が存在します。 </p> <p> <span class="keyword"> Insightサーバーは、こ </span> のディレクトリに書き込むように設定する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トレース </td> 
   <td colname="col2"> Insightサーバーに関するログおよびイベ <span class="keyword"> ントデー </span>タ。 トラブルシューティングに役立ちます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Users </td> 
   <td colname="col2"> サーバー上のプ <span class="keyword"> ロフ </span>ァイルにアクセスできる名前付き(Insight)ユーザー。 権限を持つ各ユーザーのディレクトリは、ユーザーが <span class="keyword"> Insightを介してInsightサーバーに最初にアクセスしたときに、Users\ディレクトリ内に作成 </span> されま <span class="keyword"></span>す。 各名前付きユーザーのディレクトリには、その <span class="keyword"> Insightサーバー上でユーザーがアクセスしたすべてのプロファイルに対応するディレクトリと、そ </span> のローカルアドレスファイルが含まれます。 </td> 
  </tr> 
 </tbody> 
</table>

