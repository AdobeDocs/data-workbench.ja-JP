---
description: '[ 詳細な状態 ] インターフェイスは、Data Workbench・サーバー・コンピュータのエラーやその他の問題のトラブルシューティングに役立ちます。'
title: 詳細ステータスインターフェイス
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 75%

---

# 詳細ステータスインターフェイス{#detailed-status-interface}

{{eol}}

[ 詳細な状態 ] インターフェイスは、Data Workbench・サーバー・コンピュータのエラーやその他の問題のトラブルシューティングに役立ちます。

これには、 [!DNL Transform] これらのコンピューター上で実行されているプロファイル、または [!DNL Report] コンピューターサーバーのクライアントであるData Workbenchー。 次にアクセスできます： [!DNL Master Server] および [!DNL Query Server Detailed Status] インターフェイスを介して [!DNL Admin] メニュー 次の手順で [!DNL Detailed Status] 他のコンピュータ用のインターフェイス、 [!DNL Servers Manager]をクリックし、ステータスを表示するサーバーのノードを右クリックして、 **[!UICONTROL Detailed Status]**. 詳しくは、 [サーバーマネージャー](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Data Workbench・サーバの詳細については、 *サーバー製品のインストールおよび管理ガイド*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>の情報を更新するには、以下を実行します。 [!DNL Detailed Status] インターフェイスで、 **[!UICONTROL Detailed Status]** 見出しとクリック **[!UICONTROL Refresh]**.

次の表に、 [!DNL Detailed Status] インターフェイス。

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
   <td colname="col2"> <p><span class="uicontrol">パフォーマンス</span>／<span class="uicontrol">ディメンション</span>／<span class="uicontrol">ディスク使用量</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt; </i>または<span class="uicontrol">パフォーマンス</span>／<span class="uicontrol">ディメンション</span>／<span class="uicontrol">メモリ使用量</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i> をクリックします。 </p> <p>「<span class="wintitle">ディスク使用量</span>」フィールドには、各ディメンション名と、保存に必要なディスクスペースの量（MB 単位）が表示されます。関連するクエリを完了するには、Data Workbenchサーバーがすべてのデータを読み取る必要があるので、ディスク使用量の数値が大きいと、クエリ時間に悪影響を与える可能性があります。 ディメンションのディスク使用量を低下させると、関連クエリーの完了に要する時間を短縮できます。 </p> <p>「<span class="wintitle">メモリ使用量</span>」フィールドには、各ディメンションの要素数と、要素名のリストを保存するために必要なメモリの量が表示されます。Data Workbenchサーバーは各要素を読み取る必要があるので、要素の数が多いと、クエリ中に使用されるメモリの量に悪影響を与える可能性があります。 ディメンションの要素数を減らすと、関連クエリーの完了に要する時間を短縮できます。 </p> <p>例：<code>+&nbsp;Performance
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
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Real Time — クエリの実行にData Workbenchサーバーが使用できた時間。 </li> 
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
   <td colname="col1"> <p>表示する <span class="wintitle"> レポートサーバー</span> ステータス <span class="keyword"> レポート</span> サーバーに接続するData Workbench </p> </td> 
   <td colname="col2"> <p>「<span class="uicontrol">レポートサーバーのステータス</span>」をクリックします。 </p> <p><span class="wintitle">詳細ステータス</span>インターフェイスのこのセクションには、<span class="filepath">Report Server.cfg</span> ファイルのコピー、実行中のレポート数に関する情報（現在のスライス）、最新のエラーに関する情報（前回のエラー）が含まれています。 </p> <p><span class="filepath">Report Server.cfg</span> ファイルの編集手順については、『<i>Data Workbench レポートガイド</i>』を参照してください。 </p> <p> <p>注意：この <span class="wintitle"> レポートサーバーのステータス</span> セクションが <span class="wintitle"> 詳細なステータス</span> インターフェイスでは、表示するData Workbenchサーバーを設定する必要があります <span class="wintitle"> レポートサーバーのステータス</span>. 手順については、『<i>Data Workbench レポートガイド</i>』を参照してください。 </p> </p> </td> 
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
   <td colname="col2"> <p>ログソースごとの行数を詳細なステータスで報告する必要がある場合は、Data Workbench管理者が「ログソース ID」を定義し、カスタムプロファイルの Log Processing.cfg で一意の名前を指定する必要があります。 </p> </td> 
  </tr> 
 </tbody> 
</table>
