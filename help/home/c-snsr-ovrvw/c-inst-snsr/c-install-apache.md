---
description: Apache Server 2.0.40、2.0.42 以降、Apache Server 2.2、または Apache Server 2.4 を Linux、Sun Solaris、FreeBSD のいずれかにインストールして設定する方法について説明します。
title: Apache サーバー 2.0.40、2.0.42 以降、および Apache サーバー 2.2 または 2.4（Linux、Solaris、FreeBSD のいずれか）
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
exl-id: d5b943be-e9ca-4601-88c7-bb2bfdc0d080
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1546'
ht-degree: 2%

---

# Apache サーバー 2.0.40、2.0.42 以降、および Apache サーバー 2.2 または 2.4（Linux、Solaris、FreeBSD のいずれか）{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

{{eol}}

Apache Server 2.0.40、2.0.42 以降、Apache Server 2.2、または Apache Server 2.4 を Linux、Sun Solaris、FreeBSD のいずれかにインストールして設定する方法について説明します。

Sensor のプログラムファイルは、インストールファイルにパッケージ化され、Adobeダウンロードサイトから入手できます。 ご使用の Web サーバー用の Sensor インストールファイルがまだない場合は、次の手順を開始する前に、そのファイルをダウンロード ( またはAdobe担当者から入手 ) してください。

Sensor をインストールして設定するには、次の大まかな手順を実行する必要があります。

次の Apache サーバーがサポートされています。

* RedHat Linux 7.x 以降、または Sun Solaris SPARC 2.6 以降で動作する Apache Server 2.0.40
* Apache Server 2.0.40、2.0.42 以降、Apache Server 2.2、Apache Server 2.4（Linux、Sun Solaris、FreeBSD のいずれか）
* RedHat Linux 7.x 以降、Sun Solaris SPARC 2.6 以降、SUSE Linux 9.x 以降、FreeBSD 5.3 以降で動作する Apache Server 2.0.42 以降
* 64 ビットバージョンの RedHat Linux ES 4 および ES 5 で動作する Apache Server 2.0.42 以降。
* RedHat Linux 7.x 以降または Sun Solaris SPARC 2.6 以降で動作する Apache Server 2.2
* RedHat Linux 7.x 以降、Sun Solaris x86_64、FreeBSD のいずれかで動作する Apache Server 2.4

>[!NOTE]
>
>Apache Server バージョン 2.0.40、2.0.42 以降（32 ビットと 64 ビット）、または 2.2 を実行する Web サーバーに Sensor をインストールする手順は同じですが（以下の手順で説明します）、各バージョンのインストールファイルは異なります。 Sensor をインストールする前に、実行中の Apache サーバーおよびオペレーティングシステムのバージョンに対して、正しいインストールファイルを受け取っていることを確認してください。

## プログラムファイルのインストール {#section-2f3e85083b4f4aa989a85997330e86ae}

Sensor のプログラムファイルを抽出してインストールする手順です。

1. root ユーザーまたは root 権限を持つユーザーとしてログオンします。
1. 次のコマンドを使用して、インストールファイルを解凍し、解凍します。

   * Linux の場合：

      ```
      tar -zxf installationFilename
      ```

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

   * Solaris の場合：

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
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> コレクターのロードモジュール。 </td> 
   <td colname="col3"> <i> IBMHttpServer/modules</i> </td> 
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

## Sametime サーバーでのログの有効化 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Sametime Server にログオンするための手順です。

1. Lotus Domino 管理者クライアントを使用して、Sametime を実行している Lotus Domino サーバーに接続します。
1. Lotus Domino 管理者で、「ファイル」タブをクリックし、「 Sametime Configuration - stconfig.nsf 」をダブルクリックして、Sametime 設定ファイルを開きます。
1. Sametime 設定ファイルで、コミュニティサービスフォームを開き、フォーム上の任意の場所をダブルクリックして編集モードに入ります。
1. チャットログフラグを&quot;strict&quot;に設定し、キャプチャサービスの種類を&quot;0x1000&quot;に設定します。
1. コミュニティサービスフォームを保存して閉じ、Sametime 設定ファイルを閉じます。
1. Sametime サーバーを再起動します。

## センサー設定ファイルの編集 {#section-de0eb4a646394b61abb6cd5a2b706de0}

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

## Web サーバーにコレクタを追加する {#section-c5b83ae4ebce430aa764f951e849b333}

IBM HTTP サーバーの場合、コレクターは、Web サーバープロセスに読み込む動的共有オブジェクトです。

Web サーバーにコレクターを追加するには、以下の説明に従って httpd.conf ファイルを編集し、Web サーバーを再起動する必要があります。

センサーがサーバーコンピューター上の複数の Web サーバーのデータをキャプチャする場合は、各 Web サーバーで次の手順を実行する必要があります。

1. テキストエディターを使用して、Sensor が取り込むイベントの Web サーバーの httpd.conf ファイルを開きます。
1. ファイルの末尾に次の 2 行を追加します。

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >これらの行では大文字と小文字が区別されます。 上に表示されたとおりに入力します。

1. Web サーバープロセスを再起動します（サーバーコンピューター全体を再起動する必要はありません。Web サーバープロセスを再起動するだけです）。 コレクタは Web サーバと共にロードされ、イベントデータの収集とディスクキューへの書き込みを開始します。

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

このコマンドは、トランスミッターをデーモンとして起動します。 トランスミッタが生成する動作およびエラーメッセージは、syslog に書き込まれます。
