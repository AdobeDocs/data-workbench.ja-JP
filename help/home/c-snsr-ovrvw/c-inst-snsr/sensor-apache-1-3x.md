---
description: RedHat Linux 7.x以降、SUSE Linux 9.x以降、Sun Solaris SPARC 2.6以降、Sun Solaris x86 9以降、FreeBSD 4以降、またはMac OS X PowerPC上でApache Server 1.3.x用のSensorのインストールと設定の詳細手順。
title: Linux、Sun Solaris、FreeBSD、またはMac OS X上のApache Server 1.3.x
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Linux、Sun Solaris、FreeBSD、またはMac OS X上のApache Server 1.3.x{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

RedHat Linux 7.x以降、SUSE Linux 9.x以降、Sun Solaris SPARC 2.6以降、Sun Solaris x86 9以降、FreeBSD 4以降、またはMac OS X PowerPC上でApache Server 1.3.x用のSensorのインストールと設定の詳細手順。

Sensorのプログラムファイルは、アドビのダウンロードサイトから入手したインストールファイルにパッケージ化されます。 お使いのWebサーバー用のSensorインストールファイルがまだない場合は、次の手順を開始する前に、ダウンロード（またはアドビの担当者から入手）してください。

Sensorをインストールして設定するには、次の高レベルな手順を実行する必要があります。

## Install the Program Files {#section-aae323e252394212bf4096d65fdd280c}

Sensorのプログラムファイルを抽出し、サーバーコンピューターにインストールする手順です。

1. rootユーザーまたはroot権限を持つユーザーとしてログオンします。
1. 次のコマンドを使用して、インストールファイルを解凍し、解凍します。

   * Linuxの場合：

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * Solarisの場合：

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. 展開したプログラムファイルを、次の表に示すディレクトリにコピーします。

<table id="table_A97CF630633C4543A742D96C302D1138"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> ターゲットディレクトリ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> コレクタロードモジュール </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> 送信プログラム </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor設定ファイル </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書の検証に使用される証明書 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestTest.xlsという名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、設計者が制御実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorを実行しているコンピューターにファイルをインストールする必要はありません（ただし、インストールする必要はありません）。 必要に応じて、設計者がアクセスできる場所にファイルをコピーするか、インストールパッケージからファイルを抽出します。 対照実験について詳しくは、『Insight Controlled Experiments Guide』を参照してください。

**プログラムファイルの権限**

プログラムファイルに対する権限が正しくないと、Sensorのインストール時に発生する問題の大部分が発生します。

この節で説明したとおりに権限が設定されていることを確認してください。

デフォルトでは、tarファイル内のプログラムファイルには次の権限があります。 システムの設定によっては、ファイルを抽出する際に、これらの設定が変更（マスクされない）される場合があります。 推奨されるデフォルト設定に権限をリセットするには、次のchmodコマンドを使用します。 ファイルをインストールしたディレクトリで、少なくともこのレベルのアクセスが許可されていることを確認します。

| File | デフォルトの権限 | chmodコマンド |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-rw- r— | chmod 664 |
| trust_ca_cert.pem | rw-rw- r— | chmod 664 |

## Sensor設定ファイルの編集 {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

このファ [!DNL txlogd.conf] イルには、Sensorの設定パラメーターが含まれています。

ファイルを編集して、特に、ディスクキューのサイズ、Insightサーバーのアドレス、およびこのセンサーで生成されるデータに添付されるIDを指定する必要があります。

設定ファイルには、必須パラメーターとオプションのパラメーターが含まれています。

* 必須パラメーターは、Sensorのインストール時に指定する必要がある設定です。 これらの設定がないと、Sensorは正常に実行されません。
* オプションのパラメーターは、デフォルトで事前定義済みの値（変更可能）に設定される設定、またはオプション機能を有効にする設定です。

Sensor設定ファイルを編集するには

1. /etc/txlogd.confファイルをテキストエディターで開き、必要なパラメーターと必要なオプションのパラメーターを設定します。
1. ファイルを保存して閉じます。

## 送信機を起動し、ディスク・キューを作成する {#section-a453d912ec3d47aa8e40ccacf527119d}

txlogd.confファイルの設定後にディスクキューを作成する手順。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリがコレクタ・モジュールと送信プログラムの両方にファイルへの読み取り/書き込みアクセスを提供していることを確認します。
1. Sensorがインストールされているコンピューターで、次のコマンドを実行して送信機を起動します。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、送信機をインタラクティブ・モードで起動します。 このモードは、送信機のメッセージを画面に表示し、キーボードコマンドを使用して送信機とやり取りすることもできます。
   * 「c」オプションは、送信機にディスク・キューを作成するよう指示します。
   * 「f」オプションは設定ファイルの場所を指定します。

1. 送信機が、QueueFileパラメーターで指定された場所と、QueueSizeパラメーターで指定されたサイズのディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl + Cキーを押して送信機を終了し、次の手順を実行します。

   1. txtlogd.confファイルを調べ、QueueFileパラメーターとQueueSizeパラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作し、QueueSizeパラメータで指定されたサイズのファイルを保持するのに十分な空き領域があることを確認します。
   1. 必要な修正を加え、この手順を繰り返します。

## Webサーバーへのコレクタの追加 {#section-a7fb6425956f4f518ae3a7db091b33d2}

Apacheサーバーの場合、コレクターは、Webサーバープロセスに読み込む動的共有オブジェクトです。

Webサーバーにコレクターを追加するには、以下の説明に従ってhttpd.confファイルを編集し、Webサーバーを再起動する必要があります。

Sensorがサーバーコンピューター上の複数のWebサーバーのデータを取り込む場合は、各Webサーバーに対して次の手順を実行する必要があります。

1. テキストエディターを使用して、Sensorで取 [!DNL httpd.conf] り込んだイベントを持つWebサーバーのファイルを開きます。
1. ファイルの末尾に次の行を追加します。

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >これらの行では大文字と小文字が区別されます。 上に表示されたとおりに入力します。

1. Webサーバーを再起動します。 コレクタはWebサーバーと共に読み込まれ、イベントデータの収集とディスクキューへの書き込みを開始します。

## センサーのテスト {#section-83d9f60b39a6474f9c76bee3e19b2575}

送信機を起動し、Insightサーバーに接続して、イベントデータを送信できることを確認します。

>[!NOTE]
>
>送信機がイベントデータをInsightサーバーに正常に送信できることを確認するには、次のテストを開始する前に、ターゲットのInsightサーバーがインストールされ、実行されていることを確認します。

1. トランスミッタがまだ実行されていない場合は、次のコマンドを使用して再起動します。

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. （任意のマシン上の）ブラウザーを開き、Sensorが実行されているWebサーバーからページを要求します（Sensorが監視しているページを必ず選択してください）。
1. リクエストを発行した後、送信機のコンソールで、送信機がターゲットのInsightサーバーにイベントデータを送信していることを示すメッセージを確認します。
1. センサーがデータを正常に送信しない場合は、次のことを確認します。

   * 対象のInsightサーバーが実行中です。
   * とのパ [!DNL ServerAddress] ラメー [!DNL ServerPort] ターは、で正しく設定されま [!DNL txtlogd.conf]す。

   * サーバー名を使 [!DNL ServerAddress] 用して指定した場合は、代わりに数値のIPアドレスを使用してみてください。 このパラメーターの値 [!DNL CertName] は、ターゲットInsightサーバーのデジタル証明書に表示される共通名と完全に一致します。

## システム起動スクリプトへの送信機の追加 {#section-4e1ffa6e043941ab91411d91d596477a}

Webサーバーコンピューターの再起動時に送信機が自動的に読み込まれるようにする情報です。

次のコマンド（送信機を起動するコマンド）をシステム起動スクリプトに追加します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、送信機をデーモンとして起動します。 送信機が生成する動作メッセージとエラーメッセージはsyslogに書き込まれます。

>[!NOTE]
>
>一部のSolarisユーザーで、「mutexを取得できません」というエラーが発生する場合があります。 Sensorがこれらのシステムで正しく機能するには、次の行を/etc/systemファイルに追加または編集する必要があります。>
>
```>
>semsys:seminfo_semmnu=1024
>```>
>The default Solaris setting is 60. Based on tests conducted with Sensor, which uses three semaphores for each instance, Adobe recommends that you use 1024 as your setting. This number is high enough for Sensor to function along with any other applications on the server that may require semaphores, but does not affect performance. To support this recommendation, please note that Adrian Cockcroft stated the following in his book Sun Performance and Tuning (Prentice Hall, October 1994): “Databases tend to use lots of shared memory and semaphore settings. These do not affect performance; as long as they are big enough, the programs will run.”



