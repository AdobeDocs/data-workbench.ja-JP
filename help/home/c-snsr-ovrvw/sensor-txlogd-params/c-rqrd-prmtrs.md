---
description: 必要なSensor txlogd.confパラメーターに関する情報です。
solution: Analytics
title: 必須パラメーター
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---


# 必須パラメーター{#required-parameters}

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
   <td colname="col2"> <p>この <span class="wintitle"> Sensorを一意に識別する文字列</span>。 </p> <p> <span class="wintitle"> Sensor</span> は、SensorIDを各イベントレコードに添付し、Data Workbenchサーバーに送信し <span class="keyword"> ます</span>。 SensorIDを使用すると、このWebサーバーからのイベントデータを、他の <span class="wintitle"> Sensorが取り込んだイベントデータと区別できます</span>。 </p> <p>SensorIDは任意の文字列で構成できますが、通常は、 <span class="wintitle"> Sensorが取り込むイベントのWebサーバー名が使用されます</span> 。 サーバー名をSensorIDとして使用すると、分析段階でイベントのソースを簡単に特定できます。 また、実装内でSensorIDが一意であることを確認します。 </p> <p>例： <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>この <span class="keyword"> Sensorがイベントデータを送信する</span> Data Workbenchサーバーのアドレス <span class="wintitle"></span> 。 </p> <p>注釈:  <p>When working in a clustered environment, <span class="wintitle"> Sensor</span> should be configured to access the master <span class="keyword"> data workbench server</span> to avoid synchronization issues. In Data Workbench you can view information about the processing <span class="keyword"> data workbench servers</span> in your cluster using the Related Servers menu item in the <span class="wintitle"> Servers Manager</span>. サーバーマネージャーの詳細については、『 <span class="wintitle"> Data Workbench</span><i><span class="keyword"></span><span class="wintitle"> Sensor</span> Guide</i>』を参照してください。 </p> <p>WebサーバーがDNSを使用してサーバー名を解決できる場合は、サーバーのアドレスを名前で指定できます。 サーバー名が入力されていない場合は、サーバーの数値のIPアドレスを指定する必要があります。 </p> <p>例： <span class="filepath"> ServerAddress 10.1.0.7</span> または </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Sensor <span class="wintitle"> が、HTTPまたはHTTPSを使用して</span> data workbenchサーバーと通信するかどうか <span class="keyword"></span> 。 HTTPSの場合は「on」、HTTPの場合は「off」に設定します。 </p> <p>例： <span class="filepath"> SSL on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>Data Workbenchサーバーが <span class="keyword"> イベントデータをリッスンするポート</span> 。 </p> <p>例： <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>SSLパラメーターが「on」に設定されている場合にのみ必要です。 </p> <p>この <span class="keyword"> Sensorがイベントデータを送信するData Workbenchサーバー</span><span class="wintitle"></span> の共通名です。 </p> <p>指定する値は、Data Workbenchサーバーの <span class="keyword"> ライセンス証明書に表示される共通名と完全に一致する必要があります</span> 。 </p> <p>例： <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>SSLパラメーターが「on」に設定されている場合にのみ必要です。 </p> <p>認証局(<span class="filepath"> trust_ca_cert.pem</span>)ファイルが存在するディレクトリ </p> <p>例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>インターネット情報サービス(IIS)バージョン5.xまたは6.xを実行するMicrosoft Windows <span class="wintitle"> 2000または2003 ServerコンピューターにSensor</span> をインストールする場合は不要です。 </p> <p>ディスクキューファイルの完全修飾名。 </p> <p>このファイルには任意の名前を割り当てることができますが、通常、キューファイルの名前は <span class="filepath"> VisualSensor.datです</span>。 </p> <p>Unixでの <span class="wintitle"> Sensor</span> インストールの場合は、このファイルを任意の場所に配置できます。 Java Webサーバーを実行するWindowsでは、送信者と同じディレクトリにこのファイルを配置する必要があります。 他のすべてのWebサーバーでは、このファイルは/var/queueディレクトリに存在する必要があります。 </p> <p>例： <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>注意： このファイルを割り当てるデバイスに、必要なサイズのキューを収容するのに十分な空き領域があることを確認します。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>ディスクキューファイルのサイズ（MB単位）を表す整数です。 </p> <p>Microsoft Windowsで <span class="wintitle"> Sensorをインストールする場合</span> 、キューファイル自体は送信機と同じディレクトリに作成され、Diskq2000.logという名前が付けられます <span class="filepath"></span>。 </p> <p>次の例では、キューサイズを200 MBに設定します。 </p> <p>QueueSize 200 </p> <p>次の例では、キューサイズを2 GBに設定します。 </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

