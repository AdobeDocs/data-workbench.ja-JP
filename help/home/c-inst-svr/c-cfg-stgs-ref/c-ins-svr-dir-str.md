---
description: Insight Serverと共にインストールされ、登録後に存在し、初めて実行されるファイルのリスト。
solution: Analytics
title: Insight サーバーのディレクトリ構造
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---


# Insight サーバーのディレクトリ構造{#insight-server-directory-structure}

Insight Serverと共にインストールされ、登録後に存在し、初めて実行されるファイルのリスト。

## インストールパッケージに含まれているファイル {#section-daec17dab3e34c3c9e1ef65842cb91f1}

インストールパッケージには、次のディレクトリが含まれ [!DNL Insight Server] ます。

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
   <td colname="col2"> Insightサーバーとの通信に使用するアドレス <span class="keyword"> で </span>す。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 監査 </td> 
   <td colname="col2"> 毎日のアクセスログには、 <span class="keyword"> Insightサーバーへのすべての接続試行に関する詳細が含まれ </span>ます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insight Serverの実行可能 </span> プログラムファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificates </td> 
   <td colname="col2"> SSLデジタル証明書。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> コンポーネント設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーを処理するコンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insightサーバー </span> クラスター内の <span class="keyword"> Insight Serverを処理するため </span> のInsightサーバーコンポーネント設定ファイル <span class="keyword"></span> です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> エラーメッセージを含む詳細なイベントステータスメッセージを含む毎日のイベントログ。 Insight Serverによってキャプチャおよびログに記録されるイベント <span class="keyword"></span> は、Windowsイベントビューアにも表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログ </td> 
   <td colname="col2"> <p>Sensorによって生成された <span class="wintitle"> ログファイル </span>です。 </p> <p>"Logs"はデフォルトのログディレクトリですが、 <span class="filepath"> communications.cfg </span> ファイルで代替ディレクトリが指定されている場合があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照 </td> 
   <td colname="col2"> ロボットや検索エンジンのリストなどの参照ファイル。 <span class="keyword"> Insightサーバー </span> は、すべての参照ファイルをメモリに読み込む必要があります。 コンポーネント構成ファイルで参照されるすべての参照ファイルの合計サイズとオーバーヘッド(FlatFileLookup <span class="filepath"></span> ファイルの場合は1行に12バイト)は、他のすべてのソフトウェアアプリケーションが読み込まれた後に使用可能な物理メモリまたは仮想メモリを超えてはなりません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイル </td> 
   <td colname="col2"> <p>各プロファイルに関連するファイル（設定、ワークスペースおよびビジュアライゼーションファイル）。 プロファイルは、データセットのデータによって入力されます。 データセットにはイベントデータ（「ログデータ」）が含まれます。このようなデータは、インストール済みの <span class="wintitle"></span>センサーによって取り込まれ、ウェブビーコンやページタグによって送信されたり、データ・ウェアハウスから入力されたりすることがあります。 <span class="keyword"> 特定のプロファイルにアクセスできるInsight </span> ユーザーは、そのプロファイル用に処理済みデータのセット、およびそのプロファイル内で定義されたワークスペースとビジュアライゼーションを使用できます。 </p> <p>ワークスペースは、システム管理や分析のための作業領域です。 Workspaceには、システムのパフォーマンスに関する異なる詳細を示す複数のインターフェイスを含めることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ソフトウェア </td> 
   <td colname="col2"> <span class="keyword"> Insight </span> ソフトウェアの更新。 レポートソフトウェアの更新もここに保存されます。 </td> 
  </tr> 
 </tbody> 
</table>

## Directories and Files Created after Startup {#section-ef7408e8fae64454b326ec07453d4628}

次に示すディレクトリは、が登録され [!DNL Insight Server] て初めて実行された後に作成されます。

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
   <td colname="col2"> Insightサーバーによって生成される処理情報 <span class="keyword"> で </span>す。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>再処理と操作中に <span class="keyword"> Insightサーバーで使用される一時ファイルの場所 </span> です。 通常、物理ドライブ1台につき1つのファイル( <span class="filepath"> temp.db </span> という名前)が存在します。 </p> <p> <span class="keyword"> Insightサーバー </span> は、このディレクトリに書き込むように設定する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トレース </td> 
   <td colname="col2"> Insightサーバーに関するログと <span class="keyword"> イベントのデータ </span>です。 トラブルシューティングに役立ちます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ユーザー </td> 
   <td colname="col2"> サーバー上のプロファイルにアクセスできる名前付き( <span class="keyword"> Insight </span>)ユーザー。 権限を持つ各指定ユーザーのディレクトリは、ユーザーが <span class="keyword"> Insightを介して最初に </span> Insightサーバーにアクセスしたときに、Users\ディレクトリ内に作成され <span class="keyword"></span>ます。 指定された各ユーザーのディレクトリには、その <span class="keyword"> Insightサーバーでユーザーがアクセスしたすべてのプロファイルに対応するディレクトリと、そのローカルアドレスファイル </span> が含まれます。 </td> 
  </tr> 
 </tbody> 
</table>

