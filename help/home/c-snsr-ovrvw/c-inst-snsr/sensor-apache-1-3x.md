---
description: RedHat Linux 7.x以降、SUSE Linux 9.x以降、Sun Solaris SPARC 2.6以降、Sun Solaris x86 9以降、FreeBSD 4以降、Mac OS X PowerPC上にApache Server 1.3.x用のSensorをインストールして設定する詳細な手順。
title: Apache サーバー 1.3.x（Linux、Sun Solaris、FreeBSD、Mac OS X のいずれか）
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---


# Apache サーバー 1.3.x（Linux、Sun Solaris、FreeBSD、Mac OS X のいずれか）{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

RedHat Linux 7.x以降、SUSE Linux 9.x以降、Sun Solaris SPARC 2.6以降、Sun Solaris x86 9以降、FreeBSD 4以降、Mac OS X PowerPC上にApache Server 1.3.x用のSensorをインストールして設定する詳細な手順。

Sensorのプログラムファイルは、Adobeのダウンロードサイトから取得したインストールファイルにパッケージ化されています。 お使いのWebサーバーにSensorのインストールファイルがまだない場合は、次の手順を開始する前に、ダウンロード(またはAdobeの担当者から入手)してください。

Sensorをインストールして設定するには、次の高レベルな手順を実行する必要があります。

## Install the Program Files {#section-aae323e252394212bf4096d65fdd280c}

Sensorのプログラムファイルを抽出し、サーバーマシンにインストールする手順です。

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
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書の検証に使用される証明書です </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestTest.xlsというスプレッドシートファイルが含まれています。 このスプレッドシートは、設計者が制御実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorを実行しているコンピューターにファイルをインストールする必要はありません（ただし、インストールを選択することもできます）。 必要に応じて、設計者がアクセスできる場所にファイルをコピーするか、インストールパッケージからファイルを抽出します。 対照実験について詳しくは、『Insight Controlled Experiments Guide』を参照してください。

**プログラムファイルに対する権限**

プログラムファイルに対する権限が正しくないと、Sensorのインストール時に発生する問題の大部分が発生します。

この節に記載されているとおりに権限が設定されていることを確認してください。

デフォルトでは、tarファイル内のプログラムファイルには次の権限があります。 システムの構成によっては、ファイルを抽出する際に、これらの設定が変更（マスクされない）場合があります。 推奨されるデフォルト設定にアクセス権をリセットするには、次のchmodコマンドを使用します。 ファイルをインストールしたディレクトリで、少なくともこのレベルのアクセスが許可されていることを確認します。

| ファイル | デフォルトの権限 | chmodコマンド |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-rw- r— | chmod 664 |
| trust_ca_cert.pem | rw-rw- r— | chmod 664 |

## Edit the Sensor configuration file {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

この [!DNL txlogd.conf] ファイルには、Sensorの設定パラメーターが含まれています。

ファイルを編集して、特に、ディスクキューのサイズ、Insightサーバーのアドレス、このセンサーによって生成されるデータに添付されるIDを指定する必要があります。

設定ファイルには、必須パラメーターとオプションのパラメーターが含まれています。

* 必須パラメーターは、Sensorのインストール時に指定する必要がある設定です。 これらの設定がないと、Sensorは正常に実行されません。
* オプションのパラメータは、デフォルトで事前定義済みの値（変更可能）またはオプション機能を有効にする設定です。

Sensor設定ファイルを編集するには

1. /etc/txlogd.confファイルをテキストエディターで開き、必要なパラメーターと必要なオプションのパラメーターを設定します。
1. ファイルを保存して閉じます。

## 送信機の開始とディスク・キューの作成 {#section-a453d912ec3d47aa8e40ccacf527119d}

txlogd.confファイルを設定した後にディスクキューを作成する手順。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリに、コレクタ・モジュールと送信プログラムの両方に、ファイルへの読み取り/書き込みアクセス権が与えられていることを確認します。
1. Sensorがインストールされているコンピューターで、次のコマンドを実行して送信機の開始を行います。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、トランスミッタをインタラクティブモードで開始します。 このモードでは、送信機メッセージが画面に表示され、キーボード・コマンドを使用して送信機と対話することができます。
   * 「c」オプションは、送信機にディスク・キューを作成するよう指示します。
   * 「f」オプションは設定ファイルの場所を指定します。

