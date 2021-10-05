---
description: システムの計画と実装を行う前に、Data Workbench（旧称  [!DNL Insight]）サーバーコンポーネントの最小要件と推奨事項を確認してください。
title: サーバーの必要システム構成
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# サーバーの必要システム構成{#server-system-requirements}

システムの計画と実装を行う前に、Data Workbench・サーバ・コンポーネントの最小要件と推奨事項を特定します。

## DPU の要件{#dpu-requirements}

サーバデータ処理ユニット (DPU) は、Data Workbenchの主なデータ処理要素です。 Data Workbenchからのネットワーク接続をリッスンし、ファイルサーバーユニット (FSU) から生のソースデータを読み取り、大量の計算リソースとストレージリソースを使用します。

### ライセンス容量 {#section-71850e13783443798b3df9eb22cc63dc}

ライセンス容量の情報については、*Adobe[!DNL Data Workbench (Insight)] サービス契約* のサービスの説明を参照してください。

>[!NOTE]
>
>Windows 2012 Servers の *MS System Center Endpoint Protection* の場合、これらの実行可能ファイルを ***除外プロセス：*** > に追加する必要があります。
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]

>


### DPU システムのRecommendationsと要件 {#section-ae30555959bf4a309c76d0fd597b5162}

Adobeは、ビジネスニーズを満たすData Workbenchデザインに関するレコメンデーションを提供します。 ただし、DPU ソフトウェアの最適化された特性により、OS/ハードウェアプラットフォームに固有の要件が置かれるので、オペレーティングシステム (OS) とハードウェアを選択する場合は、次のガイドラインが役立ちます。

1 つのデータセットが 1 つの DPU の容量または速度によって制限されている場合は、それらをクラスタリングできます。 例えば、DPU ソフトウェアの 3 つのライセンスを持つコピーを組み合わせて使用し、より大きなデータセットをより迅速に実行するとします。 データがマシン間で均等に分割されると、データセットのライセンス容量に 3 が掛けられます。 また、1 行あたりの処理速度は、1 つの DPU の 3 倍の速さになります。

DPU への投資で最高のパフォーマンスを実現するため、Adobeでは次の表に示す高性能コンポーネントを推奨しています。

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> </th>
   <th colname="col2" class="entry"> 必須 </th>
   <th colname="col3" class="entry"> 推奨 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>オペレーティングシステム </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td>
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>CPU </p> </td>
   <td colname="col2"> <p>レコメンデーションを参照してください。 </p> </td>
   <td colname="col3"> Intel または AMD の最新の 4 コア+プロセッサを推奨します。 最適なパフォーマンスを実現するには、8 コア速度とコストのトレードオフの場合は、4 コアを推奨します。 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>8 GB </p> </td>
   <td colname="col3"> <p>12 GB </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>作業用データストレージ </p> </td>
   <td colname="col2"> <p>1 TB 以上の論理一時ストレージ。 </p> <p>ディスク・サブ・システムへの低レイテンシ・アクセス </p> </td>
   <td colname="col3"> <p>一時的なストレージAdobeの場合は、次のいずれかをお勧めします。 </p>
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283">
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4～8) * （750 GB 以上） SATA HDD （3.5 インチスピンドル） </li>
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6～10) * （300 GB 以上） SATA HDD（2.5 インチスピンドル） </li>
    </ul> <p>これらは JBOD アレイで設定する必要があります。 また、総ディスク容量が 2 TB を超える場合は、2 ディスクの RAID1 ボリュームのアレイを使用できます。 たとえば、6 台のディスクを 3*（2*750 GB RAID 1 ペア）として構成します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>システムデータストレージ </p> </td>
   <td colname="col2"> <p>さらに、Adobeには、OS、DPU ソフトウェア、その他のシステムソフトウェア用に、適度なサイズ (20 GB) の高可用性ストレージが必要です。 </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>クラスタリングハードウェア </p> </td>
   <td colname="col2"> <p>レコメンデーションを参照してください。 </p> </td>
   <td colname="col3"> <p>同種のサーバセットを使用する。 DPU クラスターでは、最も遅いサーバーによって、データセット全体のパフォーマンスが低下します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ネットワークパフォーマンスのクラスタリング </td>
   <td colname="col2"> スイッチドギガビットイーサネット接続以上。 </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

