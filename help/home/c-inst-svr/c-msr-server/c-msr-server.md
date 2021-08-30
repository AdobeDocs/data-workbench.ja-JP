---
description: システムの計画と実装を行う前に、Data Workbench（旧称 [!DNL Insight]）サーバーコンポーネントの最小要件と推奨事項を特定してください。
title: サーバーの必要システム構成
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# サーバーの必要システム構成{#server-system-requirements}

システムの計画と実装を行う前に、Data Workbench・サーバーのコンポーネントに関する最小要件と推奨事項を特定します。

## DPUの要件{#dpu-requirements}

サーバData Processing Unit（DPU；データ処理ユニット）は、Data Workbenchの主要なデータ処理コンポーネントです。 Data Workbenchからのネットワーク接続をリッスンし、ファイルサーバーユニット(FSU)から生のソースデータを読み取り、大量の計算リソースとストレージリソースを使用します。

### ライセンス容量 {#section-71850e13783443798b3df9eb22cc63dc}

ライセンス容量の情報については、*Adobe[!DNL Data Workbench (Insight)]サービス契約*&#x200B;のサービスの説明を参照してください。

>[!NOTE]
>
>Windows 2012 Serverの&#x200B;*MS System Center Endpoint Protection*&#x200B;の場合、これらの実行可能ファイルを&#x200B;***Excluded Processes:*** >に追加する必要があります。
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]

>


### DPUシステムのRecommendationsと要件 {#section-ae30555959bf4a309c76d0fd597b5162}

Adobeは、ビジネスニーズを満たすData Workbenchデザインに関する推奨事項を提供します。 ただし、DPUソフトウェアの最適化された特性により、OS/ハードウェアプラットフォームに固有の要件が課されるので、オペレーティングシステム(OS)とハードウェアを選択する際には、次のガイドラインが役立ちます。

1つのデータセットが1つのDPUの容量または速度によって制限されている場合は、それらをクラスター化できます。 例えば、DPUソフトウェアのライセンスコピーが3つあり、これらを一緒に使用してより迅速に大きなデータセットを実行するとします。 データがマシン間で均等に分割されると、データセットのライセンス容量に3を掛けます。 また、1行あたりの処理速度は、1つのDPUの3倍の速さになります。

DPUへの投資で最高のパフォーマンスを実現するために、Adobeでは、次の表に示す高パフォーマンスのコンポーネントを推奨しています。

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
   <td colname="col3"> インテルまたはAMDの最新世代4コア+プロセッサーを推奨します。 最適なパフォーマンスを実現するには、8コア速度とコストのトレードオフの場合は、4コアを推奨します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>作業用データストレージ </p> </td> 
   <td colname="col2"> <p>1 TB以上の論理一時ストレージ。 </p> <p>ディスク・サブ・システムへの低レイテンシ・アクセス </p> </td> 
   <td colname="col3"> <p>一時的なストレージAdobeの場合は、次のいずれかを推奨します。 </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4～8) * （750 GB以上） SATA HDD （3.5インチスピンドル） </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6～10) * （300 GB以上） SATA HDD （2.5インチスピンドル） </li> 
    </ul> <p>これらはJBODアレイで設定する必要があります。 また、総ディスク容量が2 TBを超える場合は、2ディスクRAID1ボリュームのアレイを使用できます。 たとえば、6台のディスクを3*（2*750 GB RAID 1ペア）として構成します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>システムデータストレージ </p> </td> 
   <td colname="col2"> <p>さらに、Adobeには、OS、DPUソフトウェア、その他のシステムソフトウェア用に、適度なサイズ(20 GB)の高可用性ストレージが必要です。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>クラスタリングハードウェア </p> </td> 
   <td colname="col2"> <p>レコメンデーションを参照してください。 </p> </td> 
   <td colname="col3"> <p>同種のサーバセットを使用する。 DPUクラスターでは、最も遅いサーバーによって、データセット全体のパフォーマンスが低下します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ネットワークパフォーマンスのクラスタリング </td> 
   <td colname="col2"> スイッチギガビットイーサネット接続以上。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### 代替ディスクサブシステム {#section-6f984eabe8074759aa9deaf17e3a68b7}

一時ストレージの代替ディスクサブシステムを検討する際は、次の要因とガイドラインを考慮してください。

* DPUは、高パフォーマンスのディスクシステムを異常に要求しているので、不十分なディスクサブシステムを設定すると、パフォーマンスのボトルネックが生じる可能性があります。
* DPUソフトウェアは、一連のJBODディスクに対して、独自のパフォーマンス指向のデータストライピングを実行します。 RAIDを使用して速度を上げないでください。
* Adobeでは、DPUに400 MB/秒以上の帯域幅がディスクに対して集約されていることを推奨します。
* 平均読み取りサイズは非常に大きい（2 MB以上）。 このため、15,000または10,000 SASディスクは、多くの場合、SATAディスクよりも少し優れた（または劣った）パフォーマンスを発揮しますが、コストと容量に大きなペナルティがかかります。
* SANアーキテクチャの使用は避けます。 経験から、SANを必要なレベルで実行するコストは、通常は極端です。
* ローカル・ディスク・サブシステムはスクラッチ領域として使用され、HDD障害によってデータが永久的に失われることはないため、コストのかかる、低速で高可用性のシステムを避けることを検討してください。

