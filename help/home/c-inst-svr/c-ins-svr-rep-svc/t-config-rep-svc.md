---
description: 元のイベントデータが保存されているリピーターからデータを取得するように、ターゲットInsightサーバーを設定する必要があります。
title: レプリケーションサービスの設定
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 6%

---

# レプリケーションサービスの設定{#configuring-the-replication-service}

元のイベントデータが保存されているリピーターからデータを取得するように、ターゲットInsightサーバーを設定する必要があります。

[!DNL Repeater]からターゲット[!DNL Insight Server]へのデータの取得を設定するには、次の手順に従って、ターゲット[!DNL Insight Server(s)]の[!DNL Components]フォルダーに格納されている[!DNL Replicate.cfg]ファイルを編集する必要があります。

**ターゲットマシン [!DNL Replication Service] でを設定するには**

1. [!DNL Insight]の「[!DNL Admin] > [!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして「サーバーマネージャー」ワークスペースを開きます。
1. 設定するターゲット[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。
1. [!DNL Server Files Manager]で、**[!UICONTROL Components]**&#x200B;をクリックして内容を表示します。 [!DNL Replicate.cfg] ファイルは、このディレクトリ内に格納されています。
1. *[!DNL Replicate.cfg]のサーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Replicate.cfg]の[!DNL Temp]列にチェックマークが表示されます。
1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。 [!DNL Replicate.cfg]ウィンドウが開きます。
1. [!DNL Replicate.cfg]ウィンドウで、「**[!UICONTROL Replicate.cfg]**」をクリックし、次に「**[!UICONTROL component]**」をクリックして内容を表示します。
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
      <td colname="col2"> <p>ターゲット<span class="keyword"> Insightサーバー</span>にコピー（レプリケート）する<span class="wintitle">リピーター</span>上のディレクトリ。 <span class="wintitle">レプリケーションサービス</span>を使用すると、1つの<span class="wintitle">リピーター</span>から複数のディレクトリをレプリケーションできます。 </p> <p>新しいディレクトリを追加するには、<span class="uicontrol"> Directories</span>を右クリックし、<span class="uicontrol"> Add new</span> / <span class="uicontrol"> Directory</span>をクリックします。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> パスの統合 </td> 
      <td colname="col2"> <p>true または false。このパラメーターの設定で定義されるアクションは、このファイル内のRecursiveパラメーターの設定によって異なります。 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Recursiveがfalseの場合、Flatten Pathsは無効です。 Remote URIパラメーターで指定されたディレクトリの最上位レベルのファイルのみがレプリケートされます。 </li>
      <li id="li_8FDB351102344E3995035557445354BB">RecursiveがtrueでFlatten Pathsがfalseの場合、リモート(<span class="wintitle"> Repeater</span>)ディレクトリのディレクトリ構造は、ターゲット<span class="keyword"> Insight Server</span>上のローカルパスに正確に複製されます。 </li>
      <li id="li_3114B191C73744658799E112C61AB004">RecursiveとFlatten Pathsの両方がtrueの場合、ローカルパスにサブディレクトリは作成されません。 代わりに、リモートディレクトリツリーのすべてのファイルがローカルディレクトリの最上位に配置されます。 </li>
      </ul></p> <p> <p>注意：Flatten PathsとRecursiveの両方がtrueで、リモートマシン上の様々なサブディレクトリ内のファイルが同じ名前を共有している場合、<span class="wintitle">レプリケーションサービス</span>が停止したり、その他の未定義の動作が発生したりする可能性があります。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> ローカルパス </td> 
      <td colname="col2"><span class="wintitle">リピーター</span>から取得したファイルの保存場所。 パスは、<span class="keyword"> Insightサーバー</span>のインストールディレクトリを基準とした相対パスです。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursive </td> 
      <td colname="col2"> true または false。falseの場合、Remote URIパラメーターで指定されたディレクトリの最上位レベルのファイルのみがレプリケートされます。 この表の「パスの統合」を参照してください。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> リモートURI </td> 
      <td colname="col2"><span class="wintitle">リピーターの</span>ファイルストアにアクセスするためのURI（ファイルマスクを含む）。 <span class="wintitle"> Repeater</span>上の<span class="filepath"> Communications.cfg</span>ファイルを設定し、このURIを使用してイベントデータにアクセスできるようにする必要があります。 <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440">イベントデータ空間の監視</a>を参照してください。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> サーバー </td> 
      <td colname="col2">ターゲット<span class="keyword"> Insightサーバー</span>がイベントデータファイルを取得する<span class="wintitle">リピーター</span>のパラメーター。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 名前 </td> 
      <td colname="col2">（オプション）<span class="wintitle">リピータ</span>を識別する名前。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Server Common Name </td> 
      <td colname="col2">Use SSLがtrueに設定されている場合にのみ必要です。 イベントデータが格納される<span class="wintitle">リピーター</span>の共通名。 この名前は、コンピューターの通信証明書に一覧表示されている共通名と一致する必要があります。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Address </td> 
      <td colname="col2">イベントデータが格納される<span class="wintitle">リピーター</span>のホスト名または数値IPアドレス。 サーバーの共通名が有効なエントリではありません。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> データ送信に使用するポート。 デフォルトポートは 80 です。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Client Certificate </td> 
      <td colname="col2">Use SSLがtrueに設定されている場合にのみ必要です。 <span class="wintitle">リピーター</span>への接続に使用するライセンス証明書の名前。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Use SSL </td> 
      <td colname="col2"> <p>データ送信にSSLを使用するかどうかを決定します。 オプションはtrueまたはfalseで、デフォルト値はfalseです。 </p> <p> <p>注意：SSLの使用は、パフォーマンスに悪影響を与える可能性があるので、お勧めしません。 <span class="wintitle">リピータ</span>をターゲットマシンに接続するネットワークが安全でない限り、SSLは必要ありません。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 終了時間、開始時間 </td> 
      <td colname="col2"> <p>（オプション）ターゲット<span class="keyword"> Insight Server</span>にコピーするイベントデータファイルのセットを、Start TimeとEnd Timeで定義された範囲のデータを含むイベントデータファイルに制限します。 Start Timeを設定した場合、すべてのログエントリが指定した開始時刻より前のイベントデータファイルはコピーされません。 End Timeを設定した場合、指定した時刻以降のすべてのログエントリがコピーされないイベントデータファイル。 ファイル内のデータの一部のみが指定された範囲にある場合、ファイル全体がターゲットマシンにコピーされます。 </p> <p>この時刻には、次のいずれかの形式を使用することをお勧めします。 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">January 1 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">Jan 1 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>注意：タイムゾーンを指定する必要があります。 指定しない場合、タイムゾーンはデフォルトではシステム時間に設定されません。 夏時間などの時計調整ポリシーを実装する場合は、適切なルールを含んだ<span class="filepath"> .dst</span>ファイルをBase\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span>マシンに保存する必要があります。 サポートされているタイムゾーンの略語と夏時間の実装に関する情報については、 <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211">タイムゾーンコード</a>を参照してください。 </p> </p> <p> <p>注意： これらの設定を使用するには、イベントデータファイルの名前がISO日付(YYYYMMDD)で始まり、各ファイルには、その日の午前12時から24時間のデータが含まれている必要があります。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。
   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]***&#x200B;を選択します。

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

次の例は、Flatten PathsパラメータとRecursiveパラメータの両方がtrueに設定されている場合に、ファイルをコピーする方法を示しています。

リモートURIが[!DNL /RemoteRoot/]で、ローカルパスが [!DNL E:\LocalRoot\]であるとします。 リモート([!DNL Repeater])マシンでは、ファイルは次のように編成されます。

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

レプリケーションが完了すると、ローカルディレクトリには次のファイルが含まれます。

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

ローカルディレクトリには、サブディレクトリは作成されず、リモートディレクトリツリーのすべてのファイルがローカルディレクトリの最上位レベルに配置されます。

>[!NOTE]
>
>リモートマシン上の様々なサブディレクトリ内のファイルが同じ名前を共有している場合、[!DNL Replication Service]が停止したり、その他の未定義の動作が発生したりする可能性があります。
