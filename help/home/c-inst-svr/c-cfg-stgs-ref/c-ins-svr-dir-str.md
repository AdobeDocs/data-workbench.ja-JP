---
description: Insight サーバーと共にインストールされるファイルと、登録後に存在するファイルのリストで、初めて実行します。
title: Insight サーバーのディレクトリ構造
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Insight サーバーのディレクトリ構造{#insight-server-directory-structure}

{{eol}}

Insight サーバーと共にインストールされるファイルと、登録後に存在するファイルのリストで、初めて実行します。

## インストールパッケージに含まれているファイル {#section-daec17dab3e34c3c9e1ef65842cb91f1}

以下のディレクトリが [!DNL Insight Server] インストールパッケージ：

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディレクトリ </th> 
   <th colname="col2" class="entry"> 説明 ディレクトリコンテンツの </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> アクセス制御 </td> 
   <td colname="col2"> <span class="keyword"> Insight サーバー </span> アクセスグループのリストを指定する構成ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アドレス </td> 
   <td colname="col2"> との通信に使用するアドレス <span class="keyword"> Insight サーバー </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 監査 </td> 
   <td colname="col2"> すべての接続試行済みの詳細を含む毎日のアクセスログ <span class="keyword"> Insight サーバー </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insight サーバー </span> 実行可能プログラムファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificates </td> 
   <td colname="col2"> SSL 電子証明書。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insight サーバー </span> コンポーネント設定ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 処理サーバーのコンポーネント </td> 
   <td colname="col2"> <span class="keyword"> Insight サーバー </span> 処理するコンポーネント設定ファイル <span class="keyword"> Insight サーバー </span> 内 <span class="keyword"> Insight サーバー </span> クラスター。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> エラーメッセージを含む詳細なイベントステータスメッセージを含む毎日のイベントログ。 キャプチャされ、ログに記録されたイベント <span class="keyword"> Insight サーバー </span> は、Windows イベントビューアにも表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログ </td> 
   <td colname="col2"> <p>が作成したログファイル <span class="wintitle"> センサー </span>(s). </p> <p>"Logs"はデフォルトのログディレクトリですが、代替ディレクトリが <span class="filepath"> communications.cfg </span> ファイル。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照 </td> 
   <td colname="col2"> 参照ファイル（ロボットや検索エンジンのリストなど）。 <span class="keyword"> Insight サーバー </span> は、すべての参照ファイルをメモリに読み込む必要があります。 コンポーネント設定ファイルで参照されるすべての参照ファイルの合計サイズに加えて、オーバーヘッド ( 例： <span class="filepath"> FlatFileLookup </span> ファイル ) を使用する場合は、他のすべてのソフトウェアアプリケーションが読み込まれた後に使用可能な物理メモリまたは仮想メモリを超えてはなりません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイル </td> 
   <td colname="col2"> <p>各プロファイルに関連するファイル（設定、ワークスペース、ビジュアライゼーションファイル）。 プロファイルは、データセットのデータによって設定されます。 データセットには、イベントデータ（「ログデータ」）が含まれます。このようなデータは、インストールされた <span class="wintitle"> センサー </span>Web ビーコンやページタグで送信されたり、データウェアハウスからの入力で送信されたりします。 <span class="keyword"> Insight </span> 特定のプロファイルにアクセスできるユーザーは、そのプロファイルの処理済みデータのセットと、そのプロファイル内で定義された Workspaces とビジュアライゼーションを使用できます。 </p> <p>ワークスペースは、システム管理や解析の作業領域です。 Workspace には、システムのパフォーマンスに関する様々な詳細を示す複数のインターフェイスを含めることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ソフトウェア </td> 
   <td colname="col2"> <span class="keyword"> Insight </span> ソフトウェアの更新。 また、レポートソフトウェアの更新もここに保存されます。 </td> 
  </tr> 
 </tbody> 
</table>

## 起動後に作成されたディレクトリとファイル {#section-ef7408e8fae64454b326ec07453d4628}

以下に示すディレクトリは、の後に作成されます。 [!DNL Insight Server] が登録され、初めて実行されます。

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
   <td colname="col2"> 次によって生成された情報を処理中 <span class="keyword"> Insight サーバー </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>が使用する一時ファイルの場所 <span class="keyword"> Insight サーバー </span> 再処理中および操作中。 通常、1 つのファイル ( <span class="filepath"> temp.db </span> （デフォルト）物理ドライブごと。 </p> <p> <span class="keyword"> Insight サーバー </span> は、このディレクトリに書き込むように設定する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トレース </td> 
   <td colname="col2"> に関するログとイベントのデータ <span class="keyword"> Insight サーバー </span>. トラブルシューティングに役立ちます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ユーザー </td> 
   <td colname="col2"> 名前 ( <span class="keyword"> Insight </span>) ユーザーがサーバー上のプロファイルにアクセスできる状態になっています。 ユーザーが最初にアクセスすると、許可された各ネームドユーザーのディレクトリが Users\ディレクトリ内に作成されます <span class="keyword"> Insight サーバー </span> 経由 <span class="keyword"> Insight </span>. 各名前付きユーザーのディレクトリには、そのユーザーがアクセスしたすべてのプロファイルに対応するディレクトリが含まれます <span class="keyword"> Insight サーバー </span> ローカルアドレスファイルを含める。 </td> 
  </tr> 
 </tbody> 
</table>