### 代替ディスクサブシステム {#section-6f984eabe8074759aa9deaf17e3a68b7}

一時保存用の代替ディスクサブシステムを検討する際は、次の要素とガイドラインを考慮してください。

* DPU は、高性能のディスクシステムを異常に要求しているので、不十分なディスクサブシステムを設定すると、パフォーマンスのボトルネックを引き起こす可能性があります。
* DPU ソフトウェアは、一連の JBOD ディスクに対して独自のパフォーマンス指向のデータストライピングを実行します。 RAID を使用して速度を上げないでください。
* Adobeでは、DPU に 400 MB/秒以上の総持続帯域幅をディスクに割り当てることを推奨します。
* 平均読み取りサイズは非常に大きい（2 MB 以上）。 このため、15,000 または 10,000 SAS ディスクは、多くの場合、SATA ディスクよりも少し優れた（または劣った）パフォーマンスを発揮しますが、コストと容量に大きなペナルティがかかります。
* SAN アーキテクチャの使用は避けます。 経験から、SAN を必要なレベルで実行するコストは、通常、極端です。
* ローカル・ディスク・サブシステムはスクラッチ領域として使用され、HDD 障害からデータが永久的に失われることはないので、コストのかかる、低速で高可用性のシステムを避けることを検討してください。

### 速度に関する考慮事項 {#section-01330be232894e08a526d8d82b7c4eb2}

Adobeは、設定されたData Workbenchでデータが処理される速度に関して保証または表現を提供できません。これは、様々な要因がデータ処理速度に影響を与えるからです。以下の要因は含まれますが、これに限定されません。

* データの行数
* データのディメンション（列）の数
* カスタム処理手順の数と複雑さ
* クラスタリングの使用
* ハードウェアの速度

## ファイルサーバーの単位要件{#file-server-unit-requirements}

サーバの FSU(File Serving Unit) は、Data Workbenchの主要なデータ・ストレージおよび管理コンポーネントです。 FSU は、DPU に対する生のソースデータのファイルサーバとして機能し、必要に応じて DPU のクラスタリングを調整する。 各 FSU は、最大 5 個の DPU にソースデータを供給するライセンスを持っています。

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E">
 <thead>
  <tr>
   <th colname="col1" class="entry"> FSU コンポーネント </th>
   <th colname="col2" class="entry"> Recommendations </th>
   <th colname="col3" class="entry"> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>オペレーティングシステム、CPU、RAM </p> </td>
   <td colname="col2"> <p>これらの要件は、DPU の要件と同じです。 ただし、FSU の場合、Adobeは推奨事項に従うのではなく、最小要件を使用することをお勧めします。 </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ディスク・システム </p> <p>FSU には、大量のデータに対して高可用性で冗長なストレージが必要です。 Adobeがお客様と連携して、お客様の正確な要件を決定します。 </p> </td>
   <td colname="col1"> <p>Adobeの推奨事項： </p>
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539">
     <li id="li_F98750D509D640C68885D53FC691ED43">（12 以上） * （750 GB 以上） SATA HDD を RAID 5/6 構成で使用。 </li>
     <li id="li_3F84F63F9541476987015C27FDE8251B">100 MB/秒以上の持続帯域幅をサポートする、高パフォーマンスの SAN 接続。 </li>
    </ul> <p>FSU が生のソース・データを保持しているので、損失は回復できず、Adobeはこのデータを定期的にバックアップすることを示唆しています。 </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ネットワークのパフォーマンス </p> </td>
   <td colname="col2"> <p>Adobeでは、FSU と DPU 間のスイッチギガビットイーサネット接続が必要です。 </p> </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

## センサーの要件{#sensor-requirements}

