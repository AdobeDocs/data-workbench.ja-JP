---
description: システムの計画と実装を行う前に、Data Workbench（旧称[!DNL Insight]）サーバーコンポーネントの最小要件と推奨事項を特定します。
title: サーバの必要システム構成
uuid: c4487c76-03b9-4755-893b-555d451b1e69
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# サーバの必要システム構成{#server-system-requirements}

システムの計画と実装を行う前に、Data Workbenchサーバーコンポーネントの最小要件と推奨事項を特定します。

## DPU要件{#dpu-requirements}

サーバーのデータ処理ユニット(DPU)は、Data Workbenchのメインのデータ処理コンポーネントです。 Data Workbenchのネットワーク接続をリッスンし、ファイルサーバーユニット(FSU)から生のソースデータを読み取り、大量の計算リソースとストレージリソースを使用します。

### ライセンス容量 {#section-71850e13783443798b3df9eb22cc63dc}

ライセンス容量に関する情報については、 *Adobe Service Agreement[!DNL Data Workbench (Insight)]のServices Description* （サービスの説明）を参照してください。

>[!NOTE]
>
>Windows 2012 Serverで *MS System Center Endpoint Protectionを使用する場合* 、次の実行可能ファイルを除外プロセスに追加する必要 ***があります。*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>



### DPUの推奨システム構成と要件 {#section-ae30555959bf4a309c76d0fd597b5162}

ビジネスニーズに合ったData Workbenchのデザインに関する推奨事項を示します。 ただし、DPUソフトウェアの最適化された特性により、OS/ハードウェアプラットフォームに特定の要件が配置されるので、オペレーティングシステム(OS)とハードウェアを選択する場合は、次のガイドラインが役立ちます。

単一のデータセットが単一のDPUの容量や速度によって制限される場合は、それらをクラスタリングできます。 例えば、DPUソフトウェアのライセンスを3つ持っていて、これらを一緒に使用して、より大きなデータセットをより迅速に実行しているとします。 データがマシン間で均等に分割されると、データセットのライセンス容量に3が掛かります。 また、1行あたりの処理速度は、1つのDPUの3倍高速になります。

DPU投資で最高のパフォーマンスを得るために、次の表に示す高パフォーマンスのコンポーネントをアドビで推奨します。

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
   <td colname="col2"> <p>recommendationsを参照してください。 </p> </td> 
   <td colname="col3"> IntelまたはAMDの最新世代4コア+プロセッサーを推奨します。 最適なパフォーマンスを実現するために、8コア速度とコストのトレードオフには、4コアを推奨します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>作業データストレージ </p> </td> 
   <td colname="col2"> <p>1 TB以上の論理一時ストレージ。 </p> <p>ディスクサブシステムへの低遅延アクセス </p> </td> 
   <td colname="col3"> <p>一時的なストレージの場合は、次のいずれかを推奨します。 </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4～8) * （750 GB以上） SATA HDD （3.5インチスピンドル） </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 ～ 10) * （300 GB以上） SATA HDD （2.5インチスピンドル） </li> 
    </ul> <p>これらは、JBODアレイで構成する必要があります。 また、総ディスク容量が2 TBを超える場合は、2ディスクのRAID1ボリュームのアレイを使用できます。 たとえば、6台のディスクを3*（2*750 GB RAID 1ペア）として構成します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>システムデータストレージ </p> </td> 
   <td colname="col2"> <p>さらに、OS、DPUソフトウェア、その他のシステムソフトウェアには、わずかなサイズ(20 GB)の高可用性ストレージが必要です。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>クラスタリングハードウェア </p> </td> 
   <td colname="col2"> <p>recommendationsを参照してください。 </p> </td> 
   <td colname="col3"> <p>同種のサーバを使用します。 DPUクラスターでは、最も低速なサーバーにより、データセット全体のパフォーマンスが低下します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ネットワークパフォーマンスのクラスタリング </td> 
   <td colname="col2"> スイッチドギガビットイーサネット接続以上。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### 代替ディスク・サブシステム {#section-6f984eabe8074759aa9deaf17e3a68b7}

一時記憶域の代替ディスクサブシステムを検討する場合は、次の要因とガイドラインを考慮してください。

* DPUは、高パフォーマンスのディスクシステムを異常に要求しているので、不適切なディスクサブシステムを設定すると、パフォーマンスのボトルネックを引き起こす可能性があります。
* DPUソフトウェアは、JBODディスクのセット全体で、独自のパフォーマンス指向のデータストライピングを行います。 RAIDを使用して速度を上げないでください。
* DPUのディスクに対する総帯域幅は、400 MB/秒以上にすることをお勧めします。
* 平均読み取りサイズは非常に大きい（2 MB以上）。 このため、15,000または10,000 SASディスクは、多くの場合、コストと容量の大幅な削減により、SATAディスクよりも少し優れた（または劣った）パフォーマンスを発揮します。
* SANアーキテクチャの使用は避けてください。 経験から見ると、SANを必要なレベルで実行するコストは、通常は極端です。
* ローカルディスクサブシステムはスクラッチ領域として使用され、HDD障害によってデータが永久的に失われることはないので、コストがかかり、低速で高可用性を実現するシステムの使用を避けることを検討します。

