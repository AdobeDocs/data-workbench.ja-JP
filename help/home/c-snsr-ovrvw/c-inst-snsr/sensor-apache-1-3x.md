---
description: RedHat Linux 7.x 以降、SUSE Linux 9.x 以降、Sun Solaris SPARC 2.6 以降、Sun Solaris x86 9 以降、FreeBSD 4 以降、Mac OS X PowerPC 上に Sensor をインストールして設定する手順の詳細。
title: Apache サーバー 1.3.x（Linux、Sun Solaris、FreeBSD、Mac OS X のいずれか）
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---

# Apache サーバー 1.3.x（Linux、Sun Solaris、FreeBSD、Mac OS X のいずれか）{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

{{eol}}

RedHat Linux 7.x 以降、SUSE Linux 9.x 以降、Sun Solaris SPARC 2.6 以降、Sun Solaris x86 9 以降、FreeBSD 4 以降、Mac OS X PowerPC 上に Sensor をインストールして設定する手順の詳細。

Sensor のプログラムファイルは、インストールファイルにパッケージ化され、Adobeダウンロードサイトから入手できます。 ご使用の Web サーバー用の Sensor インストールファイルがまだない場合は、次の手順を開始する前に、そのファイルをダウンロード ( またはAdobe担当者から入手 ) してください。

Sensor をインストールして設定するには、次の大まかな手順を実行する必要があります。

## プログラムファイルのインストール {#section-aae323e252394212bf4096d65fdd280c}

Sensor のプログラムファイルを抽出してサーバーマシンにインストールする手順。

1. root ユーザーまたは root 権限を持つユーザーとしてログオンします。
1. 次のコマンドを使用して、インストールファイルを解凍し、解凍します。

   * Linux の場合：

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * Solaris の場合：

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. 展開済みのプログラムファイルを、次の表で指定されたディレクトリにコピーします。

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
   <td colname="col2"> コレクターロードモジュール </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> 送信機プログラム </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor 設定ファイル </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中に Insight サーバーが提示する電子証明書を検証するために使用される証明書 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestExperiment.xls という名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、アーキテクトが対照実験の設定に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensor が実行されているマシンにファイルをインストールする必要はありません（ただし、インストールを選択することもできます）。 代わりに、アーキテクトがアクセスできる場所にファイルをコピーするか、必要に応じてインストールパッケージからファイルを抽出します。 対照実験の詳細については、『 Insight 対照実験ガイド』を参照してください。

**プログラムファイルに対する権限**

プログラムファイルに対する権限が正しくないと、Sensor のインストール時に発生する問題の大部分が発生します。

権限は、この節で説明したとおりに設定してください。

デフォルトでは、tar ファイル内のプログラムファイルには次の権限があります。 システムの設定によっては、ファイルを抽出する際に、これらの設定が変更（マスクなし）される場合があります。 権限を推奨されるデフォルト設定にリセットするには、次の chmod コマンドを使用します。 ファイルをインストールしたディレクトリで、少なくともこのレベルのアクセスが許可されていることを確認します。

| ファイル | デフォルトの権限 | chmod コマンド |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-rw-r-— | chmod 664 |
| trust_ca_cert.pem | rw-rw-r-— | chmod 664 |

## Sensor 設定ファイルを編集します。 {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

この [!DNL txlogd.conf] ファイルには、Sensor の設定パラメータが含まれています。

ファイルを編集して、ディスクキューのサイズ、Insight サーバーのアドレス、このセンサーによって生成されるデータに添付される ID を指定する必要があります。

設定ファイルには、必須のパラメーターとオプションのパラメーターが含まれています。

* 必須パラメータは、Sensor をインストールする際に指定する必要がある設定です。 これらの設定がないと、センサーは正常に動作しません。
* オプションのパラメーターは、事前定義済みの値（変更可能）をデフォルトにする設定またはオプション機能を有効にする設定です。

Sensor 設定ファイルを編集するには

1. /etc/txlogd.confファイルをテキストエディターで開き、必要なパラメーターと必要なオプションパラメーターを設定します。
1. ファイルを保存して閉じます。