1. 送信機がQueueFileパラメーターで指定された場所にディスクキューを作成し、QueueSizeパラメーターで指定されたサイズでディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl + Cキーを押して送信機を終了し、次の操作を行います。

   1. txtlogd.confファイルを調べ、QueueFileパラメーターとQueueSizeパラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作していて、QueueSizeパラメーターで指定されたサイズのファイルを保持するのに十分な領域があることを確認してください。
   1. 必要な修正を加え、この手順を繰り返します。

## Webサ追加ーバーへのコレクタ {#section-a7fb6425956f4f518ae3a7db091b33d2}

Apacheサーバーの場合、コレクターは、Webサーバープロセスに読み込む動的共有オブジェクトです。

Webサーバーにコレクターを追加するには、以下の説明に従ってhttpd.confファイルを編集し、Webサーバーを再起動する必要があります。

Sensorがサーバーコンピューター上の複数のWebサーバーのデータをキャプチャする場合は、各Webサーバーに対して次の手順を実行する必要があります。

1. テキストエディターを使用して、Sensorのイベントを取り込んだWebサーバーの [!DNL httpd.conf] ファイルを開きます。
1. フ追加ァイルの最後に次の行を追加します。

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

送信者を開始し、Insightサーバーに接続して、イベントデータを送信できることを確認します。

>[!NOTE]
>
>送信機がイベントデータをInsightサーバーに正常に送信できることを確認するには、次のテストを開始する前に、ターゲットInsightサーバーがインストールされ、実行されていることを確認します。

1. トランスミッタがまだ実行されていない場合は、次のコマンドを使用して再起動します。

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. （任意のマシン上で）ブラウザーを開き、Sensorが実行されているWebサーバーに対してページを要求します（Sensorが監視しているページを必ず選択してください）。
1. リクエストを発行した後、送信者のコンソールを調べて、送信者がイベントデータをターゲットインサイトサーバーに送信していることを示すメッセージがないかどうかを確認します。
1. センサーがデータを正常に送信しない場合は、次のことを確認します。

   * ターゲットインサイトサーバーが実行されている。
   * との [!DNL ServerAddress] パラメーターは、で正しく設定され [!DNL ServerPort][!DNL txtlogd.conf]ます。

   * サーバー名を使用 [!DNL ServerAddress] して指定した場合は、代わりに数値のIPアドレスを使用してみてください。 この [!DNL CertName] パラメーターの値は、ターゲットインサイトサーバーのデジタル証明書に表示される共通名と完全に一致します。

## シ追加ステム起動スクリプトへの送信機 {#section-4e1ffa6e043941ab91411d91d596477a}

Webサーバーコンピューターの再起動時に、送信機が自動的に読み込まれるようにする情報です。

次の追加コマンド（送信機を起動）は、システム起動スクリプトに対して実行します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、送信機をデーモンとして開始します。 送信機が生成する動作メッセージとエラーメッセージは、syslogに書き込まれます。

>[!NOTE]
>
>一部のSolarisユーザーで、「mutexを取得できません」というエラーが発生する場合があります。 Sensorがこれらのシステムで正しく機能するには、次の行を/etc/systemファイルに追加または編集する必要があります。
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>デフォルトのSolaris設定は60です。 Sensorで実行されたテストに基づき、Adobeでは、各インスタンスに3つのセマフォーを使用します。このテストでは、1024を設定として使用することを推奨します。 この値は、Sensorが、セマフォを必要とする可能性のある他のアプリケーションと共に機能するのに十分な大きさですが、パフォーマンスには影響しません。 この勧告を支持するために、Adrian Cockcroftは著書Sun Performance and Tuning（Prentice Hall、1994年10月）で次のように述べていることに注意してください。「データベースは、多くの共有メモリとセマフォの設定を使う傾向があります。 これらはパフォーマンスに影響を与えません。十分大きい限り、プログラムは動く」