### 速度に関する考慮事項 {#section-01330be232894e08a526d8d82b7c4eb2}

アドビは、設定済みのData Workbenchでデータが処理される速度に関する保証や表現を提供できません。これは、次のような様々な要因がデータ処理速度に影響を与えるためです。

* データの行数
* データのディメンション（列）数
* カスタム処理手順の数と複雑さ
* クラスタリングの使用
* ハードウェアの速度

## ファイルサーバーユニットの要件{#file-server-unit-requirements}

サーバーのファイルサービングユニット(FSU)は、Data Workbenchの主要なデータの格納および管理コンポーネントです。 FSUは、DPUに対する生のソースデータのファイルサーバーとして機能し、必要に応じて、DPUのクラスタリングを調整します。 各FSUは、最大5つのDPUにソースデータを提供するライセンスを受けています。

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> FSUコンポーネント </th> 
   <th colname="col2" class="entry"> Recommendations </th> 
   <th colname="col3" class="entry"> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>オペレーティングシステム、CPU、RAM </p> </td> 
   <td colname="col2"> <p>これらの要件はDPUの要件と同じです。 ただし、FSUの場合は、推奨事項に従うのではなく、最小要件を使用することをお勧めします。 </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディスクシステム </p> <p>FSUには、大量のデータを処理するために、可用性の高い冗長ストレージが必要です。 アドビはお客様と協力して、お客様の要件を正確に決定します。 </p> </td> 
   <td colname="col1"> <p>推奨事項： </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">（12台以上）* RAID 5/6構成の750 GB以上のSATA HDD。 </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">100 MB/秒以上の持続的な帯域幅をサポートする、高パフォーマンスのSAN接続。 </li> 
    </ul> <p>FSUが生のソースデータを保持するので、損失を回復できないので、アドビはこのデータを定期的にバックアップすることを推奨します。 </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネットワークパフォーマンス </p> </td> 
   <td colname="col2"> <p>アドビでは、FSUとDPUの間のスイッチドギガビットイーサネット接続が必要です。 </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## センサー要件{#sensor-requirements}

Data Workbench Sensorは、任意のサーバーに送信されるWeb、アプリケーションおよびデータ収集サーバーからイベントデータを収集します。 [!DNL Sensor’s] インストゥルメンテーションは、インターネットチャネルで発生するイベントを常に正確に測定します。 [!DNL Sensor] は、Webサーバーソフトウェアとオペレーティングシステムの多くの組み合わせをサポートしています。

### センサーシステムの推奨事項 {#section-0a981c3a47b644c1a1a56974ba033b9c}

次の表に、のシステム推奨事項を示しま [!DNL Sensor]す。

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
   <td colname="col2"> <p>512 MB以上。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 MBのRAMは、HTTPまたはそのホストの他のサ <span class="wintitle"> ーバ </span> ーコンピューター上のSensorで使用できる必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネットワークパフォーマンス </p> </td> 
   <td colname="col2"> <p>リピータサーバーまたはData Workbenchサーバーへの1 Mbps以上のネットワ <span class="keyword"> ーク接続で </span>す。 <span class="wintitle"> センサ </span> ーの消費帯域幅は通常、1 Mbpsよりもはるかに少なくなります。 アドビのコンサルタントが、定期的に必要となる実際の帯域幅の量を見積もるお手伝いをします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネットワークポートとファイアウォール </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> Sensorは、HTTPS(設定 </span><span class="keyword"></span> は可能ですが、通常はポート443)またはHTTP（通常はポート80）を使用して、Data Workbenchサーバーに接続します（設定は可能です）。 </p> <p>Sensorと対象のData Workbenchサーバー <span class="wintitle"> Repeaterサーバーの間にある適切なポートは、各Sensor </span> computerとWorkbench <span class="keyword"> ServerまたはSensor </span> Sensor <span class="wintitle"></span><span class="keyword"></span><span class="wintitle"></span> Sensor Storeの前にあるRepeaterの間でのみ開く必要があります。 <span class="wintitle"> Sensorは、 </span> Data Workbenchサーバーまたはリピーターサーバーへの一方向のHTTPS <span class="keyword"> またはHTTP接 </span> 続を行います。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネットワーク管理システム </p> </td> 
   <td colname="col2"> <p>既存のネットワーク管理システムは、基盤となるコンピュータハードウェア（ディスク容量、ネットワークサービスなど）とネットワーク接続、およびWindowsイベントログやUNIX syslogの状態を監視する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバー時刻の同期 </p> </td> 
   <td colname="col2"> <p>コンピューターシステムの時間が、センサーをホストするすべてのコンピューター間で継続的に同期されていることを確 <span class="wintitle"> 認しま </span>す。 Sensorで監視されるWebサーバーアプリケーションとコンピューターから収集さ <span class="wintitle"> れたイベ </span> ントデータを正確に表示するには、システム時間が同期されている必要があります。 NTPなどの時刻同期機能を使用して、システム時刻を継続的に同期する手順については、オペレーティングシステムのドキュメントを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DNS名の使用 </p> </td> 
   <td colname="col2"> <p>アドビでは、 <span class="wintitle"> Sensor </span> で（IPアドレスではなく）DNS名を使用して、Data Workbenchサーバーまたはリピーターサーバーのネットワークアドレスを解決す <span class="keyword"> ることを </span> お勧めします。 SensorがDNS名を <span class="wintitle"> 使 </span> 用する場合、ホストWebサーバーのDNSまたはローカルホストファイルを設定して、Data Workbenchサーバーまたはリピーターサーバーの名前を解決する必要 <span class="keyword"></span> があります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### サポートサーバソフトウェア {#section-d6071706539f49d9a861d87b98e6f382}