Data Workbenchセンサーは、Web、アプリケーション、データ収集サーバーからイベントデータを収集し、任意のサーバーに送信します。 [!DNL Sensor’s] インストゥルメンテーションは、インターネットチャネルで発生するイベントを一貫して正確に測定します。[!DNL Sensor] は、Web サーバーソフトウェアとオペレーティングシステムの多くの組み合わせをサポートしています。

### センサーシステムRecommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

次の表に、[!DNL Sensor] の推奨システム構成を示します。

<table id="table_A132E06D6B8146C1B199B82464EA0898">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 機能 </th>
   <th colname="col2" class="entry"> 推奨 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>ディスクストレージ </p> </td>
   <td colname="col2"> <p>最低 512 MB です。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>32 MB の RAM が、HTTP またはそのホストである他のサーバーコンピューター上の <span class="wintitle"> センサー </span> に対して使用可能である必要があります。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ネットワークのパフォーマンス </p> </td>
   <td colname="col2"> <p>1 Mbps 以上のリピーターサーバーまたは <span class="keyword"> Data Workbench サーバー </span> へのネットワーク接続。 <span class="wintitle"> 通 </span> 常、センサーの消費帯域幅は 1 Mbps よりも大幅に少なくなります。Adobeコンサルタントは、通常の基準で必要な実際の帯域幅を見積もる際に役立ちます。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ネットワークポートとファイアウォール </p> </td>
   <td colname="col2"> <p> <span class="wintitle"> Sensor </span> は、HTTPS( 通常はポート 443 <span class="keyword">  </span> ですが、設定は可能です ) または HTTP（通常はポート 80 ですが、設定は可能です）を使用して、Data Workbench サーバーに接続します。 </p> <p><span class="wintitle"> Sensor </span> と対象の <span class="keyword"> Data Workbench サーバー </span> またはリピーターサーバーとの間にあるファイアウォール上の適切なポートは、 <span class="wintitle"> Sensor </span> をホストするコンピューターと <span class="keyword"> Data Workbench サーバー </span> の間でのみ開く必要があります。 <span class="wintitle"></span><span class="wintitle"> センサ </span> ーは、Data Workbench サーバーまたはリピーターサーバーに対し <span class="keyword"> て、一方向の HTTPS または HTTP </span> 接続を行います。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ネットワーク管理システム </p> </td>
   <td colname="col2"> <p>既存のネットワーク管理システムは、基になるコンピュータハードウェア（ディスク領域、ネットワークサービスなど）とネットワーク接続、および Windows のイベントログや UNIX の syslog の状態を監視する必要があります。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>サーバー時刻の同期 </p> </td>
   <td colname="col2"> <p><span class="wintitle"> センサー </span> をホストするすべてのコンピューターで、コンピューターシステムの時間が継続的に同期されていることを確認します。 <span class="wintitle"> Sensor </span> で監視される Web サーバーアプリケーションとコンピューターは、システム時刻を同期して、それらから収集されたイベントデータを正確に表示する必要があります。 NTP やその他の時刻同期機能と継続的にシステム時刻を同期する手順については、オペレーティングシステムのマニュアルを参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>DNS 名の使用 </p> </td>
   <td colname="col2"> <p>Adobeでは、<span class="wintitle"> センサー </span> で（IP アドレスではなく）DNS 名を使用して、<span class="keyword"> Data Workbench サーバー </span> またはリピーターサーバーのネットワークアドレスを解決することをお勧めします。 <span class="wintitle"> センサー </span> が DNS 名を使用する場合は、ホスト Web サーバーの DNS またはローカルホストファイルを設定して、<span class="keyword"> Data Workbench サーバー </span> またはリピーターサーバーの名前を解決する必要があります。 </p> </td>
  </tr>
 </tbody>
</table>

### サポートサーバソフトウェア {#section-d6071706539f49d9a861d87b98e6f382}

次の表に、[!DNL Sensor] がサポートする最も一般的な組み合わせを示します。

