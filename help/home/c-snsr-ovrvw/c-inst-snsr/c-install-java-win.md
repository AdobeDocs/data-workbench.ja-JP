---
description: Windows Server 2000以降で実行するSun Java System Application Server Standard Edition 7用のSensorのインストールおよび設定の手順。
title: Windows Server 2000以降でのSun Java Server
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Server 2000以降でのSun Java Server{#sun-java-server-on-windows-server-or-later}

Windows Server 2000以降で実行するSun Java System Application Server Standard Edition 7用のSensorのインストールおよび設定の手順。

Sensorのプログラムファイルは、アドビのダウンロードサイトから入手したインストールファイルにパッケージ化されます。 お使いのWebサーバー用のSensorインストールファイルがまだない場合は、次の手順を開始する前に、ダウンロード（またはアドビの担当者から入手）してください。

Sensorは、RedHat Linux 7.x以降またはSun Solaris SPARC 2.6以降で実行されている次のサーバーをサポートしています。

Sensorをインストールして設定するには、次の手順を実行する必要があります。

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

Sensorのプログラムファイルを抽出し、サーバーにインストールする手順。

1. Netscape Enterprise、iPlanet、Sun ONE、またはSun Java System Serverで、Sensorプログラムファイルをインストールするディレクトリを作成します。 ディスクキューはこのディレクトリに存在するので、選択したデバイスに必要なサイズのキューを保持するのに十分な領域があることを確認してください。

   ```
   C:\VisualSensor
   ```

1. 作成したディレクトリにインストールファイルの内容を抽出します。 この手順で、Sensorは次のファイルをインストールします。

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> ターゲットディレクトリ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> saf_visual_sciences.dll </td> 
   <td colname="col2"> コレクタロードモジュール。 </td> 
   <td colname="col3"> <i>/usr/local/aolserver/ visual_sciences</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> 送信プログラム。 </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor設定ファイル。 </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書の検証に使用される証明書 </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestTest.xlsという名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、設計者が制御実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorを実行しているコンピューターにファイルをインストールする必要はありません（ただし、インストールは可能です）。 必要に応じて、設計者がアクセスできる場所にファイルをコピーするか、インストールパッケージからファイルを抽出します。 対照実験について詳しくは、『Insight Controlled Experiments Guide』を参照してください。

## センサー設定ファイルの編集 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

このファ [!DNL txlogd.conf] イルには、Sensorの設定パラメーターが含まれています。

このファイルを編集して、特に、ディスクキューファイルのサイズと場所、Insightサーバーのアドレス、およびこのセンサーによって生成されるイベントデータに添付されるIDを指定する必要があります。

設定ファイルには、必須パラメーターとオプションのパラメーターが含まれています。

* **必須パラメータ** ーは、Sensorのインストール時に指定する必要がある設定です。 これらの設定がないと、Sensorは正常に実行されません。
* **オプションのパラメータ** は、デフォルトで事前定義された値（変更可能）に設定される設定、またはオプション機能を有効にする設定です。

**Sensor設定ファイルを編集するには**

* テキストエデ [!DNL /etc/txlogd.conf] ィターでファイルを開き、必要なパラメーターと必要なオプションのパラメーターを設定します。
* ファイルを保存して閉じます。

**Sensor設定ファイルを編集するには**

1. テキストエデ [!DNL /etc/txlogd.conf] ィターでファイルを開き、必要なパラメーターと必要なオプションのパラメーターを設定します。
1. ファイルを保存して閉じます。

## 送信機を起動し、ディスク・キューを作成する {#section-55630de65f264274aefd771da2002852}

txlogd.confファイルを設定したら、送信プログラムを起動し、Windowsサービスとして登録し、ディスクキューを作成します。

1. Windowsのスタートメニューで、アクセサリ/コマンドプロンプトを選択します。
1. コマンドプロンプトウィンドウで、Sensorをインストールしたディレクトリに移動し、次のコマンドを実行します。

   ```
   txlog /regserver
   ```

   このコマンドは、トランスミッタを起動し、ディスクキューを作成し、SensorをWindowsサービスとして登録します。

1. 送信機が正しく動作していることを確認するには、スタート/コントロールパネル/管理ツール/サービスをクリックします。 サービスリストで、Sensorのエントリを探し、ステータスがStartedで、スタートアップの種類がAutomaticであることを確認します。 次に、[サービス]コントロールパネルを閉じます。
1. 起動中に送信機でエラーが発生したかどうかを確認するには、スタート/コントロールパネル/管理ツール/イベントビューアをクリックし、イベントビューアを開きます。

   1. 「Event Viewer」ウィンドウの左ペインで、「Applications」ログを選択します。
   1. 右側のウィンドウで、「Source」列に「Adobe」が含まれているイベントを探します。
   1. 「アドビ」からエラーが見つかった場合は、エラーをダブルクリックして、イベントのプロパティウィンドウを表示します。 このウィンドウには、エラーに関する詳細情報が表示されます。

1. アプリケーションログの確認が完了したら、イベントビューアを閉じます。
1. 送信機が、Sensorプログラムファイルをインストールしたディレクトリにディスクキュー(Diskq2000.log)を作成し、txlogd.confファイルのQueueSizeパラメーターで指定したサイズであることを確認します。

   キューが正しく作成されていない場合：

   1. txtlogd.confファイルを調べ、QueueSizeパラメーターが正しく設定されていることを確認します。
   1. Sensorをインストールしたデバイスに、QueueSizeパラメーターで指定したサイズのファイルを保持するのに十分な空き領域があることを確認します。
   1. Windowsのサービス・コントロール・パネルを使用して、送信機を停止します。
   1. キューファイルを削除します。
   1. SensorをWindowsサービスとして再登録します。windowsのスタートメニューから、アクセサリ/コマンドプロンプトを選択します。 コマンドプロンプトウィンドウで、Sensorをインストールしたディレクトリに移動し、次のコマンドを実行します。

      ```
      txlog /regserver
      ```

送信機は、連続的に動作するように設計されています。 コンピューターを再起動すると、送信機が自動的に再起動します。 送信機を手動で起動および停止する必要がある場合は、Windowsのサービスコントロールパネルを使用して実行できます。

## 起動スクリプトの変更 {#section-19a38f27c9f44adf88f8910f5ed483a3}

init.confファイル(例：C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf)の末尾に次の行を追加します。

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

obj.confファイル(例：C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.conf)で、既存の「」行のすぐ下に次の行を追加<Object name="default">します。

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```

