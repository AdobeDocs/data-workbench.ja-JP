---
description: Windows Server 2000 以降で実行される Sensor for Sun Java System Application Server Standard Edition 7 のインストールと設定の手順。
title: Sun Java Server（Windows Server 2000 以降）
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
exl-id: 33f24073-8eff-4bf6-8f83-7a122d1505d8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Sun Java Server（Windows Server 2000 以降）{#sun-java-server-on-windows-server-or-later}

{{eol}}

Windows Server 2000 以降で実行される Sensor for Sun Java System Application Server Standard Edition 7 のインストールと設定の手順。

Sensor のプログラムファイルは、インストールファイルにパッケージ化され、Adobeダウンロードサイトから入手できます。 ご使用の Web サーバー用の Sensor インストールファイルがまだない場合は、次の手順を開始する前に、そのファイルをダウンロード ( またはAdobe担当者から入手 ) してください。

センサーは、RedHat Linux 7.x 以降または Sun Solaris SPARC 2.6 以降で稼働する次のサーバーをサポートしています。

Sensor をインストールして設定するには、次の手順を実行する必要があります。

## プログラムファイルのインストール {#section-2f3e85083b4f4aa989a85997330e86ae}

Sensor のプログラムファイルを抽出し、サーバにインストールする手順。

1. Netscape Enterprise、iPlanet、Sun ONE、または Sun Java System Server で、Sensor プログラムファイルをインストールするディレクトリを作成します。 ディスクキューはこのディレクトリに存在するので、選択したデバイスに必要なサイズのキューを保持するのに十分な空き容量があることを確認してください。

   ```
   C:\VisualSensor
   ```

1. 作成したディレクトリに、インストールファイルの内容を抽出します。 この手順の間、Sensor は以下のファイルをインストールします。

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

1. Windows の [ スタート ] メニューから、[ アクセサリ ] > [ コマンドプロンプト ] を選択します。
1. コマンドプロンプトウィンドウで、Sensor をインストールしたディレクトリに移動し、次のコマンドを実行します。

   ```
   txlog /regserver
   ```

   このコマンドは、トランスミッターを起動し、ディスクキューを作成し、Sensor を Windows サービスとして登録します。

1. トランスミッターが正しく実行されていることを確認するには、スタート/Campaign コントロールパネル/管理ツール/サービスをクリックします。 サービスリストで、Sensor のエントリを探し、そのステータスが「開始済み」で、起動タイプが「自動」であることを確認します。 次に、[ サービス ] コントロールパネルを閉じます。
1. 起動中にトランスミッターでエラーが発生したかどうかを確認するには、スタート/Campaign コントロールパネル/管理ツール/イベントビューアをクリックして、イベントビューアを開きます。

   1. [Event Viewer] ウィンドウの左ペインで、[Applications] ログを選択します。
   1. 右側のウィンドウで、「ソース」列に「Adobe」があるイベントを探します。
   1. 「Adobe」からエラーが見つかった場合は、そのエラーをダブルクリックして「イベントのプロパティ」ウィンドウを表示します。 このウィンドウには、エラーに関する詳細情報が表示されます。

1. アプリケーションログの調査が終了したら、イベントビューアを閉じます。
1. トランスミッターが Sensor プログラムファイルをインストールしたディレクトリにディスクキュー (Diskq2000.log) を作成し、txlogd.conf ファイルの QueueSize パラメーターで指定したサイズであることを確認します。

   キューが正しく作成されていない場合：

   1. txtlogd.conf ファイルを調べ、QueueSize パラメーターが正しく設定されていることを確認します。
   1. Sensor をインストールしたデバイスに、QueueSize パラメータで指定したサイズのファイルを保持するのに十分な空き容量があることを確認します。
   1. Windows のサービスコントロールパネルで、トランスミッターを停止します。
   1. キューファイルを削除します。
   1. センサーを Windows サービスとして再登録：Windows の [ スタート ] メニューから、[ アクセサリ ] > [ コマンドプロンプト ] を選択します。 コマンドプロンプトウィンドウで、Sensor をインストールしたディレクトリに移動し、次のコマンドを実行します。

      ```
      txlog /regserver
      ```

トランスミッターは、連続的に実行するように設計されています。 コンピューターを再起動すると、トランスミッターが自動的に再起動します。 トランスミッターを手動で起動および停止する必要がある場合は、Windows の [ サービス ] コントロールパネルを使用して実行できます。

## 起動スクリプトを変更する {#section-19a38f27c9f44adf88f8910f5ed483a3}

init.conf ファイル ( 例：C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf) の最後に次の行を追加します。

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

obj.conf ファイル (C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.confなど ) で、次の行を既存の `<Object name="default">` 行：

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```
