---
description: Insight Serverを起動し、Microsoft Windowsサービスとして同時に登録する手順です。
solution: Insight
title: Insight ServerをWindowsサービスとして登録する
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Insight ServerをWindowsサービスとして登録する{#registering-insight-server-as-a-windows-service}

Insight Serverを起動し、Microsoft Windowsサービスとして同時に登録する手順です。

>[!NOTE]
>
>[!DNL Insight Server] を初めて起動すると、デジタル証明書を登録するために、Adobe License Server に自動的に接続されます。登録プロセスを正常に完了するには、次の手順を実行する際に、コンピューターがインターネットに接続されている必要があります。

**Windowsサービスを[!DNL Insight Server]開始して登録するには**

1. コマンドプロンプトを開き、をインストールしたフォルダー内のbinサブディレクトリに移動しま [!DNL Insight Server]す。

   例：[!DNL C:\Adobe\Server\bin]

1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windows [!DNL Insight Server] でサービスとして実行するように起動し、同時に登録します。

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. が正しく実行され [!DNL Insight Server] ていることを確認するには、/// **[!UICONTROL Start]** をク **[!UICONTROL Control Panel]** リック **[!UICONTROL Administrative Tools]** しま **[!UICONTROL Services]**&#x200B;す。 このコマンドの順序は、使用しているWindowsのバージョンによって異なります。

   1. サービスリストで、のエントリを見つけ、そのエ **[!DNL Adobe Insight Server]** ントリのステータスが「開始」で、スタートアップの種類が「自動」であることを確認します。
   1. [サービス]コントロールパネルを閉じます。

1. 起動時にエラー [!DNL Insight Server] が発生したかどうかを確認するには、///をク **[!UICONTROL Start]** リッ **[!UICONTROL Control Panel]** クし **[!UICONTROL Administrative Tools]** ます **[!UICONTROL Event Viewer]**。 このコマンドの順序は、使用しているWindowsのバージョンによって異なります。

   1. ウィンドウの左側のペイン [!DNL Event Viewer] で、ログを選択し **[!UICONTROL Application]** ます。
   1. 右側のウィンドウで、列に「Adobe」が含まれているイベントを探し [!DNL Source] ます。
   1. 「アドビ」からエラーが見つかった場合は、エラーをダブルクリックしてウィンドウを表示し [!DNL Event Properties] ます。 このウィンドウには、エラーに関する詳細情報が表示されます。

1. ログの確認が完了したら、イ [!DNL Applications] ベントビューアを閉じます。

のインストールが完了しまし [!DNL Insight Server]た。 [!DNL Insight Server] は、連続的に実行するように設計されています。 コンピューターを再起動すると、が自動的に再 [!DNL Insight Server] 起動します。 手動で起動および停止する必要があ [!DNL Insight Server] る場合は、Windowsの[サービス]コントロールパネルを使用して実行できます。 次の節で説明するように、サービスを定期的に自動的に再起動するよ [!DNL Insight Server] うにオプションで設定できます。

## 自動的に再起動するサービスの設定 {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] は、中断なしで実行を続けるように設計されています。 通常、停止または開始されるのは、ソフトウェアのアップグレードや証明書の変更など、まれなタスクを実行する場合、または特定のシステムエラーが発生した場合に限られます。 通常のシステム操作中に、サービスを停止または再 [!DNL Insight Server] 開する必要はありません。ただし、定期的に（毎日、毎週、または毎月）サービスを再起動して、例えばイベントメッセージを消去するように設定できます。

**サービスが自動的に再起[!DNL Insight Server]動されるように設定するには**

1. インストールしたデ [!DNL Components] ィレクトリ内のフォルダに移動しま [!DNL Insight Server]す。

   例：[!DNL C:\Adobe\Server\Components]

1. メモ帳などのテキストエディターを使用して、という名前の新しいファイルを作成しま [!DNL ScheduledRestart.cfg]す。
1. ファイルに次のテキストを入力 [!DNL ScheduledRestart.cfg] します。

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> この値の場合… </th> 
      <th colname="col2" class="entry">     </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>Month DD , YYYY HH :MM :SS TZone</i> </td> 
      <td colname="col2"> <p>Insightサーバーを初 <span class="keyword"> めて </span> 再起動する時間です。 </p> <p>例：August 13, 2013 22:30:00 EST </p> <p> <p>注意： タイムゾーンを指定する必要があります。 タイムゾーンを指定しない場合、デフォルトではシステム時間が設定されません。 If you wish to implement Daylight Saving Time or a similar clock-shifting policy, you must save the <span class="filepath"> .dst </span> file containing the appropriate rules in the Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span> machine. サポートされるタイムゾーンの省略形の一覧と、夏時間の導入に関する情報については、タイムゾーンコードを参 <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> 照してくださ </a>い。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequency</i> </td> 
      <td colname="col2"> <p>次のいずれかの値です。 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">か月 </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">週間 </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">day </li> 
       </ul> </p> <p>「開始時間」で指定した初期時間 <span class="keyword"> 後にInsightサ </span> ーバーを再起動する頻度を指定します。 </p> <p>例えば、 <span class="keyword"> Insightサーバーを週に1 </span> 回再起動する場合、この値を「week」に設定します。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Save the [!DNL ScheduledRestart.cfg] file.

   ファイルが、イ [!DNL ScheduledRestart.cfg] ンストール先のディレ [!DNL Components] クトリ内のフォルダにあることを確認しま [!DNL Insight Server]す。