### 速度に関する考慮事項 {#section-01330be232894e08a526d8d82b7c4eb2}

Adobeは、設定されたData Workbenchによってデータが処理される速度に関する保証または表現を提供できません。これは、様々な要因がデータ処理速度に影響を与えるからです。以下に例を示しますが、これに限定されません。

* データの行数
* データのディメンション（列）の数
* カスタム処理手順の数と複雑さ
* クラスタリングの使用
* ハードウェアの速度

## ファイルサーバーのユニット要件{#file-server-unit-requirements}

サーバのFSU(File Serving Unit)は、Data Workbenchの主なデータ・ストレージおよび管理コンポーネントです。 FSUは、DPUに対する生のソースデータのファイルサーバとして機能し、必要に応じて、DPUのクラスタリングを調整します。 各FSUには、最大5つのDPUにソースデータを提供するライセンスが付与されます。

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
   <td colname="col2"> <p>これらの要件は、DPUの要件と同じです。 ただし、FSUの場合、Adobeは推奨事項に従うのではなく、最小要件を使用することをお勧めします。 </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディスクシステム </p> <p>FSUには、大量のデータに対して高可用性、冗長ストレージが必要です。 Adobeは、お客様と協力して正確な要件を決定します。 </p> </td> 
   <td colname="col1"> <p>Adobeの推奨事項： </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">（12以上） * （750 GB以上） SATA HDD （RAID 5/6構成） </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">100 MB/秒以上の持続帯域幅をサポートする高パフォーマンスSAN接続。 </li> 
    </ul> <p>FSUが生のソース・データを保持するので、損失は回復できず、Adobeは定期的にこのデータをバックアップすることを提案します。 </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネットワークパフォーマンス </p> </td> 
   <td colname="col2"> <p>Adobeでは、FSUとDPU間のスイッチギガビットイーサネット接続が必要です。 </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## センサーの要件{#sensor-requirements}

Data Workbenchセンサーは、Web、アプリケーション、データ収集サーバーからイベントデータを収集し、任意のサーバーに送信します。 [!DNL Sensor’s] インストルメンテーションは、インターネットチャネルで発生するイベントを一貫して正確に測定します。[!DNL Sensor] は、Webサーバソフトウェアとオペレーティングシステムの多くの組み合わせをサポートしています。

### センサーシステムRecommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

次の表に、[!DNL Sensor]の推奨システム構成を示します。

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
   <td colname="col2"> <p>最小512 MB。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 MBのRAMは、HTTPまたはそのホストである他のサーバーコンピューター上の<span class="wintitle">センサー</span>に対して使用可能である必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネットワークパフォーマンス </p> </td> 
   <td colname="col2"> <p>1 Mbps以上のリピーターサーバーまたは<span class="keyword"> data workbenchサーバー</span>へのネットワーク接続。 <span class="wintitle"> 通常、セ </span> ンサーの消費帯域幅は1 Mbpsよりも大幅に少なくなります。Adobeコンサルタントが、通常必要となる実際の帯域幅を見積もる際に役立ちます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネットワークポートとファイアウォール </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> Sensor </span> は、HTTPS(通常は設定可能です <span class="keyword">  </span> が、ポート443)またはHTTP（通常はポート80）を使用して、Data Workbenchサーバーに接続します（設定は可能です）。 </p> <p><span class="wintitle"> Sensor </span>と対象の<span class="keyword"> Data Workbenchサーバー</span>またはリピーターサーバーとの間にあるファイアウォール上の適切なポートは、 <span class="wintitle"> Sensor </span>インストールプロセスを開始する前に、 <span class="wintitle"> Sensor </span>とリピーターサーバーの間でのみ開く。 <span class="keyword"></span><span class="wintitle"> センサ </span> ーは、Data Workbenchサーバーまたはリピーターサーバーに対し <span class="keyword"> て、一方向のHTTPSまたは </span> HTTP接続を行います。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネットワーク管理システム </p> </td> 
   <td colname="col2"> <p>既存のネットワーク管理システムは、基になるコンピュータハードウェア（ディスク領域、ネットワークサービスなど）とネットワーク接続、Windowsイベントログ、UNIXsyslogの状態を監視する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバー時間の同期 </p> </td> 
   <td colname="col2"> <p><span class="wintitle">センサー</span>をホストするすべてのコンピューター間で、コンピューターシステムの時間が継続的に同期されていることを確認します。 <span class="wintitle">センサー</span>が監視するWebサーバーアプリケーションとコンピューターは、システム時刻を同期していなければ、Webサーバーから収集されたイベントデータが正確になりません。 NTPやその他の時刻同期機能を使用してシステム時刻を継続的に同期する手順については、オペレーティングシステムのマニュアルを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DNS名の使用 </p> </td> 
   <td colname="col2"> <p>Adobeでは、<span class="wintitle">センサー</span>で、（IPアドレスではなく）DNS名を使用して、<span class="keyword"> data workbenchサーバー</span>またはリピーターサーバーのネットワークアドレスを解決することをお勧めします。 <span class="wintitle">センサー</span>がDNS名を使用する場合は、<span class="keyword"> data workbenchサーバー</span>またはリピーターサーバーの名前を解決するように、ホストWebサーバーのDNSまたはローカルホストファイルを設定する必要があります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### サポートサーバソフトウェア {#section-d6071706539f49d9a861d87b98e6f382}

