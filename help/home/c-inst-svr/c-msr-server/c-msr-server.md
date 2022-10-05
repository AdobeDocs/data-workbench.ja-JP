---
description: Data Workbench( 以前の [!DNL Insight]) サーバーコンポーネントを使用します。
title: サーバーの必要システム構成
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# サーバーの必要システム構成{#server-system-requirements}

{{eol}}

システムの計画と実装を行う前に、Data Workbench・サーバ・コンポーネントの最小要件と推奨事項を特定します。

## DPU 要件{#dpu-requirements}

サーバデータ処理部 (DPU) は、Data Workbenchの主要なデータ処理部分である。 Data Workbenchからのネットワーク接続をリッスンし、ファイルサーバーユニット (FSU) から生のソースデータを読み取り、大量の計算リソースとストレージリソースを使用します。

### ライセンス容量 {#section-71850e13783443798b3df9eb22cc63dc}

詳しくは、 *Adobe [!DNL Data Workbench (Insight)] サービス契約* ライセンス容量情報を参照してください。

>[!NOTE]
>
>の場合 *MS System Center エンドポイント保護* Windows 2012 Server では、次の実行ファイルを ***除外されたプロセス：*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>


### DPU システムのRecommendationsと要件 {#section-ae30555959bf4a309c76d0fd597b5162}

Adobeは、ビジネスニーズに合ったData Workbenchデザインに関するレコメンデーションを提供します。 ただし、DPU ソフトウェアの最適化された性質により、OS/ハードウェアプラットフォームに固有の要件が置かれるので、オペレーティングシステム (OS) とハードウェアを選択する場合は、次のガイドラインが役立ちます。

1 つのデータセットが 1 つの DPU の容量または速度によって制限されている場合は、それらをクラスター化できます。 例えば、DPU ソフトウェアのライセンスを持つ 3 つのコピーを一緒に使用して、より迅速に大きなデータセットを実行したとします。 データがマシン間で均等に分割されると、データセットのライセンス済みの容量に 3 が乗じます。 また、1 行あたりの処理速度は、1 つの DPU の 3 倍の速さになります。

DPU への投資で最高のパフォーマンスを実現するために、Adobeでは次の表に示す次の高性能コンポーネントを推奨しています。

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
   <td colname="col3"> インテルまたは AMD の最新世代 4 コア+プロセッサーをお勧めします。 最適なパフォーマンスを実現するには、8 コアを使用します。速度とコストの間のトレードオフの場合は、4 コアを推奨します。 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>8 GB </p> </td>
   <td colname="col3"> <p>12 GB </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>作業用データストレージ </p> </td>
   <td colname="col2"> <p>1 TB 以上の論理温度ストレージ。 </p> <p>ディスクサブシステムへの低レイテンシアクセス </p> </td>
   <td colname="col3"> <p>一時ストレージAdobeの場合は、次のいずれかを推奨します。 </p>
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283">
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4～8) * （750GB 以上） SATA HDD （3.5 インチスピンドル） </li>
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6～10) * （300GB 以上） SATA HDD （2.5 インチスピンドル） </li>
    </ul> <p>これらは JBOD アレイで構成する必要があります。 また、総ディスク容量が 2 TB を超える場合は、2 ディスクの RAID1 ボリュームのアレイを使用できます。 たとえば、6 台のディスクを 3*（2*750GB RAID 1 ペア）として構成します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>システムデータストレージ </p> </td>
   <td colname="col2"> <p>さらに、Adobeには、OS、DPU ソフトウェア、その他のシステムソフトウェアに対して、わずかなサイズ (20GB) の高可用性ストレージが必要です。 </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ハードウェアのクラスタリング </p> </td>
   <td colname="col2"> <p>レコメンデーションを参照してください。 </p> </td>
   <td colname="col3"> <p>同種のサーバセットを使用します。 DPU クラスターでは、最も遅いサーバーによってデータセット全体のパフォーマンスが低下します。 </p> </td>
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

* DPU は、高パフォーマンスのディスクシステムを異常に要求しているため、不適切なディスクサブシステムを設定すると、パフォーマンスのボトルネックを引き起こす可能性があります。
* DPU ソフトウェアは、一連の JBOD ディスクに対して、独自のパフォーマンス指向のデータストライピングを実行します。 RAID を使用して速度を上げないでください。
* Adobeでは、DPU に 400 MB/秒以上の MB/秒の総合的な持続帯域幅をディスクに割り当てることを推奨します。
* 平均読み取りサイズは非常に大きい (2 MB+)。 このため、15,000 または 10,000 SAS ディスクは、多くの場合、SATA ディスクよりも少し良い（または悪い）パフォーマンスを発揮し、大幅なコストと容量のペナルティを受けます。
* SAN アーキテクチャの使用は避けます。 経験から、SAN を必要なレベルで実行するコストは、通常は極端です。
* ローカル・ディスク・サブシステムはスクラッチ領域として使用されます。HDD 障害からデータが永久に失われることはないので、コストのかかる、低速で高可用性のシステムを避けることを検討してください。

