---
description: 元のイベントデータが格納されているリピーターからデータを取得するように、ターゲット Insight サーバーを設定する必要があります。
title: レプリケーションサービスの設定
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 5%

---

# レプリケーションサービスの設定{#configuring-the-replication-service}

{{eol}}

元のイベントデータが格納されているリピーターからデータを取得するように、ターゲット Insight サーバーを設定する必要があります。

からのデータの取得を設定するには [!DNL Repeater] ターゲットに [!DNL Insight Server]を編集する場合、 [!DNL Replicate.cfg] ファイル [!DNL Components] ターゲット上のフォルダー [!DNL Insight Server(s)] 次の手順で説明するように、

**次の手順で [!DNL Replication Service] ターゲットマシン上**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。
1. ターゲットのアイコンを右クリックします。 [!DNL Insight Server] を設定して、 **[!UICONTROL Server Files]**.
1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Components]** をクリックして、その内容を表示します。 [!DNL Replicate.cfg] ファイルは、このディレクトリ内に格納されています。
1. チェックマーク ( *サーバー名* 列 [!DNL Replicate.cfg] をクリックし、 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Replicate.cfg].
1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. この [!DNL Replicate.cfg] ウィンドウが開きます。
1. 内 [!DNL Replicate.cfg] ウィンドウ、クリック **[!UICONTROL Replicate.cfg]**&#x200B;を、 **[!UICONTROL component]** をクリックして、その内容を表示します。
1. 次の例と表をガイドとして使用して、パラメーターを編集します。

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
      <td colname="col2"> <p>上のディレクトリ <span class="wintitle"> リピーター</span> ターゲットにコピー（レプリケート）する <span class="keyword"> Insight サーバー</span>. この <span class="wintitle"> レプリケーションサービス</span> 1 つのディレクトリから複数のディレクトリをレプリケーションできます。 <span class="wintitle"> リピーター</span>. </p> <p>新しいディレクトリを追加するには、右クリックします。 <span class="uicontrol"> ディレクトリ</span> をクリックし、 <span class="uicontrol"> 新規追加</span> &gt; <span class="uicontrol"> ディレクトリ</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> パスを統合 </td> 
      <td colname="col2"> <p>true または false。このパラメーターの設定で定義されるアクションは、このファイル内の Recursive パラメーターの設定によって異なります。 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Recursive が false の場合、Flatten Paths は無効です。 Remote URI パラメーターで指定されたディレクトリの最上位レベルのファイルのみがレプリケートされます。 </li>
      <li id="li_8FDB351102344E3995035557445354BB">Recursive が true で Flatten Paths が false の場合、リモートのディレクトリ構造 (<span class="wintitle"> リピーター</span>) ディレクトリは、ターゲット上のローカルパスで正確に複製されます <span class="keyword"> Insight サーバー</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Recursive と Flatten Paths の両方が true の場合、ローカルパスにサブディレクトリは作成されません。 代わりに、リモートディレクトリツリーのすべてのファイルは、ローカルディレクトリの最上位に配置されます。 </li>
      </ul></p> <p> <p>注意：Flatten Paths と Recursive の両方が true で、リモートマシン上の様々なサブディレクトリ内のファイルが同じ名前を共有する場合、 <span class="wintitle"> レプリケーションサービス</span> が停止したり、その他の未定義の動作が発生する場合があります。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> ローカルパス </td> 
      <td colname="col2">から取得したファイルの保存場所 <span class="wintitle"> リピーター</span>. パスは <span class="keyword"> Insight サーバー</span> インストールディレクトリ。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursive </td> 
      <td colname="col2"> true または false。false の場合、Remote URI パラメーターで指定されたディレクトリの最上位レベルのファイルのみがレプリケートされます。 この表の「パスの統合」を参照してください。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> リモート URI </td> 
      <td colname="col2">ファイルマスクを含む、 <span class="wintitle"> リピーターの</span> ファイルの保存場所。 この <span class="filepath"> Communications.cfg</span> ファイルを <span class="wintitle"> リピーター</span> は、この URI を使用してイベントデータにアクセスできるように設定する必要があります。 詳しくは、 <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> イベントデータ容量の監視</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> サーバー </td> 
      <td colname="col2">のパラメーター <span class="wintitle"> リピーター</span> ターゲットから <span class="keyword"> Insight サーバー</span> イベントデータファイルを取得します。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 名前 </td> 
      <td colname="col2">（オプション）。識別する名前 <span class="wintitle"> リピーター</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Server Common Name </td> 
      <td colname="col2">Use SSL が true に設定されている場合にのみ必須です。 の共通名 <span class="wintitle"> リピーター</span> イベントデータが格納される場所です。 この名前は、コンピューターの通信証明書に一覧表示されている共通名と一致する必要があります。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Address </td> 
      <td colname="col2">のホスト名または数値 IP アドレス <span class="wintitle"> リピーター</span> イベントデータが格納される場所です。 サーバーの共通名が有効なエントリではありません。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> データ送信に使用するポート。 デフォルトポートは 80 です。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL Client Certificate </td> 
      <td colname="col2">Use SSL が true に設定されている場合にのみ必須です。 への接続に使用するライセンス証明書の名前 <span class="wintitle"> リピーター</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Use SSL </td> 
      <td colname="col2"> <p>SSL をデータ送信に使用するかどうかを決定します。 オプションは true または false で、デフォルト値は false です。 </p> <p> <p>注意：SSL の使用は、パフォーマンスに悪影響を与える可能性があるので、お勧めしません。 SSL は、 <span class="wintitle"> リピーター</span> ターゲットマシンには安全ではありません。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 終了時刻、開始時刻 </td> 
      <td colname="col2"> <p>（オプション）ターゲットにコピーされるイベントデータファイルのセットを制限します <span class="keyword"> Insight サーバー</span> を、Start Time と End Time で定義された範囲のデータを含むデータに追加します。 Start Time が設定されている場合、すべてのログエントリが指定された開始時刻より前のログエントリを含むイベントデータファイルはコピーされません。 End Time が設定されている場合、指定された時刻以降のすべてのログエントリがコピーされないイベントデータファイル。 ファイル内のデータの一部のみが指定された範囲にある場合、ファイル全体がターゲットマシンにコピーされます。 </p> <p>この時刻には、次のいずれかの形式を使用することをお勧めします。 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">2013 年 1 月 1 日 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">2013 年 1 月 1 日 HH:MM:SS GMT </li>
      </ul></p> <p> <p>注意：タイムゾーンを指定する必要があります。 指定しない場合、タイムゾーンはデフォルトではシステム時間に設定されません。 夏時間などの時計シフティングを実装する場合は、 <span class="filepath"> .dst</span> ファイル内の <span class="keyword"> Insight サーバー</span> マシン。 サポートされるタイムゾーンの略語と夏時間の導入に関する情報については、 <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> タイムゾーンのコード</a>. </p> </p> <p> <p>注意：これらの設定を使用するには、イベントデータファイルの名前が ISO 日付 (YYYYMMDD) で始まり、各ファイルには、その日の午前 12 時から 24 時間のデータが含まれている必要があります。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.
   1. 内 [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列と選択 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

次の例は、「Flatten Paths」パラメータと「Recursive」パラメータの両方が true に設定されている場合のファイルのコピー方法を示しています。

リモート URI が [!DNL /RemoteRoot/] ローカルパスは [!DNL E:\LocalRoot\] です。 リモート ( [!DNL Repeater])」マシンでは、ファイルは次のように整理されます。

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
>リモートマシン上の様々なサブディレクトリ内のファイルが同じ名前を共有している場合、 [!DNL Replication Service] が停止したり、その他の未定義の動作が発生する場合があります。