次の表に、[!DNL Sensor]がサポートする最も一般的な組み合わせを示します。

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Webサーバソフトウェア </th> 
   <th colname="col2" class="entry"> オペレーティングシステム </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Apacheサーバー/IBM HTTP Server 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003以降RedHat Enterprise Linux 6.x以降Sun Solaris 8.x以降IBM AIX 5.1x以降。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apacheサーバー2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x以降 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003以降 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Javaアプリケーションサーバー(Tomcat、JBoss、iPlanet、Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003以降RedHat Enterprise Linux 6.x以降Sun Solaris 8.x以降IBM AIX 5.1x以降。 </p> </td> 
  </tr> 
 </tbody> 
</table>

その他のサーバーとオペレーティングシステムの組み合わせについては、可用性に関するAdobeを参照してください。 [!DNL Sensor]のすべての機能が、Web/アプリケーションサーバーとオペレーティングシステムの組み合わせで利用できるわけではありません。 特定の[!DNL Sensor]リリースの詳細については、Adobeサポートにお問い合わせください。

## レポートサーバーの要件{#report-server-requirements}

Data Workbenchレポートサーバーは、スケジュールされたレポートの出力を可能にするコンポーネントです。 出力されるレポートは、ファイルシステムに配置された.PNG画像または.XLSスプレッドシートの形式、または電子メールとして出力できます。 ハードウェア要件は、[Data Workbenchクライアント](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=ja)と同じです。

[!DNL report server]には次の要件があります。

* データ（ネットワーク共有、またはローカルドライブ）の出力用のファイルシステムへのアクセス
* 設定済みのSMTPサーバーにアクセスします。
* [!DNL report]サーバーにMicrosoft Excel 2003以降がインストールされている。 詳しくは、[Officeのサーバー側自動化に関する考慮事項](http://support.microsoft.com/kb/257757)を参照してください。

## ネットワーク管理{#network-management}

Adobeは、既存のネットワーク管理システムが、Data Workbench・プラットフォームが依存するハードウェアとネットワークを監視することを推奨します。

また、Adobeでは、エラー発生時に書き込まれるFSUおよびDPUのWindowsイベントログの監視をお勧めします。

>[!NOTE]
>
>ログファイルをホストするネットワーク・ストレージ・システムは、持続的な帯域幅をDPUあたり10 MB以上提供する必要があります。

## データの可用性{#data-availability}

サーバーDPUでデータを処理し、新しいデータセットや更新されたデータセットに再処理するのは、通常で必要な方法です。

この問題は、構成の変更、データソースの変更、ハードウェアの変更、不適切な構成、ハードウェアの障害、ソフトウェアの障害、電源の障害などが原因で発生する場合があります。 このような処理や再処理がおこなわれると、すべてのデータセットとシステムデータをDPUおよびFSUコンポーネントから直ちに使用できるようにする必要があります。 この要件に準拠しないと、システムのダウンタイムが大幅に長くなり、不要になる可能性があります。

## DPUとFSUのネットワークに関する問題{#dpu-and-fsu-network-issues}

DPUおよびFSUネットワークを使用する際に注意すべき考慮事項。

* ネットワーク・ログ・ファイルを配布する場合、ログ・ファイルをホストするネットワーク・ストレージ・システムは、持続的な帯域幅をDPUあたり10 MB以上提供する必要があります。
* DPU、FSU、およびData Workbenchは、ポート80または443(デフォルトでは、ポートを別の方法で設定することもできます)。
* Data Workbench[!DNL Sensor(s)]は、（片道）サーバに接続できる必要があります。
* DPUがSMTPを介してアラートメッセージを送信できるようにするには、設定済みのSMTPサーバーと通信できる必要があります。
* Adobeでは、IPアドレスが変更された場合に再構成を避けるために、FSUおよびDPUにFSU01.CLIENT.COMなどのネットワーク名を付けることを推奨します。