### 速度に関する考慮事項 {#section-01330be232894e08a526d8d82b7c4eb2}

Adobeは、設定されたData Workbenchでデータが処理される速度に関する保証または表現を提供できません。これは、様々な要因がデータ処理速度に影響を与えるためです。以下に例を示しますが、これらに限りません。

* データの行数
* データのディメンション（列）の数
* カスタム処理手順の数と複雑さ
* クラスタリングの使用
* ハードウェアの速度

## ファイルサーバーのユニット要件{#file-server-unit-requirements}

サーバの FSU(File Serving Unit) は、Data Workbenchの主要なデータ・ストレージおよび管理コンポーネントです。 FSU は、DPU に対する生のソースデータのファイルサーバとして機能し、必要に応じて、DPU のクラスタリングを調整します。 各 FSU は、最大 5 個の DPU にソースデータを提供するライセンスを受けます。

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E">
 <thead>
  <tr>
   <th colname="col1" class="entry"> FSU コンポーネント </th>
   <th colname="col2" class="entry"> 推奨事項 </th>
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
   <td colname="col1"> <p>ディスクシステム </p> <p>FSU には、大量のデータに対して高可用性で冗長なストレージが必要です。 Adobeがお客様と連携して、お客様の正確な要件を決定します。 </p> </td>
   <td colname="col1"> <p>Adobeの推奨事項： </p>
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539">
     <li id="li_F98750D509D640C68885D53FC691ED43">（12 台以上） * （750GB 以上） RAID 5/6 構成の SATA HDD </li>
     <li id="li_3F84F63F9541476987015C27FDE8251B">100 MB/秒以上の持続的な帯域幅をサポートする高パフォーマンス SAN 接続。 </li>
    </ul> <p>FSU が生のソース・データを保持しているので、損失は回復不可能となり、Adobeはこのデータを定期的にバックアップすることを示しています。 </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ネットワークパフォーマンス </p> </td>
   <td colname="col2"> <p>Adobeでは、FSU と DPU 間のスイッチギガビットイーサネット接続が必要です。 </p> </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

## センサーの要件{#sensor-requirements}

Data Workbenchセンサーは、Web、アプリケーション、およびデータ収集サーバーからイベントデータを収集し、任意のサーバーに送信します。 [!DNL Sensor’s] インストルメンテーションは、インターネットチャネルで発生するイベントを一貫して正確に測定することを保証します。 [!DNL Sensor] は、Web サーバーソフトウェアとオペレーティングシステムの多くの組み合わせをサポートしています。

### センサーシステムRecommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

