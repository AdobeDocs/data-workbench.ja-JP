---
description: Microsoft Windows Server 2008以降で実行されているMicrosoft IIS 7.xまたは8.x用のSensorをインストールし、設定します。
title: Windows Server 2008以降でのMicrosoft IIS
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Server 2008以降でのMicrosoft IIS{#microsoft-iis-on-windows-server-or-later}

Microsoft Windows Server 2008以降で実行されているMicrosoft IIS 7.xまたは8.x用のSensorをインストールし、設定します。

Sensorのプログラムファイルは、アドビのダウンロードサイトから入手したインストールファイルにパッケージ化されます。 お使いのWebサーバー用のSensorインストールファイルがまだない場合は、次の手順を開始する前に、ダウンロード（またはアドビの担当者から入手）してください。

Sensorをインストールして設定するには、次の高レベルな手順を実行する必要があります。

1. [プログラムファイルのインストール](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [Sensor設定ファイルの編集](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [送信機を起動し、ディスク・キューを作成します。](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [Webサーバーにコレクターを追加します](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [追加データの取り込み](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## Install the program files {#section-cb51e5932a6d40c5b00758a7a51b7578}

Windows IISでSensorを実行する場合、プログラムファイルとディスクキューファイルは同じディレクトリに存在する必要があります。

プログラムファイルをインストールする前に、まずディスクキューを保守する場所を決めます。これは、プログラムファイルをインストールする必要があるからです。

次の手順を使用して、Sensorのプログラムファイルを抽出し、インストールします。

1. Windowsコンピューターで、Sensorプログラムファイルをインストールするディレクトリを作成します。 ディスクキューもこのディレクトリに存在するので、選択したデバイスに必要なサイズのキューを保持するのに十分な領域があることを確認してください。

   例：C:\VisualSensor

1. 作成したディレクトリにインストールファイルの内容を抽出します。 この手順で、Sensorは次のファイルをインストールします。

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> イベントビューアのメッセージ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> qlog.dll </td> 
   <td colname="col2"> コレクタモジュール（ISAPIフィルタ）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TestTest.xls </td> 
   <td colname="col2"> <p>設計者が制御実験の設定に使用できるExcelスプレッドシートファイル。 </p> <p>センサーはこのファイルを使用しません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書の検証に使用される証明書です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> 送信プログラム。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor設定ファイル。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestTest.xlsという名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、設計者が制御実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorを実行しているコンピューターにファイルをインストールする必要はありません（ただし、インストールは可能です）。 必要に応じて、設計者がアクセスできる場所にファイルをコピーするか、インストールパッケージからファイルを抽出します。 対照実験について詳しくは、『Insight Controlled Experiments Guide』を参照してください。

## Sensor設定ファイルの編集 {#section-1e1590a92222430e92066292512ae0df}

txlogd.confファイルには、Sensorの設定パラメーターが含まれています。

ファイルを編集して、特に、ディスクキューのサイズ、Insightサーバーのアドレス、およびこのセンサーで生成されるデータに添付されるIDを指定する必要があります。 設定ファイルには、必須パラメーターとオプションのパラメーターが含まれています。

* **必須パラメータ** ーは、Sensorのインストール時に指定する必要がある設定です。 これらの設定がないと、Sensorは正常に実行されません。
* **オプションのパラメータ** は、デフォルトで事前定義された値（変更可能）に設定される設定、またはオプション機能を有効にする設定です。

**Sensor設定ファイルを編集するには**

1. テキストエデ `<SensorDirectory>/txlogd.conf` ィターでファイルを開き、必要なパラメーターと必要なオプションのパラメーターを設定します。

   パラメーターの説 [!DNL txlogd.conf] 明については、 [Sensor Txlogd.conf File Parametersを参照してください](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed)。

1. ファイルを保存して閉じます。

## 送信機を起動し、ディスク・キューを作成します。 {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

ファイルを設定し [!DNL txlogd.conf]たら、送信プログラムを起動し、Windowsサービスとして登録し、ディスクキューを作成します。

1. Windowsのスタートメニューで、アクセサリ/コマンドプロンプトを選択します。
1. コマンドプロンプトウィンドウで、Sensorをインストールしたディレクトリに移動し、次のコマンドを実行します。

   ```
   txlog /regserver
   ```

   このコマンドは、トランスミッタを起動し、ディスクキューを作成し、SensorをWindowsサービスとして登録します。

1. 送信機が正しく動作していることを確認するには、スタート/コントロールパネル/管理ツール/サービスをクリックします。

   >[!NOTE]
   >
   >このコマンドの順序は、使用しているWindowsのバージョンによって異なる場合があります。

   1. サービスリストで、Sensorのエントリを探し、ステータスがStartedで、スタートアップの種類がAutomaticであることを確認します。
   1. [サービス]コントロールパネルを閉じます。

1. 起動中に送信機でエラーが発生したかどうかを確認するには、スタート/コントロールパネル/管理ツール/イベントビューアをクリックし、イベントビューアを開きます。

   >[!NOTE]
   >
   >このコマンドの順序は、使用しているWindowsのバージョンによって異なる場合があります。

   1. 「Event Viewer」ウィンドウの左ペインで、「Applications」ログを選択します。
   1. 右側のウィンドウで、「Source」列に「Adobe」が含まれているイベントを探します。
   1. 「アドビ」からエラーが見つかった場合は、エラーをダブルクリックして、イベントのプロパティウィンドウを表示します。 このウィンドウには、エラーに関する詳細情報が表示されます。

1. アプリケーションログの確認が完了したら、イベントビューアを閉じます。
1. 送信機が、Sensorプログラムファイルをインストールしたディレクトリにディスクキュー(Diskq2008.log)を作成し、txlogd.confファイルのQueueSizeパラメーターで指定したサイズであることを確認します。

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

## Webサーバーにコレクターを追加します {#section-088960c986cf449cb712152298b3518d}

IISの場合、コレクタはISAPIフィルタで、IISのWebサーバーに追加します。

1. スタート/管理ツール/インターネ **ットインフォメーションサービス(IIS)マネージャを使用して、IISマネージャを開きます**。
1. [ローカルコンピ **ュータ** ]ノードと[サ **イト** ]ノードを展開します。
1. Webサイトを選択し、右側のウィンドウで、「 **ISAPI Filters」をダブルクリックします**。
1. 「 **Actions** 」ペインで、「 **Add**」をクリックします。

1. 「フィルタ **ー名** 」フィールドに、フィルターの表示名を入力します。 推奨されるフィルター名は「Sensor」です。
1. 「 **Browse**」をクリックし、（Sensorをインストールしたディレクトリにある）qlog.dllファイルを選択し、「 **OK」をクリックします**。

1. 「 **OK** 」をクリックしてフィルタを追加します。

   フィルターを追加すると、コレクターはすぐに動作し、データを収集する準備が整います。

コレクターにトラフィックが流れた後に緑色の矢印が表示されない場合は、次の手順を実行します。

1. スタート/管理ツール/イベントビューアをクリックし、イベントビューアでエラーを確認します。

   >[!NOTE]
   >
   >このコマンドの順序は、使用しているWindowsのバージョンによって異なる場合があります。

1. 「Event Viewer」ウィンドウの左ペインで、「 **Application** log」を選択します。
1. 右側のウィンドウで、「Source **** 」列に「Adobe」が含まれているイベントを探します。
1. エラーが見つかった場合は、エラーをダブルクリックして「 **Event Properties** 」ウィンドウを表示します。

## 追加データの取り込み {#section-98db9625efdc4b60bfd76f7adf4af74d}

ウェブページは、多くの場合、ASP(Active Server Pages)プログラミング言語を使用して構造化されます。

ASPは、IIS内で動作するMicrosoftのテクノロジーです。 ブラウザがASPファイルを要求すると、IISはASPエンジンに要求を渡す。 ASPエンジンは、ASPファイルを1行ずつ読み取り、ファイル内のスクリプトを実行する。 最後に、ASPファイルはプレーンHTMLとしてブラウザに返されます。 ASPは、他の利用に加えて、HTMLフォームから送信されたユーザークエリやデータの応答、要求を可能にするRESPONDまたはREQUESTオブジェクトを提供します。

フォームに入力した値を、ユーザーのブラウザーのアドレスバーに表示されるURLや、HTMLコード自体で表示可能なURLに追加しない場合があります。 簡単なサーバーサイドASPスクリプトを使用すると、フォームフィールド名とそれぞれの値をログファイルに追加できます。ユーザーのブラウザー内で使用したり、HTMLファイルに埋め込んだりする必要はありません。 Webサイト内の特定のフォームに入力された実際のフォーム値を取り込むには、数行のコードを追加して、フォーム値をログ要求に追加する必要があります。

フォームの処理ページ内で、次のコードを含めて、入力したフォーム値を要求データに追加します（送信したフォーム値を外部データベースや他の場所に書き込むのに加えて）。

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

このプロセスでは、フォーム処理ページの要求データに定義されたフォーム値が追加されます。 ログデータ内で、後述のように、付加された値がフォーム処理ページのクエリ文字列として使用できます。 例えば、v_1、v_2、v_3、v_4は、適切なフォームフィールドに入力されたデータを含むクエリ文字列になります。 前の例で説明した構文は、取り込む追加のフォームフィールドと値に対して複製できます。

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

すべてのフォームフィールドと値を取得し、分析に使用する場合は、次の構文を使用できます。

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues);
```

次の例では、HTML内に存在するすべてのフォームフィールドとそれぞれの値を取り込み、それらをクエリ文字列としてフォーム処理ページのログエントリに追加します。 この場合、フォーム内に存在する非表示のフィールドが含まれることに注意してください。

ログデータは、次の表に示すように拡張されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | NAMEクエリ文字列に関連付けられた値 | v_1=John Smith |
| v_2 | CITYクエリ文字列に関連付けられた値 | v_2=ロサンゼルス |
| v_3 | STATEクエリ文字列に関連付けられた値 | v_3=カリフォルニア |
| v_4 | ZIPクエリ文字列に関連付けられた値 | v_4=90210 |

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->

