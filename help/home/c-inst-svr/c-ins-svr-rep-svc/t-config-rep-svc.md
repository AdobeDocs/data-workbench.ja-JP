---
description: 元のターゲットデータが格納されているリピーターからデータを取得するように、イベントインサイトサーバーを設定する必要があります。
solution: Analytics
title: レプリケーションサービスの設定
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 6%

---


# レプリケーションサービスの設定{#configuring-the-replication-service}

元のターゲットデータが格納されているリピーターからデータを取得するように、イベントインサイトサーバーを設定する必要があります。

からターゲットへのデータの取得を設定するには、次の手順に従って、ターゲット上の [!DNL Repeater] フォルダに提供される [!DNL Insight Server]ファイルを編集する必要があります。 [!DNL Replicate.cfg] ファイルは次の手順 [!DNL Components][!DNL Insight Server(s)] で取得します。

**ターゲットマシン[!DNL Replication Service]でを設定するには**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。
1. 設定するターゲットのアイコンを右クリック [!DNL Insight Server] し、をクリックし **[!UICONTROL Server Files]**&#x200B;ます。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Replicate.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the *server name* column for [!DNL Replicate.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Replicate.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. ウィンドウが開き [!DNL Replicate.cfg] ます。
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
      <td colname="col2"> <p>ターゲット <span class="wintitle"> Insightサーバーにコピー</span> （複製）する、リピーター上のディレクトリ <span class="keyword"></span>。 Replication Service <span class="wintitle"> では、1つの</span> リピータから複数のディレクトリを複製できます <span class="wintitle"></span>。 </p> <p>新しいディレクトリを追加するには、 <span class="uicontrol"> Directories</span> （ディレクトリ）を右クリックし、 <span class="uicontrol"> new</span><span class="uicontrol"> /Directory（ディレクトリ）をクリックします</span>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> パスの統合 </td> 
      <td colname="col2"> <p>true または false。このパラメーターの設定で定義されるアクションは、このファイル内のRecursiveパラメーターの設定によって異なります。 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Recursiveがfalseの場合、Flatten Pathsは無効です。 Remote URIパラメーターで指定されたディレクトリの最上位にあるファイルのみが複製されます。 </li>
      <li id="li_8FDB351102344E3995035557445354BB">RecursiveがtrueでFlatten Pathsがfalseの場合、リモート(<span class="wintitle"> Repeater</span>)ディレクトリのディレクトリ構造は、ターゲット <span class="keyword"> Insightサーバーのローカルパスに正確に複製されます</span>。 </li>
      <li id="li_3114B191C73744658799E112C61AB004">RecursiveとFlatten Pathsの両方がtrueの場合、ローカルパスにサブディレクトリは作成されません。 代わりに、リモートディレクトリツリーのすべてのファイルは、ローカルディレクトリの最上位に配置されます。 </li>
      </ul></p> <p> <p>注意：Flatten PathsとRecursiveの両方がtrueで、リモートマシン上の様々なサブディレクトリ内のファイルが同じ名前を共有している場合、 <span class="wintitle"> Replication Service</span> が停止したり、未定義の他の動作が発生したりする場合があります。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> ローカルパス </td> 
      <td colname="col2">リピータから取得したファイルのストレージ <span class="wintitle"> 位置</span>。 パスは、 <span class="keyword"> Insight Server</span> インストールディレクトリからの相対パスです。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursive </td> 
      <td colname="col2"> true または false。falseの場合、Remote URIパラメーターで指定されたディレクトリの最上位のファイルのみが複製されます。 詳しくは、この表の「パスの統合」を参照してください。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> リモートURI </td> 
      <td colname="col2">ファイルマスクを含む、 <span class="wintitle"> RepeaterのファイルストアにアクセスするURIです</span> 。 このURIを使用して <span class="filepath"> イベントデータにアクセスできるように、</span> RepeaterのCommunications.cfg <span class="wintitle"></span> ファイルを設定する必要があります。 See <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitoring Event Data Space</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> サーバー </td> 
      <td colname="col2">ターゲット <span class="wintitle"> Insightサーバーがイベントデータファイルを取得する</span> Repeater <span class="keyword"></span> （リピーター）のパラメーター。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 名前 </td> 
      <td colname="col2">（オプション）リピータを識別する名前 <span class="wintitle"></span>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Server Common Name </td> 
      <td colname="col2">「Use SSL」がtrueに設定されている場合にのみ必要です。 イベントデータが格納される <span class="wintitle"> リピータの共通名</span> 。 この名前は、コンピューターの通信証明書に一覧表示されている共通名と一致する必要があります。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Address </td> 
      <td colname="col2">イベントデータが格納されるリピータのホスト名または <span class="wintitle"> 数値のIPアドレス</span> 。 サーバーの共通名が有効なエントリではありません。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> データ送信に使用するポート。 デフォルトポートは 80 です。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Client Certificate </td> 
      <td colname="col2">「Use SSL」がtrueに設定されている場合にのみ必要です。 リピーターへの接続に使用するライセンス証明書の名前 <span class="wintitle"></span>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Use SSL </td> 
      <td colname="col2"> <p>データ送信にSSLを使用するかどうかを指定します。 オプションはtrueまたはfalseで、デフォルト値はfalseです。 </p> <p> <p>注意：SSLの使用は、パフォーマンスに悪影響を与える可能性があるので、お勧めしません。 リピータをターゲットマシンに接続するネットワークのセキュリティが低い場合を除き、 <span class="wintitle"> SSLは必要ありません</span> 。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 終了時間、開始時間 </td> 
      <td colname="col2"> <p>（オプション）ターゲット <span class="keyword"></span> Insightサーバーにコピーするイベントデータファイルのセットを、開始時間と終了時間で定義された範囲のデータを含むファイルに制限します。 「開始時間」を設定した場合、すべてのログエントリが指定した開始時間より前に存在するイベントデータファイルはコピーされません。 End Timeを設定した場合、指定した時刻以降のすべてのログエントリが含まれるイベントデータファイルはコピーされません。 ファイル内のデータの一部だけが指定された範囲に含まれる場合、ファイル全体がターゲットマシンにコピーされます。 </p> <p>この時刻には、次のいずれかの形式を使用することをお勧めします。 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">January 1 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">Jan 1 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>注意：タイムゾーンを指定する必要があります。 タイムゾーンを指定しない場合、デフォルトではシステム時間に設定されません。 If you wish to implement Daylight Saving Time or a similar clock-shifting policy, you must save the <span class="filepath"> .dst</span> file containing the appropriate rules in the Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> machine. サポートされるタイムゾーンの略称と夏時間の導入に関するリストについては、 <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> タイムゾーンのコードを参照してください</a>。 </p> </p> <p> <p>注意： これらの設定を使用するには、イベントデータファイルの名前がISO日付(YYYYMMDD)で始まり、各ファイルには、その日の午前12時から24時間のデータが含まれている必要があります。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。
   1. で、列内 [!DNL Server Files Manager]のファイルのチェックマークを右クリックし、 [!DNL Temp] / **[!UICONTROL Save to]** &lt; *>を選択します&#x200B;**[!UICONTROL server name]***。

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

次の例は、Flatten PathsパラメーターとRecursiveパラメーターの両方がtrueに設定されている場合にファイルをコピーする方法を示しています。

「Remote URI」 [!DNL /RemoteRoot/] と「Local Path」が [!DNL E:\LocalRoot\]、 リモート( [!DNL Repeater])マシン上のファイルは、次のように構成されます。

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

レプリケーションが完了すると、ローカルディレクトリには次のファイルが含まれます。

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

ローカルディレクトリにはサブディレクトリは作成されず、リモートディレクトリツリーのすべてのファイルはローカルディレクトリの最上位に配置されます。

>[!NOTE]
>
>リモートマシン上の様々なサブディレクトリ内のファイルが同じ名前を共有している場合、が停止したり、その他の未定義の動作が発生した [!DNL Replication Service] りする場合があります。
