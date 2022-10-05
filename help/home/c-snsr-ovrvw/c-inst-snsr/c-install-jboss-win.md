---
description: Microsoft Windows Server 2000 以降で実行する JBoss Server 4.0.5 以降用のセンサーのインストールと設定に関する詳細な手順。
title: JBoss サーバー（Windows Server 2000 以降）
uuid: b0501749-9479-484b-8876-fe3001825f8d
exl-id: d9001bc4-f3ef-4d26-9190-807194d20ada
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 2%

---

# JBoss サーバー（Windows Server 2000 以降）{#jboss-server-on-windows-server-or-later}

{{eol}}

Microsoft Windows Server 2000 以降で実行する JBoss Server 4.0.5 以降用のセンサーのインストールと設定に関する詳細な手順。

Sensor のプログラムファイルは、インストールファイルにパッケージ化され、Adobeダウンロードサイトから入手できます。 ご使用の Web サーバー用の Sensor インストールファイルがまだない場合は、次の手順を開始する前に、そのファイルをダウンロード ( またはAdobe担当者から入手 ) してください。

サポートされる J2EE 実装には、以下が含まれます。

* Microsoft Windows Server 2000 以降で動作する JBoss Server 4.0.5 以降

Sensor をインストールして設定するには、次の手順を実行する必要があります。

## プログラムファイルのインストール {#section-2f3e85083b4f4aa989a85997330e86ae}

Sensor のプログラムファイルを抽出してインストールする手順です。

1. JBoss サーバー上で、Sensor プログラムファイルをインストールするディレクトリを作成します。 ディスクキューはこのディレクトリに存在するので、選択したデバイスに必要なサイズのキューを保持するのに十分な空き容量があることを確認してください。

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
>インストールパッケージには、 [!DNL TestExperiment.xls]. このスプレッドシートは、アーキテクトが対照実験の設定に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensor が実行されているマシンにファイルをインストールする必要はありません（ただし、インストールすることは可能です）。 代わりに、アーキテクトがアクセスできる場所にファイルをコピーするか、必要に応じてインストールパッケージからファイルを抽出します。 対照実験の詳細については、『 Insight 対照実験ガイド』を参照してください。

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

1. トランスミッターが正しく実行されていることを確認するには、スタート/Campaign コントロールパネル/管理ツール/サービスをクリックします。

   >[!NOTE]
   >
   >このコマンドの順序は、使用している Windows のバージョンによって異なる場合があります。

   1. サービスリストで、Sensor のエントリを探し、そのステータスが「開始済み」で、起動タイプが「自動」であることを確認します。
   1. [ サービス ] コントロールパネルを閉じます。

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

## Web サーバーにコレクタを追加する {#section-c5b83ae4ebce430aa764f951e849b333}

JBoss サーバーの場合、コレクターはサーブレットコンテナ内でフィルターとして動作します。

Web サーバーにコレクターを追加するには、 [!DNL web.xml] ファイルを開き、web アプリケーションを再起動します。

1. テキストエディターを使用して、 [!DNL web.xml] ファイルを作成します。
1. 以下を追加します。 `<filter>` および `<filter-mapping>` 記述子ファイルの要素。 /etc ディレクトリに txlogd.conf をインストールしなかった場合は、 `<param-value>` 要素：

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping> 
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping> 
   ```

   >[!NOTE]
   >
   >これらの行では大文字と小文字が区別されます。 上に表示されたとおりに入力します。

1. Web サーバープロセスを再起動します（サーバーコンピューター全体を再起動する必要はありません。Web サーバープロセスを再起動するだけです）。 コレクタは Web サーバと共にロードされ、イベントデータの収集とディスクキューへの書き込みを開始します。

## 起動スクリプトを変更する {#section-0dae181ef8884f10a57f6cfda8500969}

起動スクリプトを変更する前に、Windows 環境で JAVA_HOME 変数が定義されていることを確認します。

内 [!DNL run.bat] ファイル (C:\jboss-4.0.5.GA\bin\run.bat など ) に、JBoss サーバーの起動コマンドの直前の「echo」行の直前に、ファイルの末尾近くに次の行を追加します。

```
set JBOSS_CLASSPATH=%JBOSS_CLASSPATH%;C:\jboss-4.0.5.GA\server\default\lib\javax.servlet.jar;C:\VisualSciences\J2EECollector.jar 
set JAVA_OPTS=%JAVA_OPTS% -Djava.library.path=C:\VisualSciences
```

## 追加データのキャプチャ {#section-9483b663cbd0432daaca50c1089c7fca}

appendToLog() 機能を使用して、J2EE ベースの Web アプリケーションから追加の測定データを取り込むことができます。

1. データの取り込み元の.jsp ページの先頭に次のコードを追加します。

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %> 
   ```

1. collector オブジェクトの appendToLog() メソッドを使用して、要求された.jsp ページのクエリ文字列に必要な名前と値のペアを追加します。 次の例では、/index.jspページに対して要求された.jsp ページのクエリー文字列に&quot;A=1&quot;と&quot;B=2&quot;を追加します。

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html> 
   ```

   結果のリクエスト URI は/index.jsp?A=1&amp;B=2 です。

1. 追加のデータを取り込む.jsp ページごとに、この手順を繰り返します。
