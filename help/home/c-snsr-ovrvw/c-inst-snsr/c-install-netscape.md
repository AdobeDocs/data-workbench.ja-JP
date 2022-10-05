---
description: Linux または Solaris マシン上で動作する元の Netscape Enterprise Web Server から進化した Web サーバファミリに Sensor をインストールして設定する手順。 Netscape Enterprise、iPlanet、Sun ONE、Sun Java System Servers（Linux または Solaris）が含まれます。
title: Netscape Enterprise（Linux または Solaris）
uuid: 47ea614c-d45c-4ab4-a8fe-ed9227da4582
exl-id: bd2e50b9-94fe-4f05-b227-11e83eb0a665
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 1%

---

# Netscape Enterprise（Linux または Solaris）{#netscape-enteprise-on-linux-or-solaris}

{{eol}}

Linux または Solaris マシン上で動作する元の Netscape Enterprise Web Server から進化した Web サーバファミリに Sensor をインストールして設定する手順。 Netscape Enterprise、iPlanet、Sun ONE、Sun Java System Servers（Linux または Solaris）が含まれます。

Sensor のプログラムファイルは、インストールファイルにパッケージ化され、Adobeダウンロードサイトから入手できます。 ご使用の Web サーバー用の Sensor インストールファイルがまだない場合は、次の手順を開始する前に、そのファイルをダウンロード ( またはAdobe担当者から入手 ) してください。

センサーは、RedHat Linux 7.x 以降または Sun Solaris SPARC 2.6 以降で稼働する次のサーバーをサポートしています。

* Netscape Enterprise Server 3.6 以降
* iPlanet Web Server 4.0 以降

センサーは、RedHat Linux 7.x 以降または Sun Solaris 8.x 以降で稼働する次のサーバーをサポートしています。

* Sun ONE Web Server 6.0 以降
* Sun Java System Web Server 6.1 以降

Sensor は、Sun Solaris x86 9 以降で稼働する次のサーバをサポートします。

* Sun Java System Web Server 6.1 以降

>[!NOTE]
>
>このファミリの Web サーバのインストールファイルは、Adobeのダウンロードサイトで「Netscape Solaris Sensor」または「Netscape LINUX Sensor」と表示されます。

Sensor をインストールして設定するには、次の手順を実行する必要があります。

## プログラムファイルのインストール {#section-2f3e85083b4f4aa989a85997330e86ae}

Sensor のプログラムファイルを抽出してインストールする手順です。

1. root ユーザーまたは root 権限を持つユーザーとしてログオンします。
1. 次のコマンドを使用して、インストールファイルを解凍し、解凍します。

   ```
   gunzip installationFilename.tar.gz 
   
       tar -xf installationFilename.tar
   ```

1. 展開済みのプログラムファイルを、次の表で指定されたディレクトリにコピーします。

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
   <td colname="col1"> aol_visual_sciences.so </td> 
   <td colname="col2"> コレクターのロードモジュール。 </td> 
   <td colname="col3"> <i>/usr/local/aolserver/ visual_sciences</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> トランスミッタープログラム。 </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor 設定ファイル。 </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中に Insight サーバーが提示する電子証明書を検証するために使用される証明書 </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestExperiment.xls という名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、アーキテクトが対照実験の設定に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensor が実行されているマシンにファイルをインストールする必要はありません（ただし、インストールすることは可能です）。 代わりに、アーキテクトがアクセスできる場所にファイルをコピーするか、必要に応じてインストールパッケージからファイルを抽出します。 対照実験の詳細については、『 Insight 対照実験ガイド』を参照してください。

**プログラムファイルに対する権限**

>[!NOTE]
>
>プログラムファイルに対する権限が正しくないと、Sensor のインストール時に発生する問題の大部分が発生します。 権限は、この節で説明したとおりに設定してください。
>
>デフォルトでは、tar ファイル内のプログラムファイルには次の権限があります。 システムの設定によっては、ファイルを抽出する際に、これらの設定が変更（マスクなし）される場合があります。 権限を推奨されるデフォルト設定にリセットするには、次の chmod コマンドを使用します。 ファイルをインストールしたディレクトリで、少なくともこのレベルのアクセスが許可されていることを確認します。

| ファイル | デフォルトの権限 | chmod コマンド |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-r— r— | chmod 664 |
| trust_ca_cert.pem | rw-r— r— | chmod 664 |

## センサー設定ファイルの編集 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

この [!DNL txlogd.conf] ファイルには、Sensor の設定パラメータが含まれています。

このファイルを編集して、ディスクキューファイルのサイズと場所、Insight サーバーのアドレス、このセンサーによって生成されるイベントデータに添付される ID を指定する必要があります。

設定ファイルには、必須のパラメーターとオプションのパラメーターが含まれています。

* **必須パラメーター** は、Sensor をインストールする際に指定する必要がある設定です。 これらの設定がないと、センサーは正常に動作しません。
* **オプションのパラメーター** は、事前定義済みの値（変更可能）をデフォルトにする設定またはオプション機能を有効にする設定です。

**Sensor 設定ファイルを編集するには**

* を開きます。 [!DNL /etc/txlogd.conf] ファイルを編集し、必要なパラメーターと必要なオプションパラメーターを設定します。
* ファイルを保存して閉じます。

**Sensor 設定ファイルを編集するには**

1. を開きます。 [!DNL /etc/txlogd.conf] ファイルを編集し、必要なパラメーターと必要なオプションパラメーターを設定します。
1. ファイルを保存して閉じます。

