---
description: 必要なセンサーの txlogd.conf パラメーターに関する情報です。
title: 必須パラメーター
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# 必須パラメーター{#required-parameters}

{{eol}}

必要なセンサーの txlogd.conf パラメーターに関する情報です。

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
   <td colname="col2"> <p>これを一意に識別する文字列 <span class="wintitle"> センサー</span>. </p> <p> <span class="wintitle"> センサー</span> は、SensorID を、 <span class="keyword"> data workbench サーバー</span>. SensorID を使用すると、この Web サーバーからのイベントデータを、他のユーザーが取り込んだイベントデータと区別することができます <span class="wintitle"> センサー</span>. </p> <p>SensorID は任意の文字列で構成できますが、慣例により、イベントが <span class="wintitle"> センサー</span> はキャプチャを使用します。 サーバー名を SensorID として使用すると、分析ステージでイベントのソースを簡単に判断できます。 また、実装内で SensorID が一意であることも確認します。 </p> <p>例： <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>のアドレス <span class="keyword"> data workbench サーバー</span> この <span class="wintitle"> センサー</span> はイベントデータを送信します。 </p> <p>注釈:  <p>クラスター環境で作業する場合、 <span class="wintitle"> センサー</span> マスターにアクセスするように設定する必要があります <span class="keyword"> data workbench サーバー</span> 同期の問題を回避するため。 Data Workbenchで、処理に関する情報を表示できます <span class="keyword"> data workbench サーバー</span> クラスター内で、 <span class="wintitle"> サーバーマネージャー</span>. 詳しくは、 <span class="wintitle"> サーバーマネージャー</span>を参照し、 <i><span class="keyword"> Data Workbench</span><span class="wintitle"> センサー</span> ガイド</i>. </p> <p>Web サーバーが DNS を介してサーバー名を解決できる場合は、サーバーのアドレスを名前で指定できます。 そうでない場合は、サーバーの数値 IP アドレスを指定する必要があります。 </p> <p>例： <span class="filepath"> ServerAddress 10.1.0.7</span> または </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Wheth <span class="wintitle"> センサー</span> ～と通信する <span class="keyword"> data workbench サーバー</span> HTTP または HTTPS を使用している場合。 HTTPS の場合は「on」、HTTP の場合は「off」に設定します。 </p> <p>例： <span class="filepath"> SSL オン</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>ポート <span class="keyword"> data workbench サーバー</span> イベントデータをリッスンします。 </p> <p>例： <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>SSL パラメーターが「on」に設定されている場合にのみ必須です。 </p> <p>の共通名 <span class="keyword"> data workbench サーバー</span> この <span class="wintitle"> センサー</span> はイベントデータを送信します。 </p> <p>指定する値は、 <span class="keyword"> data workbench サーバー</span> ライセンス証明書。 </p> <p>例： <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>SSL パラメーターが「on」に設定されている場合にのみ必須です。 </p> <p>認証局 (<span class="filepath"> trust_ca_cert.pem</span>) ファイルが見つかりました </p> <p>例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>不要 <span class="wintitle"> センサー</span> Microsoft Windows 2000 または 2003 Server マシンで Internet Information Service(IIS) バージョン 5.x または 6.x を実行しているインストール </p> <p>ディスクキューファイルの完全修飾名。 </p> <p>このファイルには任意の名前を割り当てることができますが、キューファイルの名前は、慣例によって変更されます <span class="filepath"> VisualSensor.dat</span>. </p> <p>の場合 <span class="wintitle"> センサー</span> UNIX 上でのインストールでは、このファイルを任意の場所に配置できます。 Java Web サーバーを実行する Windows では、このファイルをトランスミッターと同じディレクトリに配置する必要があります。 その他のすべての Web サーバーでは、このファイルは/var/queue ディレクトリに配置する必要があります。 </p> <p>例： <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>注意：このファイルを割り当てたデバイスに、必要なサイズのキューが入るのに十分な空き領域があることを確認してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>ディスクキューファイルのサイズを MB 単位で表す整数です。 </p> <p>の場合 <span class="wintitle"> センサー</span> Microsoft Windows でのインストールでは、キューファイル自体はトランスミッターと同じディレクトリに作成され、という名前が付けられます。 <span class="filepath"> Diskq2000.log</span>. </p> <p>次の例では、キューのサイズを 200 MB に設定します。 </p> <p>QueueSize 200 </p> <p>次の例では、キューのサイズを 2 GB に設定します。 </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
