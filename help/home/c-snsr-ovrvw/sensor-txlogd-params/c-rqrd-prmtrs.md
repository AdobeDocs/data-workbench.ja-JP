---
description: 必要なセンサーのtxlogd.confパラメーターに関する情報です。
title: 必須パラメーター
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# 必須パラメーター{#required-parameters}

必要なセンサーのtxlogd.confパラメーターに関する情報です。

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> このパラメーター内… </th> 
   <th colname="col2" class="entry"> ... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>この<span class="wintitle"> Sensor</span>を一意に識別する文字列。 </p> <p> <span class="wintitle"> </span> Sensorは、SensorIDを各イベントレコードに接続し、Data Workbenchサー <span class="keyword"> バーに送信します</span>。SensorIDは、このWebサーバからのイベントデータを、他の<span class="wintitle"> Sensor</span>によってキャプチャされたイベントデータと区別することを可能にします。 </p> <p>SensorIDは任意の文字列で構成できますが、通常は、<span class="wintitle"> Sensor</span>が取り込むイベントのWebサーバー名が使用されます。 サーバー名をSensorIDとして使用すると、分析ステージでイベントのソースを簡単に特定できます。 また、実装内でSensorIDが一意になるようにします。 </p> <p>例：<span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>この<span class="wintitle"> Sensor</span>がイベントデータを送信する<span class="keyword"> Data Workbenchサーバー</span>のアドレス。 </p> <p>注釈:  <p>クラスター環境で作業する場合は、同期の問題を回避するために、マスター<span class="keyword"> data workbenchサーバー</span>にアクセスするように<span class="wintitle"> Sensor</span>を設定する必要があります。 Data Workbenchでは、<span class="wintitle">サーバーマネージャー</span>の「関連サーバー」メニュー項目を使用して、クラスター内の<span class="keyword"> data workbenchサーバー</span>の処理に関する情報を表示できます。 <span class="wintitle"> Servers Manager</span>について詳しくは、『<i><span class="keyword">Data Workbench</span><span class="wintitle">センサー</span>ガイド</i>』を参照してください。 </p> <p>WebサーバーがDNSを介してサーバー名を解決できる場合は、サーバーのアドレスを名前で指定できます。 そうでない場合は、サーバーの数値IPアドレスを指定する必要があります。 </p> <p>例：<span class="filepath"> ServerAddress 10.1.0.7</span>または </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p><span class="wintitle"> Sensor</span>が<span class="keyword"> data workbench server</span>と通信するかどうか（HTTPまたはHTTPSを使用）。 HTTPSの場合は「on」、HTTPの場合は「off」に設定します。 </p> <p>例：<span class="filepath"> SSL on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p><span class="keyword"> data workbenchサーバー</span>がイベントデータをリッスンするポート。 </p> <p>例：<span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>SSLパラメーターが「on」に設定されている場合にのみ必要です。 </p> <p>この<span class="wintitle"> Sensor</span>がイベントデータを送信する<span class="keyword"> Data Workbenchサーバー</span>の共通名。 </p> <p>指定する値は、<span class="keyword"> data workbenchサーバー</span>のライセンス証明書に表示される共通名と完全に一致する必要があります。 </p> <p>例：<span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>SSLパラメーターが「on」に設定されている場合にのみ必要です。 </p> <p>認証局(<span class="filepath"> trust_ca_cert.pem</span>)ファイルが置かれているディレクトリ </p> <p>例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>インターネットインフォメーションサービス(IIS)バージョン5.xまたは6.xを実行しているMicrosoft Windows 2000または2003 Serverマシンでの<span class="wintitle"> Sensor</span>のインストールには必要ありません。 </p> <p>ディスクキューファイルの完全修飾名。 </p> <p>このファイルには任意の名前を割り当てることができますが、通常、キューファイルの名前は<span class="filepath"> VisualSensor.dat</span>です。 </p> <p>Unixで<span class="wintitle"> Sensor</span>をインストールする場合、このファイルは任意の場所に配置できます。 Java Webサーバーを実行するWindowsでは、このファイルをトランスミッターと同じディレクトリに配置する必要があります。 その他のすべてのWebサーバーでは、このファイルは/var/queueディレクトリに配置する必要があります。 </p> <p>例：<span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>注意： このファイルを割り当てるデバイスに、必要なサイズのキューを収容するのに十分な空き領域があることを確認します。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>ディスクキューファイルのサイズ（MB単位）を表す整数。 </p> <p>Microsoft Windowsでの<span class="wintitle"> Sensor</span>のインストールの場合、キューファイル自体はトランスミッターと同じディレクトリに作成され、<span class="filepath"> Diskq2000.log</span>という名前が付けられます。 </p> <p>次の例では、キューのサイズを200 MBに設定します。 </p> <p>QueueSize 200 </p> <p>次の例では、キューのサイズを2 GBに設定します。 </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