次の表に、サポートされる最も一般的な組み合わせを示 [!DNL Sensor] します。

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Webサーバーソフトウェア </th> 
   <th colname="col2" class="entry"> オペレーティングシステム </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Apache Server / IBM HTTP Server 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003以降RedHat Enterprise Linux 6.x以降Sun Solaris 8.x以降IBM AIX 5.1x以降。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apache Server 2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x以降 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003以降 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Java Application Servers(Tomcat、JBoss、iPlanet、Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003以降RedHat Enterprise Linux 6.x以降Sun Solaris 8.x以降IBM AIX 5.1x以降。 </p> </td> 
  </tr> 
 </tbody> 
</table>

その他のサーバーとオペレーティングシステムの組み合わせについては、アドビにお問い合わせください。 Web/アプリケーションサーバーと [!DNL Sensor] オペレーティングシステムの組み合わせによっては、のすべての機能が使用できるわけではありません。 特定のリリースについて詳しくは、 [!DNL Sensor] アドビサポートにお問い合わせください。

## レポートサーバーの要件{#report-server-requirements}

Data Workbenchレポートサーバーは、スケジュールされたレポートの出力を可能にするコンポーネントです。 出力されるレポートは、.PNG画像または.XLSスプレッドシートの形式でファイルシステムに配置するか、電子メールで送信できます。 ハードウェア要件は、 [Data Workbenchクライアントと同じです](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html)。

には、次の要件がありま [!DNL report server]す。

* データ（ネットワーク共有、ローカルドライブ）の出力用のファイルシステムへのアクセス。
* 設定済みのSMTPサーバーへのアクセス。
* Microsoft Excel 2003以降がサーバーにインストールされて [!DNL report] います。 詳しく [は、「Officeのサーバー側自動化に関する考慮事項](http://support.microsoft.com/kb/257757) 」を参照してください。

## ネットワーク管理{#network-management}

既存のネットワーク管理システムで、Data Workbenchプラットフォームが依存するハードウェアとネットワークを監視することをお勧めします。

さらに、FSUおよびDPUのWindowsイベントログを監視し、エラーが発生した場合に書き込まれるようにすることをお勧めします。

>[!NOTE]
>
>ログファイルをホストするネットワークストレージシステムでは、DPUあたり10 MB以上の帯域幅を確保する必要があります。

## データの可用性{#data-availability}

サーバーのDPUでデータを処理し、新しいデータセットや更新されたデータセットに再処理するのは、通常どおりで、必要な方法です。

これは、構成の変更、データソースの変更、ハードウェアの変更、不適切な構成、ハードウェアの障害、ソフトウェアの障害、電源の障害などが原因で発生する場合があります。 このような処理または再処理が行われると、すべてのデータセットおよびシステムデータをDPUおよびFSUコンポーネントで即座に使用できるようにする必要があります。 この要件を満たさないと、システムのダウンタイムが大幅に長くなり、不要になる可能性があります。

## DPUとFSUのネットワークに関する問題{#dpu-and-fsu-network-issues}

DPUおよびFSUネットワークを使用する場合は、注意が必要です。

* ネットワークログファイルを配信する場合、ログファイルをホストするネットワークストレージシステムでは、DPUあたり10 MB以上の帯域幅を確保する必要があります。
* DPU、FSUおよびData Workbenchは、ポート80または443(デフォルトでは、ポートを別の方法で設定することもできます)。
* Data Workbenchがサ [!DNL Sensor(s)] ーバーに（一方向に）接続できる必要があります。
* DPUがSMTP経由で警告メッセージを送信できるようにするには、設定済みのSMTPサーバーに接続できる必要があります。
* アドビでは、IPアドレスが変更された場合に再構成を避けるために、FSUやDPUにFSU01.CLIENT.COMなどのネットワーク名を付けることをお勧めします。