<table id="table_99EA23BBC1A148B49643F4B5E4341C08">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Web サーバーソフトウェア </th>
   <th colname="col2" class="entry"> オペレーティングシステム </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Apache サーバー/IBM HTTP Server 2.2 </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003 以降RedHat Enterprise Linux 6.x 以降Sun Solaris 8.x 以降IBM AIX 5.1x 以降。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Apache サーバー 2.4 </p> </td>
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x 以降 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Microsoft IIS </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003 以降 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Java アプリケーションサーバー (Tomcat、JBoss、iPlanet、Weblogic) </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003 以降RedHat Enterprise Linux 6.x 以降Sun Solaris 8.x 以降IBM AIX 5.1x 以降。 </p> </td>
  </tr>
 </tbody>
</table>

その他のサーバーとオペレーティングシステムの組み合わせについては、可用性に関するAdobeを参照してください。 [!DNL Sensor] のすべての機能が、Web/アプリケーションサーバーとオペレーティングシステムの組み合わせで利用できるわけではありません。 特定の [!DNL Sensor] リリースの詳細については、Adobeサポートにお問い合わせください。

## レポートサーバーの要件{#report-server-requirements}

Data Workbench レポートサーバーは、スケジュールされたレポートの出力を可能にするコンポーネントです。 出力されるレポートは、.PNG 画像形式または.XLS スプレッドシート形式でファイルシステムに配置するか、電子メール形式で配置できます。 ハードウェア要件は、[Data Workbenchクライアント ](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=ja) と同じです。

[!DNL report server] には次の要件があります。

* データ（ネットワーク共有、またはローカルドライブ）の出力用のファイルシステムへのアクセス
* 設定済みの SMTP サーバーへのアクセス
* Microsoft Excel 2003 以降が [!DNL report] サーバーにインストールされている。 詳しくは、[Office のサーバー側自動化に関する考慮事項 ](https://support.microsoft.com/kb/257757) を参照してください。

## ネットワーク管理{#network-management}

Adobeは、既存のネットワーク管理システムが、Data Workbench・プラットフォームが依存するハードウェアとネットワークを監視することを推奨します。

また、Adobeでは、エラーの発生時に書き込まれる FSU および DPU の Windows イベントログを監視することをお勧めします。

>[!NOTE]
>
>ログファイルをホストするネットワーク・ストレージ・システムは、DPU あたり少なくとも 10 MB の帯域幅を提供する必要があります。

## データの可用性{#data-availability}

サーバー DPU でデータを処理し、新しいデータセットや更新されたデータセットに再処理するのは、通常で必須の方法です。

この問題は、設定の変更、データソースの変更、ハードウェアの変更、不適切な設定、ハードウェアの障害、ソフトウェアの障害、電源の障害などが原因で発生する場合があります。 このような処理や再処理がおこなわれると、すべてのデータセットとシステムデータを DPU および FSU コンポーネントから直ちに利用できる必要があります。 この要件に準拠しないと、システムのダウンタイムが大幅に長くなり、不要になる可能性があります。

## DPU と FSU のネットワークに関する問題{#dpu-and-fsu-network-issues}

DPU および FSU ネットワークを使用する際に注意すべき考慮事項。

* ネットワーク・ログ・ファイルの配布の場合、ログ・ファイルをホストするネットワーク・ストレージ・システムは、持続的な帯域幅の DPU あたり少なくとも 10 MB を提供する必要があります。
* DPU、FSU、およびData Workbenchは、ポート 80 または 443( デフォルトでは、ポートを別の方法で設定することもできます )。
* Data Workbench[!DNL Sensor(s)] は、サーバに（一方向に）接続できる必要があります。
* DPU が SMTP 経由でアラートメッセージを送信できるようにするには、設定済みの SMTP サーバーと通信できる必要があります。
* Adobeでは、IP アドレスが変更された場合に再構成を避けるために、FSU および DPU に FSU01.CLIENT.COM などのネットワーク名を付けることをお勧めします。
