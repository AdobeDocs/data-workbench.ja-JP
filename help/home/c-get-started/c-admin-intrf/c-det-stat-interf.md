---
description: 「詳細なステータス」インターフェイスは、Data Workbenchサーバーコンピューターのエラーやその他の問題のトラブルシューティングに役立ちます。
solution: Analytics
title: 詳細ステータスインターフェイス
topic: Data workbench
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
translation-type: tm+mt
source-git-commit: fd3afa80250d5ae20b7758ba840fd4d436545cf2

---


# Detailed Status interface{#detailed-status-interface}

「詳細なステータス」インターフェイスは、Data Workbenchサーバーコンピューターのエラーやその他の問題のトラブルシューティングに役立ちます。

これには、これらのコンピ [!DNL Transform] ューターで実行されているすべてのプロファイル、また [!DNL Report] はData Workbenchサーバーのクライアントであるコンピューターが含まれます。 メニューを使用して、イ [!DNL Master Server] ンターフ [!DNL Query Server Detailed Status] ェイスにアクセスで [!DNL Admin] きます。 To access the [!DNL Detailed Status] interface for other computers, in the [!DNL Servers Manager], right-click the node of the server for which you want to view status and click **[!UICONTROL Detailed Status]**. See [The Servers Manager](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

For more information about the Data Workbench server, see the *Server Products Installation and Administration Guide*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>インターフェイスの情報を更新す [!DNL Detailed Status] るには、見出しを右クリック **[!UICONTROL Detailed Status]** し、をクリックしま **[!UICONTROL Refresh]**&#x200B;す。

The following table lists the tasks that can be completed using the [!DNL Detailed Status] interface.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 実行する作業... </th> 
   <th colname="col2" class="entry"> 手順... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>各コンピューターコンポーネントと現在のステータスを表示するには </p> </td> 
   <td colname="col2"> <p>「<span class="uicontrol">コンポーネントステータス</span>」をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンピューターのメモリの使用量を表示するには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">メモリステータス</span>／<span class="uicontrol">アドレス空間読み込み</span>をクリックします。 </p> <p>アドレス空間読み込みのモニタリングについて詳しくは、『<i>サーバー製品のインストールと管理ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンピューターが /3GB スイッチを使用するように設定されているかどうか判断するには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">メモリステータス</span>／<span class="uicontrol">処理アドレス空間</span>をクリックします。 </p> <p>「<span class="wintitle">合計</span>」フィールドに 3000000 KB を超える値が表示される場合、コンピューターは /3GB スイッチを使用するように設定されています。 </p> <p>/3GB スイッチについて詳しくは、『<i>サーバー製品のインストールと管理ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>各ディメンションの保存およびディメンションの要素名の保存に使用されているディスクスペースとメモリの量をモニタリングするには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">パフォーマンス</span>／<span class="uicontrol">ディメンション</span>／<span class="uicontrol">ディスク使用量</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt; </i>または<span class="uicontrol">パフォーマンス</span>／<span class="uicontrol">ディメンション</span>／<span class="uicontrol">メモリ使用量</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i> をクリックします。 </p> <p>「<span class="wintitle">ディスク使用量</span>」フィールドには、各ディメンション名と、保存に必要なディスクスペースの量（MB 単位）が表示されます。Data Workbenchサーバーは、関連するクエリーを完了するためにすべてのデータを読み取る必要があるので、ディスク使用量の数値が大きいと、クエリー時間に悪影響を与える可能性があります。 ディメンションのディスク使用量を低下させると、関連クエリーの完了に要する時間を短縮できます。 </p> <p>「<span class="wintitle">メモリ使用量</span>」フィールドには、各ディメンションの要素数と、要素名のリストを保存するために必要なメモリの量が表示されます。Data Workbenchサーバーは各要素を読み取る必要があるので、要素の数が多いと、クエリー中に使用されるメモリの量に悪影響を与える可能性があります。 ディメンションの要素数を減らすと、関連クエリーの完了に要する時間を短縮できます。 </p> <p>例：<code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ログ処理および変換に含まれるステージの CPU 使用量をモニタリングするには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">パフォーマンス</span>／<span class="uicontrol">CPU 使用量</span>／<span class="uicontrol">ログ処理</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i> または<span class="uicontrol">パフォーマンス</span>／<span class="uicontrol">CPU 使用量</span>／<span class="uicontrol">変換</span> &gt; &lt;<span class="uicontrol">profile name</span>&gt; をクリックします。 </p> <p>これらのフィールドセットにはそれぞれ、ログ処理および変換に含まれる各ステージの CPU 使用量（秒単位）が表示されます。 </p> <p>例：<code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>クエリーの完了に要する時間は、通常はすべてのディメンションの合計サイズに比例します。各ディメンションのサイズを確認してから、特定のディメンションが十分に役立っているか、ディメンションのパフォーマンスコストを正当化できるほど十分に使用されているかを評価できます。十分ではない場合、<span class="wintitle">プロファイルマネージャー</span>でディメンションを削除できます。 <p>要素名のリストが大きすぎる（128 MB 以上）ディメンションは、アドレス空間使用量合計が制限に近くない場合でも、「メモリ不足」エラーを生じさせることがあります。 </p> <p>また、Data Workbenchサーバークラスターを使用しているが、中央の正規化を使用していない場合、要素名のリストが大きいディメンションは、送信メモリ予算に大きな影響を与えます。 中央集中型の正規化について詳しくは、『<i>データセット設定ガイド</i>』を参照してください。 要素名のリストをすべて結合して保存するために必要なメモリ量が、クラスター内のすべてのサーバーで 100 MB を超える場合、クエリーアクティビティが軽量の場合でも、「送信メモリ予算を超えました」エラーが表示されることがあります。例えば、サーバー 4 台からなるクラスターがあり、各サーバーで 25 MB 以上が要素名のリストの保存に使用されている場合、エラーが表示されることがあります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ログ処理と変換に費やされる時間をモニタリングするには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">パフォーマンス</span>／<span class="uicontrol">CPU 使用量</span>／<span class="uicontrol">ログ処理</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i> または<span class="uicontrol">パフォーマンス</span>／<span class="uicontrol">CPU 使用量</span>／<span class="uicontrol">変換</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i> をクリックします。 </p> <p>これらのセクションのフィールドを確認すると、ログ処理と変換に必要な時間に悪影響を与える可能性があるフィルターおよび変換を特定できます。そして、処理時間が長い個々のフィルターと変換の設計に関して判断できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディスクスペースの使用量をモニタリングし、クエリー速度を上げるには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">パフォーマンス</span>／<span class="uicontrol">ログ処理フィールド</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i> をクリックします。 </p> <p>このセクションの各行項目は、<span class="filepath">Log Processing.cfg</span> ファイル内のパラメーターに対応しています。 これらのフィールドを確認すると、各パラメーターのメモリ使用量を確認できます。そして、非常に大きい個々の項目の設計に関して判断できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>以前の再処理または変換の経過時間を判断するには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">処理ステータス</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i>／<span class="uicontrol">処理モード履歴</span>をクリックします。 </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Real Time - Data Workbenchサーバーがクエリーの作成に使用できた時間。 </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Fast Input - この時間と Fast Merge 時間を足したものが、データセットの処理に必要な合計時間です。 </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Fast Merge - データセットの変換に必要な合計時間です。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「基準時点」の問題を診断するには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">処理ステータス</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i>／<span class="uicontrol">基準時点</span>／<span class="uicontrol">ソースの基準日</span>をクリックします。 </p> <p>各ソースの基準時点を確認すると、全体の基準日に悪影響を与える可能性があるソースを判断できます。そして、その特定のソースに関する問題に対処できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>実行中のクエリーが完了するまでの時間を予測するには </p> </td> 
   <td colname="col2"> <p>「<span class="uicontrol">実行エンジン</span>」をクリックします。 </p> <p>「<span class="wintitle">データスイープ時間</span>」フィールドを確認すると、クエリーの完了に要する時間を予測できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>このコンピューターで使用可能なすべてのプロファイルと、そのステータスに関する詳細をリストするには </p> </td> 
   <td colname="col2"> <p>「<span class="uicontrol">プロファイル</span>」をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レプリケーションステータスを表示するには </p> </td> 
   <td colname="col2"> <p>「<span class="uicontrol">コンポーネントステータス</span>」をクリックします。 </p> <p>コンポーネント複製のステータスを確認します。レプリケーションが実行中の場合は、OK が表示されます。 コンポーネント複製が失敗した場合、エラーメッセージが表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>To view <span class="wintitle"> Report Server</span> status for a <span class="keyword"> Report</span> computer that connects to the Data Workbench server </p> </td> 
   <td colname="col2"> <p>「<span class="uicontrol">レポートサーバーのステータス</span>」をクリックします。 </p> <p><span class="wintitle">詳細ステータス</span>インターフェイスのこのセクションには、<span class="filepath">Report Server.cfg</span> ファイルのコピー、実行中のレポート数に関する情報（現在のスライス）、最新のエラーに関する情報（前回のエラー）が含まれています。 </p> <p><span class="filepath">Report Server.cfg</span> ファイルの編集手順については、『<i>Data Workbench レポートガイド</i>』を参照してください。 </p> <p> <p>Note: If the <span class="wintitle"> Report Server Status</span> section does not appear in the <span class="wintitle"> Detailed Status</span> interface, you may need to configure the Data Workbench server to display <span class="wintitle"> Report Server Status</span>. 手順については、『<i>Data Workbench レポートガイド</i>』を参照してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>変換のメモリ使用量を表示するには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">処理ステータス</span>／<span class="uicontrol">変換</span>をクリックします。 </p> <p>変換について詳しくは、『<i>サーバー製品のインストールと管理ガイド</i>』および『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">詳細ステータス</span>インターフェイスをメモ帳などのテキストエディターで開いたり、他のユーザーに配布したりできる <span class="filepath">*.cfg</span> ファイルとして保存するには </p> </td> 
   <td colname="col2"> <p><span class="uicontrol">詳細なステータス</span>の見出しを右クリックし、「<span class="uicontrol">名前を付けてコピーを保存</span>」をクリックします。 </p> <p>注釈:  <p>「<span class="uicontrol">詳細なステータス</span>」見出しを右クリックし、「<span class="uicontrol">保存</span>」をクリックして <i>server name</i>/Status/ に保存する方法は、<span class="wintitle">詳細ステータス</span>インターフェイスでは使用できません。以下のエラーメッセージが表示されます。 </p> <p>Unable to save /Status/. 403 Forbidden </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol">ログソースごとの行数</span>指標を表示するには </p> </td> 
   <td colname="col2"> <p>ログソースごとの行数指標を詳細なステータスでレポートする必要がある場合、Data Workbench管理者は、「ログソースID」を定義し、カスタムプロファイルのLog Processing.cfgに一意の名前を指定する必要があります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