## トランスミッターを起動し、ディスクキューを作成します。 {#section-55630de65f264274aefd771da2002852}

txlogd.conf ファイルを設定した後、トランスミッタープログラムを起動し、Windows サービスとして登録し、ディスクキューを作成できます。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリに、コレクターモジュールとトランスミッタープログラムの両方に、ファイルへの読み取り/書き込みアクセス権が付与されていることを確認します。

   ディスクキューファイルに必要な権限の詳細については、「 Sensor UNIX File Permissions 」を参照してください。
1. センサーがインストールされているコンピューターで、次のコマンドを実行してトランスミッターを起動します。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、トランスミッターを「インタラクティブモード」で開始します。 このモードでは、トランスミッターメッセージを画面に表示し、キーボードコマンドを使用してトランスミッターを操作できます。
   * 「c」オプションは、トランスミッターにディスクキューを作成するよう指示します。
   * 「f」オプションは、設定ファイルの場所を指定します。

   トランスミッターの開始時に使用できるオプションの詳細については、センサートランスミッターのコマンドラインオプションを参照してください。

1. トランスミッターが、QueueFile パラメーターで指定された場所と、QueueSize パラメーターで指定されたサイズにディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl+C キーを押してトランスミッターを終了し、次の手順を実行します。

   1. txtlogd.conf ファイルを調べ、QueueFile および QueueSize パラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作し、QueueSize パラメータで指定されたサイズのファイルを保持するのに十分な空き容量があることを確認します。
   1. 必要な修正を加え、この手順を繰り返します。

## AOL サーバーにコレクターを追加します。 {#section-c5b83ae4ebce430aa764f951e849b333}

AOLServer の場合、コレクターは、Web サーバープロセスに読み込まれる動的共有オブジェクトです。

AOL サーバーにコレクターを追加するには、以下の説明に従って、サーバーの設定ファイルを編集し、AOL サーバーを再起動する必要があります。 通常、サーバーの設定ファイルの名前は nsd.tcl で、AOL サーバーがインストールされているディレクトリにあります。

1. テキストエディターで設定ファイルを開き、次のセクションを探します。

   ```
   ns_section "ns/server/${servername}/modules" 
   ```

1. 次の行を追加します。 ( を 1 つのステートメントとして追加します。 以下に示す単語の折り返しを無視する )。

   ```
   ns_param aol_visual_sciences /usr/local/aolserver/visual_sciences/aol_visual_sciences.so 
   ```

1. 次のように、新しいセクションを作成します。

   ```
   ns_section "ns/server/${servername}/module/aol_visual_sciences"
   ```

1. この新しいセクションに、次の行を追加します。

   ```
   ns_param    VisualSciencesConfig    /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >これらの行では大文字と小文字が区別されます。 上に表示されたとおりに入力します。

1. AOL サーバーを再起動します。 コレクターが読み込まれ、イベントデータの収集とディスクキューへの書き込みが開始されます。

## センサーをテストする {#section-0dae181ef8884f10a57f6cfda8500969}

コレクターがイベントデータを収集し、トランスミッターがターゲットの Insight サーバーに送信していることを確認します。

>[!NOTE]
>
>トランスミッターが Insight サーバーにイベントデータを正常に送信できることを確認するには、次のテストを開始する前に、ターゲット Insight サーバーがインストールされ、実行されていることを確認してください。

1. トランスミッターがまだ実行されていない場合は、次のコマンドを使用して再起動します。

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. （任意のマシン上で）ブラウザーを開き、センサーが動作している Web サーバーからページをリクエストします（センサーが監視しているページを必ず選択してください）。
1. リクエストを発行した後、トランスミッターのコンソールを調べて、イベントデータがターゲット Insight サーバーに送信されていることを示すメッセージを確認します。
1. センサーがデータを正常に送信しない場合は、次の点を確認します。

   * ターゲット Insight サーバーが実行中です。
   * txtlogd.conf で ServerAddress および ServerPort パラメーターが正しく設定されている。 サーバー名を使用して ServerAddress を指定した場合は、代わりに数値の IP アドレスを使用してみてください。
   * CertName パラメーターの値は、ターゲット Insight サーバーの電子証明書に表示される共通名と完全に一致します。

## システム起動スクリプトへのトランスミッターの追加 {#section-19a38f27c9f44adf88f8910f5ed483a3}

トランスミッターをシステム起動スクリプトに自動的に読み込む方法に関する情報です。

Web サーバーマシンの再起動時にトランスミッターが自動的に読み込まれるようにするには、次のコマンド（トランスミッターを起動する）をシステム起動スクリプトに追加します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、トランスミッターをデーモンとして起動します。 トランスミッターが生成するオペレーティングメッセージとエラーメッセージは、に書き込まれます [!DNL syslog].

デフォルトの Solaris 設定は 60 です。 Sensor で実施されたテストに基づき、各インスタンスに 3 つのセマフォを使用します。Adobeでは、1024 を設定として使用することをお勧めします。 この数値は、セマフォを必要とする可能性のあるサーバー上の他のアプリケーションと共に Sensor が機能するのに十分な高さですが、パフォーマンスには影響しません。 この勧告を支持するため、Adrian Cockcroft は彼の著書 Sun Performance and Tuning （Prentice Hall, 1994 年 10 月）で以下の内容を述べています。「データベースは、多くの共有メモリとセマフォの設定を使う傾向があります。 これらはパフォーマンスに影響を与えません。十分大きい限り、プログラムは動くだろう」
