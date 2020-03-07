---
description: 必要なSensor txlogd.confパラメーターに関する情報です。
solution: Insight
title: 必須パラメータ
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Required Parameters{#required-parameters}

必要なSensor txlogd.confパラメーターに関する情報です。

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> このパラメータ内… </th> 
   <th colname="col2" class="entry"> ... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>このセンサーを一意に識別する文字 <span class="wintitle"> 列</span>。 </p> <p> <span class="wintitle"> Sensorは</span> 、SensorIDをData Workbenchサーバーに送信する各イベントレコードに <span class="keyword"> 追加します</span>。 SensorIDを使用すると、このWebサーバーからのイベントデータを、他のSensorによってキャプチャされたイベントデータと区別で <span class="wintitle"> きます</span>。 </p> <p>SensorIDは任意の文字列で構成できますが、通常は、Sensorがキャプチャするイベントを持つWebサーバーの <span class="wintitle"> 名前</span> が使用されます。 サーバー名をSensorIDとして使用すると、分析段階でイベントのソースを簡単に判断できます。 また、実装内でSensorIDが一意であることも確認します。 </p> <p>例： <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>このSensorがイベントデータを送 <span class="keyword"> 信するData Workbench</span> Serverのア <span class="wintitle"> ドレスです</span> 。 </p> <p>注釈:  <p>When working in a clustered environment, <span class="wintitle"> Sensor</span> should be configured to access the master <span class="keyword"> data workbench server</span> to avoid synchronization issues. In Data Workbench you can view information about the processing <span class="keyword"> data workbench servers</span> in your cluster using the Related Servers menu item in the <span class="wintitle"> Servers Manager</span>. サーバーマネージャーについて詳し <span class="wintitle"> くは</span>、『 <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span> Guide』を参照してください</i>。 </p> <p>WebサーバーがDNSを使用してサーバー名を解決できる場合は、サーバーのアドレスを名前で指定できます。 サーバーのIPアドレスが指定されていない場合は、サーバーの数値を指定する必要があります。 </p> <p>例： <span class="filepath"> ServerAddress 10.1.0.7</span> 、 </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Sensorが <span class="wintitle"> HTTPまたはHTTPSを使用</span><span class="keyword"></span> してData Workbenchサーバーと通信するかどうか。 HTTPSの場合は「on」、HTTPの場合は「off」に設定します。 </p> <p>例： <span class="filepath"> SSLオン</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>Data Workbenchサーバーがイベントデ <span class="keyword"> ータをリスンする</span> ポートです。 </p> <p>例：サー <span class="filepath"> バポート443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>SSLパラメーターが「on」に設定されている場合にのみ必須です。 </p> <p>このSensorがイベントデータを送 <span class="keyword"> 信するData Workbench</span> Serverの共 <span class="wintitle"> 通名です</span> 。 </p> <p>指定する値は、Data Workbenchサーバーのライセンス証明書に表示される共通名と完全に一致する <span class="keyword"> 必要があ</span> ります。 </p> <p>例： <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>SSLパラメーターが「on」に設定されている場合にのみ必須です。 </p> <p>認証局(<span class="filepath"> trust_ca_cert.pem</span>)ファイルが存在するディレクトリ </p> <p>例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Microsoft Windows <span class="wintitle"></span> 2000または2003 ServerコンピューターでInternet Information Service(IIS)バージョン5.xまたは6.xを実行している場合は、Sensorをインストールする必要はありません。 </p> <p>ディスクキューファイルの完全修飾名。 </p> <p>このファイルには任意の名前を割り当てることができますが、通常、キューファイルの名前は <span class="filepath"> VisualSensor.datです</span>。 </p> <p>Unixでの <span class="wintitle"> Sensorのインストールの場合</span> 、このファイルはどこにでも配置できます。 Java Webサーバーを実行するWindowsでは、このファイルを送信機と同じディレクトリに配置する必要があります。 他のすべてのWebサーバーの場合、このファイルは/var/queueディレクトリに存在する必要があります。 </p> <p>例：QueueFile <span class="filepath"> /var/queue/VisualSensor.dat</span> </p> <p> <p>注意： このファイルを割り当てるデバイスに、必要なサイズのキューを収容するのに十分な空き領域があることを確認します。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>ディスクキューファイルのサイズ（MB単位）を表す整数です。 </p> <p>Microsoft Windows <span class="wintitle"> に</span> Sensorをインストールする場合、キューファイル自体は送信機と同じディレクトリに作成され、 <span class="filepath"> Diskq2000.logという名前が付けられます</span>。 </p> <p>次の例では、キューのサイズを200 MBに設定します。 </p> <p>QueueSize 200 </p> <p>次の例では、キューのサイズを2 GBに設定します。 </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

