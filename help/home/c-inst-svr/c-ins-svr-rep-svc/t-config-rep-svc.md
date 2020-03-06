---
description: 元のイベントデータが格納されているリピーターからデータを取得するように、ターゲットのInsightサーバーを設定する必要があります。
solution: Insight
title: レプリケーションサービスの構成
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# レプリケーションサービスの構成{#configuring-the-replication-service}

元のイベントデータが格納されているリピーターからデータを取得するように、ターゲットのInsightサーバーを設定する必要があります。

ターゲットからのデータの取得を設定す [!DNL Repeater] るには、次の手順に従って、ターゲット上のフ [!DNL Insight Server]ォルダーに [!DNL Replicate.cfg] 指定されたファ [!DNL Components] イルを編集 [!DNL Insight Server(s)] する必要があります。

**ターゲットコンピュー[!DNL Replication Service]ターでを設定するには**

1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。
1. 設定するターゲットのアイコンを右ク [!DNL Insight Server] リックし、をクリックしま **[!UICONTROL Server Files]**&#x200B;す。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Replicate.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the *server name* column for [!DNL Replicate.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Replicate.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. ウィンドウ [!DNL Replicate.cfg] が開きます。
1. In the [!DNL Replicate.cfg] window, click **[!UICONTROL Replicate.cfg]**, then **[!UICONTROL component]** to view its contents.
1. 次の例と表を参考にして、パラメーターを編集します。

   ![ステップ情報](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> パラメーター </th> 
      <th colname="col2" class="entry"> ... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> ディレクトリ </td> 
      <td colname="col2"> <p>ターゲット <span class="wintitle"> Insight</span> サーバーにコピー（複製）する、リピーター上のディレク <span class="keyword"> トリ</span>。 Replication Serviceを使用す <span class="wintitle"> ると</span> 、単一のリピータから複数のディレクトリを複製で <span class="wintitle"> きます</span>。 </p> <p>新しいディレクトリを追加するには、 <span class="uicontrol"> Directoriesを右クリックし、新規追加</span> / <span class="uicontrol"> Directoryをクリックし</span> ます <span class="uicontrol"></span>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> パスの統合 </td> 
      <td colname="col2"> <p>true または false。このパラメーターの設定で定義されるアクションは、このファイル内のRecursiveパラメーターの設定によって異なります。 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Recursiveがfalseの場合、Flatten Pathsは無効です。 Remote URIパラメーターで指定されたディレクトリの最上位のファイルのみが複製されます。 </li>
      <li id="li_8FDB351102344E3995035557445354BB">RecursiveがtrueでFlatten Pathsがfalseの場合、リモート(<span class="wintitle"> Repeater</span>)ディレクトリのディレクトリ構造は、ターゲットの <span class="keyword"> Insight Serverのローカルパスに正確に複製されます</span>。 </li>
      <li id="li_3114B191C73744658799E112C61AB004">再帰パスと統合パスの両方がtrueの場合、ローカルパスにサブディレクトリは作成されません。 代わりに、リモートディレクトリツリーのすべてのファイルは、ローカルディレクトリの最上位に配置されます。 </li>
      </ul></p> <p> <p>注意：Flatten PathsとRecursiveの両方がtrueで、リモート・マシン上の各サブディレクトリ内のファイルが同じ名前を共有している場合、 <span class="wintitle"> Replication Service</span> が停止したり、その他の未定義の動作が発生したりする場合があります。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> ローカルパス </td> 
      <td colname="col2">リピータから取得したファイルの保存場所 <span class="wintitle"> です</span>。 パスは、 <span class="keyword"> Insight Serverのインストールディレクトリに対する相対パス</span> です。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursive </td> 
      <td colname="col2"> true または false。falseの場合、Remote URIパラメーターで指定されたディレクトリの最上位のファイルのみが複製されます。 詳しくは、この表のパスの統合を参照してください。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> リモートURI </td> 
      <td colname="col2">RepeaterのファイルストアにアクセスするためのURI <span class="wintitle"> (ファイルマスク</span> )。 この <span class="filepath"> URIを使用してイベントデータにアクセスできるように、</span> Repeater上のCommunications <span class="wintitle"></span> .cfgファイルを設定する必要があります。 「イベントデ <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> ータ領域の監視」を参照してくださ</a>い。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> サーバー </td> 
      <td colname="col2">ターゲットの <span class="wintitle"> Insight</span> Serverがイベントデータファイルを取得する <span class="keyword"> Repeater</span> （リピーター）のパラメーター。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 名前 </td> 
      <td colname="col2">(オプション)リピータを識別する <span class="wintitle"> 名前</span>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Server Common Name </td> 
      <td colname="col2">「Use SSL」がtrueに設定されている場合にのみ必須です。 イベントデータが <span class="wintitle"> 格納される</span> Repeaterの共通名。 この名前は、コンピューターの通信証明書に記載されている共通名と一致する必要があります。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Address </td> 
      <td colname="col2">イベントデータが格納されるリピータ <span class="wintitle"> ーの</span> 、ホスト名または数値のIPアドレス。 サーバーの共通名が有効なエントリではありません。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> データ送信に使用するポート。 デフォルトポートは 80 です。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Client Certificate </td> 
      <td colname="col2">「Use SSL」がtrueに設定されている場合にのみ必須です。 Repeaterへの接続に使用するライセンス証明書の <span class="wintitle"> 名前</span>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Use SSL </td> 
      <td colname="col2"> <p>データ送信にSSLを使用するかどうかを指定します。 オプションはtrueまたはfalseで、デフォルト値はfalseです。 </p> <p> <p>注意：SSLの使用は、パフォーマンスに悪影響を与える可能性があるので、お勧めしません。 リピータをターゲットコンピュータに接続するネットワークの安全性が低い場合を除き <span class="wintitle"></span> 、SSLは不要です。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> End Time, Start Time </td> 
      <td colname="col2"> <p>（オプション）ターゲットの <span class="keyword"></span> Insightサーバーにコピーするイベントデータファイルのセットを、「開始時間」と「終了時間」で定義された範囲のデータを含むイベントデータファイルに制限します。 Start Timeを設定した場合、すべてのログエントリが指定した開始時間より前の時間にあるイベントデータファイルはコピーされません。 End Timeを設定した場合、指定した時刻以降のすべてのログエントリがコピーされないイベントデータファイル。 ファイル内のデータの一部のみが指定された範囲にある場合、ファイル全体がターゲットマシンにコピーされます。 </p> <p>この時刻には、次のいずれかの形式を使用することをお勧めします。 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">January 1 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">Jan 1 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>注意：タイムゾーンを指定する必要があります。 タイムゾーンを指定しない場合、デフォルトではシステム時間が設定されません。 If you wish to implement Daylight Saving Time or a similar clock-shifting policy, you must save the <span class="filepath"> .dst</span> file containing the appropriate rules in the Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> machine. サポートされているタイムゾーンの省略形の一覧と、夏時間の導入に関する情報については、タイムゾーンコードを <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> 参照してくださ</a>い。 </p> </p> <p> <p>注意： これらの設定を使用するには、イベントデータファイルの名前がISO日付(YYYYMMDD)で始まり、各ファイルにその日の午前12時から24時間のデータが含まれている必要があります。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 次の手順を実行して、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。
   1. で、列 [!DNL Server Files Manager]内のファイルのチェックマークを右クリックし [!DNL Temp] て、/ **[!UICONTROL Save to]** &lt; ***[!UICONTROL server name]**>を選択します*。

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

次の例は、Flatten PathsパラメーターとRecursiveパラメーターの両方がtrueに設定されている場合のファイルのコピー方法を示しています。

リモートURIが[!DNL [!DNL /RemoteRoot/] E:\LocalRoot\]で、ローカルパスが[!DNL ]であるとします。 リモート( [!DNL Repeater])マシン上では、ファイルは次のように整理されます。

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

レプリケーションが完了すると、ローカルディレクトリには次のファイルが含まれます。

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

ローカルディレクトリには、サブディレクトリは作成されず、リモートディレクトリツリーのすべてのファイルがローカルディレクトリの最上位に配置されます。

>[!NOTE]
>
>リモートマシン上の各サブディレクトリ内のファイルが同じ名前を共有している場合、が停止したり、その他の未定義の [!DNL Replication Service] 動作が発生したりすることがあります。
