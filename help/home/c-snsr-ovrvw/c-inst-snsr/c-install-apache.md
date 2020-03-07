---
description: Linux、Sun SolarisまたはFreeBSD上でApache Server 2.0.40、2.0.42以降、Apache Server 2.2、またはApache Server 2.4をインストールして設定する手順。
title: Linux、SolarisまたはFreeBSD上のApache Server 2.0.40、2.0.42以降、およびApache Server 2.2または2.4
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Linux、SolarisまたはFreeBSD上のApache Server 2.0.40、2.0.42以降、およびApache Server 2.2または2.4{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

Linux、Sun SolarisまたはFreeBSD上でApache Server 2.0.40、2.0.42以降、Apache Server 2.2、またはApache Server 2.4をインストールして設定する手順。

Sensorのプログラムファイルは、アドビのダウンロードサイトから入手したインストールファイルにパッケージ化されます。 お使いのWebサーバー用のSensorインストールファイルがまだない場合は、次の手順を開始する前に、ダウンロード（またはアドビの担当者から入手）してください。

Sensorをインストールして設定するには、次の高レベルな手順を実行する必要があります。

次のApacheサーバーがサポートされています。

* RedHat Linux 7.x以降、またはSun Solaris SPARC 2.6以降で実行されるApache Server 2.0.40。
* Linux、Sun SolarisまたはFreeBSD上のApache Server 2.0.40、2.0.42以降、Apache Server 2.2、またはApache Server 2.4
* RedHat Linux 7.x以降、Sun Solaris SPARC 2.6以降、SUSE Linux 9.x以降、またはFreeBSD 5.3で動作するApache Server 2.0.42以降。
* 64ビット版のRedHat Linux ES 4およびES 5で動作するApache Server 2.0.42以降。
* RedHat Linux 7.x以降またはSun Solaris SPARC 2.6以降で稼働するApache Server 2.2。
* RedHat Linux 7.x以降、Sun Solaris x86_64、またはFreeBSDで動作するApache Server 2.4

>[!NOTE]
>
>Apache Serverバージョン2.0.40、2.0.42以降（32ビットおよび64ビット）、2.2を実行するWebサーバーにSensorをインストールする手順は同じですが（次の手順で説明している場合を除き）、各バージョンのインストールファイルは異なります。 Sensorをインストールする前に、実行しているApacheサーバーおよびオペレーティングシステムのバージョンに対して、正しいインストールファイルを受け取っていることを確認します。

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

Sensor用のプログラムファイルを抽出してインストールする手順。

1. rootユーザーまたはroot権限を持つユーザーとしてログオンします。
1. 次のコマンドを使用して、インストールファイルを解凍し、解凍します。

   * Linuxの場合：

      ```
      tar -zxf installationFilename
      ```

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

   * Solarisの場合：

1. 展開したプログラムファイルを、次の表に示すディレクトリにコピーします。

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
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> コレクタロードモジュール。 </td> 
   <td colname="col3"> <i> IBMHttpServer/モジュール</i> </td> 
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

**プログラムファイルの権限**

>[!NOTE]
>
>プログラムファイルに対する権限が正しくないと、Sensorのインストール時に発生する問題の大部分が発生します。 この節で説明したとおりに権限が設定されていることを確認してください。
>
>デフォルトでは、tarファイル内のプログラムファイルには次の権限があります。 システムの設定によっては、ファイルを抽出する際に、これらの設定が変更（マスクされない）される場合があります。 推奨されるデフォルト設定に権限をリセットするには、次のchmodコマンドを使用します。 ファイルをインストールしたディレクトリで、少なくともこのレベルのアクセスが許可されていることを確認します。

| File | デフォルトの権限 | chmodコマンド |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-r— r— | chmod 664 |
| trust_ca_cert.pem | rw-r— r— | chmod 664 |

## Sametimeサーバーでのログの有効化 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Sametimeサーバーにログオンするための手順です。

1. Lotus Domino Administratorクライアントを使用して、Sametimeを実行しているLotus Dominoサーバーに接続します。
1. Lotus Domino Administratorで、「ファイル」タブをクリックし、Sametime Configuration - stconfig.nsfをダブルクリックして、Sametime Configurationファイルを開きます。
1. Sametime設定ファイルで、Community Servicesフォームを開き、フォームの任意の場所をダブルクリックして編集モードにします。
1. 「チャットログフラグ」を「厳密」に、「サービスの種類を取得」を「0x1000」に設定します。
1. コミュニティサービスフォームを保存して閉じ、Sametime設定ファイルを閉じます。
1. Sametimeサーバーを再起動します。

## センサー設定ファイルの編集 {#section-de0eb4a646394b61abb6cd5a2b706de0}

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

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリがコレクタ・モジュールと送信プログラムの両方にファイルへの読み取り/書き込みアクセスを提供していることを確認します。

   ディスクキューファイルに必要な権限について詳しくは、Sensor UNIX File Permissionsを参照してください。
1. Sensorがインストールされているコンピューターで、次のコマンドを実行して送信機を起動します。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、送信機を「インタラクティブ・モード」で起動します。このモードは、送信機のメッセージを画面に表示し、キーボードコマンドを使用して送信機とやり取りすることもできます。
   * 「c」オプションは、送信機にディスク・キューを作成するよう指示します。
   * 「f」オプションは設定ファイルの場所を指定します。
   送信機の起動時に使用できるオプションについて詳しくは、Sensor Transmitter Command-Line Optionsを参照してください。

1. 送信機が、QueueFileパラメーターで指定された場所と、QueueSizeパラメーターで指定されたサイズのディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl + Cキーを押して送信機を終了し、次の手順を実行します。

   1. txtlogd.confファイルを調べ、QueueFileパラメーターとQueueSizeパラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作し、QueueSizeパラメータで指定されたサイズのファイルを保持するのに十分な空き領域があることを確認します。
   1. 必要な修正を加え、この手順を繰り返します。

## Webサーバーへのコレクタの追加 {#section-c5b83ae4ebce430aa764f951e849b333}

IBM HTTPサーバーの場合、コレクターはWebサーバープロセスに読み込む動的共有オブジェクトです。

Webサーバーにコレクターを追加するには、以下の説明に従ってhttpd.confファイルを編集し、Webサーバーを再起動する必要があります。

Sensorがサーバーコンピューター上の複数のWebサーバーのデータを取り込む場合は、各Webサーバーに対して次の手順を実行する必要があります。

1. テキストエディターを使用して、Sensorが取り込むイベントのWebサーバーのhttpd.confファイルを開きます。
1. ファイルの末尾に次の2行を追加します。

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >これらの行では大文字と小文字が区別されます。 上に表示されたとおりに入力します。

1. Webサーバープロセスを再起動します（サーバーコンピューター全体を再起動する必要はなく、Webサーバープロセスを再起動します）。 コレクタは、Webサーバと共に読み込まれ、イベントデータの収集とディスクキューへの書き込みを開始する。

## センサーのテスト {#section-0dae181ef8884f10a57f6cfda8500969}

コレクターがイベントデータを収集し、送信者がそのデータをターゲットのInsightサーバーに送信していることを確認します。

>[!NOTE]
>
>送信機がイベントデータをInsightサーバーに正常に送信できることを確認するには、次のテストを開始する前に、ターゲットのInsightサーバーがインストールされ、実行されていることを確認します。

1. トランスミッタがまだ実行されていない場合は、次のコマンドを使用して再起動します。

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. （任意のマシン上の）ブラウザーを開き、Sensorが実行されているWebサーバーからページを要求します（Sensorが監視しているページを必ず選択してください）。
1. リクエストを発行した後、送信機のコンソールで、送信機がターゲットのInsightサーバーにイベントデータを送信していることを示すメッセージを確認します。
1. センサーがデータを正常に送信しない場合は、次の点を確認します。

   * 対象のInsightサーバーが実行中です。
   * txtlogd.confでServerAddressパラメーターとServerPortパラメーターが正しく設定されている。 サーバー名を使用してServerAddressを指定した場合は、代わりに数値のIPアドレスを使用してみてください。
   * CertNameパラメーターの値は、ターゲットInsightサーバーのデジタル証明書に表示される共通名と完全に一致します。

## システム起動スクリプトへの送信機の追加 {#section-19a38f27c9f44adf88f8910f5ed483a3}

システムの起動スクリプトへの送信機の自動読み込みに関する情報です。

Webサーバー・マシンの再起動時に送信機が自動的に読み込まれるようにするには、次のコマンド（送信機を起動するコマンド）をシステムの起動スクリプトに追加します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、送信機をデーモンとして起動します。 送信機が生成する動作メッセージとエラーメッセージはsyslogに書き込まれます。