## トランスミッターを起動し、ディスクキューを作成します。 {#section-a453d912ec3d47aa8e40ccacf527119d}

txlogd.conf ファイルを設定した後にディスクキューを作成する手順。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリに、コレクターモジュールとトランスミッタープログラムの両方に、ファイルへの読み取り/書き込みアクセス権が付与されていることを確認します。
1. センサーがインストールされているコンピューターで、次のコマンドを実行してトランスミッターを起動します。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、トランスミッターをインタラクティブモードで開始します。 このモードでは、トランスミッターメッセージを画面に表示し、キーボードコマンドを使用してトランスミッターを操作できます。
   * 「c」オプションは、トランスミッターにディスクキューを作成するよう指示します。
   * 「f」オプションは、設定ファイルの場所を指定します。

1. トランスミッターが、QueueFile パラメーターで指定された場所と、QueueSize パラメーターで指定されたサイズにディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl+C キーを押してトランスミッターを終了し、次の手順を実行します。

   1. txtlogd.conf ファイルを調べ、QueueFile および QueueSize パラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作し、QueueSize パラメータで指定されたサイズのファイルを保持するのに十分な空き容量があることを確認します。
   1. 必要な修正を加え、この手順を繰り返します。

## Web サーバーにコレクタを追加する {#section-a7fb6425956f4f518ae3a7db091b33d2}

Apache サーバーの場合、コレクターは、Web サーバープロセスに読み込む動的共有オブジェクトです。

Web サーバーにコレクターを追加するには、以下の説明に従って httpd.conf ファイルを編集し、Web サーバーを再起動する必要があります。

センサーがサーバーコンピューター上の複数の Web サーバーのデータをキャプチャする場合は、各 Web サーバーで次の手順を実行する必要があります。

1. テキストエディターを使用して、 [!DNL httpd.conf] ファイルを作成します。
1. ファイルの末尾に次の行を追加します。

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >これらの行では大文字と小文字が区別されます。 上に表示されたとおりに入力します。

1. Web サーバーを再起動します。 コレクターは Web サーバーと共に読み込まれ、イベントデータの収集とディスクキューへの書き込みを開始します。

## センサーをテストする {#section-83d9f60b39a6474f9c76bee3e19b2575}

トランスミッターを起動し、Insight サーバーに接続して、イベントデータを送信できることを確認します。

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
   * この [!DNL ServerAddress] および [!DNL ServerPort] パラメーターが [!DNL txtlogd.conf].

   * 指定した場合 [!DNL ServerAddress] サーバー名を使用し、代わりに数値 IP アドレスを使用してみてください。 の値 [!DNL CertName] パラメーターは、ターゲット Insight サーバーの電子証明書に表示される共通名と完全に一致します。

## システム起動スクリプトへのトランスミッターの追加 {#section-4e1ffa6e043941ab91411d91d596477a}

Web サーバーマシンを再起動したときに、トランスミッターが自動的に読み込まれるようにする情報です。

次のコマンド（トランスミッターを起動する）をシステム起動スクリプトに追加します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、トランスミッターをデーモンとして起動します。 トランスミッタが生成する動作およびエラーメッセージは、syslog に書き込まれます。

>[!NOTE]
>
>一部の Solaris ユーザーで、「mutex を取得できません」というエラーが発生する場合があります。 Sensor がこれらのシステムで正しく機能するには、次の行を/etc/system ファイルに追加または編集する必要があります。
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>デフォルトの Solaris 設定は 60 です。 Sensor で実施されたテストに基づき、各インスタンスに 3 つのセマフォを使用します。Adobeでは、1024 を設定として使用することをお勧めします。 この数値は、セマフォを必要とする可能性のあるサーバー上の他のアプリケーションと共に Sensor が機能するのに十分な高さですが、パフォーマンスには影響しません。 この勧告を支持するため、Adrian Cockcroft は彼の著書 Sun Performance and Tuning （Prentice Hall, 1994 年 10 月）で以下の内容を述べています。「データベースは、多くの共有メモリとセマフォの設定を使う傾向があります。 これらはパフォーマンスに影響を与えません。十分大きい限り、プログラムは動くだろう」