次の表に、 [!DNL Sensor]:

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
   <td colname="col2"> <p>最小 512 MB。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>32 MB の RAM を使用可能にする必要があります <span class="wintitle"> センサー </span> HTTP またはそのホストである他のサーバーコンピューター上。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ネットワークパフォーマンス </p> </td>
   <td colname="col2"> <p>1 Mbps 以上のリピーターサーバーへのネットワーク接続 <span class="keyword"> data workbench サーバー </span>. <span class="wintitle"> センサー </span> 通常、1 Mbps よりもはるかに少ない帯域幅を消費します。 Adobeコンサルタントが、日常的に必要となる実際の帯域幅量を見積もる際に役立ちます。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ネットワークポートとファイアウォール </p> </td>
   <td colname="col2"> <p> <span class="wintitle"> センサー </span> 接続先： <span class="keyword"> data workbench サーバー </span> HTTPS( 通常はポート 443（設定可能）または HTTP( 通常はポート 80（設定可能）) を使用。 </p> <p>ファイアウォール上の、 <span class="wintitle"> センサー </span> とターゲット <span class="keyword"> data workbench サーバー </span> またはリピータサーバは、それぞれの <span class="wintitle"> センサー </span> ホスティングコンピューターと <span class="keyword"> data workbench サーバー </span> またはリピーターサーバーを使用してから開始する <span class="wintitle"> センサー </span> インストールプロセス。 <span class="wintitle"> センサー </span> は、 <span class="keyword"> data workbench サーバー </span> またはリピータサーバ。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>ネットワーク管理システム </p> </td>
   <td colname="col2"> <p>既存のネットワーク管理システムは、基になるコンピュータハードウェア（ディスク容量、ネットワークサービスなど）とネットワーク接続、および Windows イベントログや UNIX syslog の状態を監視する必要があります。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>サーバー時刻の同期 </p> </td>
   <td colname="col2"> <p>コンピュータシステムの時間が、 <span class="wintitle"> センサー </span>. 監視対象の Web サーバーアプリケーションとコンピュータ <span class="wintitle"> センサー </span> から収集されたイベントデータが正確になるためには、システム時間を同期している必要があります。 NTP やその他の時刻同期機能と継続的にシステム時刻を同期する手順については、オペレーティングシステムのマニュアルを参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>DNS 名の使用状況 </p> </td>
   <td colname="col2"> <p>Adobeは、 <span class="wintitle"> センサー </span> （IP アドレスの代わりに）DNS 名を使用して、 <span class="keyword"> data workbench サーバー </span> またはリピータサーバ。 When a <span class="wintitle"> センサー </span> が DNS 名を使用する場合、ホスト Web サーバーの DNS またはローカルホストファイルを構成して、 <span class="keyword"> data workbench サーバー </span> またはリピータサーバ。 </p> </td>
  </tr>
 </tbody>
</table>

### サポートサーバソフトウェア {#section-d6071706539f49d9a861d87b98e6f382}

次の表に、 [!DNL Sensor] サポート：

<table id="table_99EA23BBC1A148B49643F4B5E4341C08">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Web サーバソフトウェア </th>
   <th colname="col2" class="entry"> オペレーティングシステム </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Apache サーバー/IBM HTTP Server 2.2 </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003 以降RedHat Enterprise Linux 6.x 以降Sun Solaris 8.x 以降IBM AIX 5.1x 以降。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Apache Server 2.4 </p> </td>
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

その他のサーバーとオペレーティングシステムの組み合わせについては、可用性に関するAdobeを参照してください。 のすべての機能とは異なる [!DNL Sensor] は、web/アプリケーションサーバーとオペレーティングシステムのすべての組み合わせで使用できます。 詳しくは、 [!DNL Sensor] のリリースについては、Adobeサポートにお問い合わせください。

## レポートサーバーの要件{#report-server-requirements}

Data Workbench レポートサーバーは、予定レポートの出力を可能にするコンポーネントです。 出力されるレポートは、ファイルシステムに配置された.PNG 画像または.XLS スプレッドシートの形式で、または電子メールで作成できます。 ハードウェア要件は、 [Data Workbenchクライアント](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=ja).

次の要件が存在します： [!DNL report server]:

* データの出力用のファイルシステム（ネットワーク共有、またはローカルドライブ）にアクセス。
* 設定済みの SMTP サーバーにアクセスします。
* Microsoft Excel 2003 以降がにインストールされている [!DNL report] サーバー。 詳しくは、 [Office のサーバー側自動化に関する考慮事項](https://support.microsoft.com/kb/257757) を参照してください。

## ネットワーク管理{#network-management}

Adobeは、既存のネットワーク管理システムが、Data Workbenchプラットフォームが依存するハードウェアとネットワークを監視することを推奨します。

また、Adobeでは、エラーが発生した場合に書き込まれる FSU および DPU の Windows イベントログを監視することをお勧めします。

>[!NOTE]
>
>ログファイルをホストするネットワークストレージシステムは、DPU あたり 10 MB 以上の持続的な帯域幅を提供する必要があります。

## データの可用性{#data-availability}

サーバー DPU でデータを処理し、新しいデータセットや更新されたデータセットに再処理するのは、通常で必要な方法です。

この問題は、構成の変更、データソースの変更、ハードウェアの変更、不適切な構成、ハードウェアの障害、ソフトウェアの障害、電源の障害などが原因で発生する場合があります。 このような処理または再処理が行われる場合、すべてのデータセットとシステムデータを DPU および FSU コンポーネントから直ちに利用できる必要があります。 この要件に準拠しないと、システムのダウンタイムが大幅に長くなり、不要になる場合があります。

## DPU と FSU のネットワークに関する問題{#dpu-and-fsu-network-issues}

DPU および FSU ネットワークを使用する際の考慮事項。

* ネットワーク・ログ・ファイルを配布する場合、ログ・ファイルをホストするネットワーク・ストレージ・システムは、DPU あたり 10 MB 以上の持続的な帯域幅を提供する必要があります。
* DPU、FSU、およびData Workbenchは、ポート 80 または 443( デフォルトでは、ポートを別の方法で設定することもできます )。
* Data Workbench [!DNL Sensor(s)] は、（一方向に）サーバーに接続できる必要があります。
* DPU が SMTP 経由でアラートメッセージを送信できるようにするには、設定済みの SMTP サーバーと通信できる必要があります。
* Adobeでは、IP アドレスが変更された場合に再構成を避けるために、FSU と DPU に FSU01.CLIENT.COM などのネットワーク名を付けることをお勧めします。
