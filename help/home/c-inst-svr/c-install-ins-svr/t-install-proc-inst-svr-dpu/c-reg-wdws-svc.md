---
description: Microsoft Windowsサービスとして開始インサイトサーバーを同時に登録する手順です。
title: Windows サービスとしての Insight サーバーの登録
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 8%

---

# Windows サービスとしての Insight サーバーの登録{#registering-insight-server-as-a-windows-service}

Microsoft Windowsサービスとして開始インサイトサーバーを同時に登録する手順です。

>[!NOTE]
>
>[!DNL Insight Server] を初めて起動すると、デジタル証明書を登録するために、Adobe License Server に自動的に接続されます。登録プロセスを正常に完了するには、次の手順を実行する際に、コンピューターがインターネットに接続されている必要があります。

**開始 [!DNL Insight Server] してWindowsサービスとして登録するには**

1. コマンドプロンプトを開き、[!DNL Insight Server]をインストールしたフォルダー内のbinサブディレクトリに移動します。

   例：[!DNL C:\Adobe\Server\bin]

1. コマンドプロンプトで、開始[!DNL Insight Server]に対して次のコマンドを実行し、同時にMicrosoft Windowsのサービスとして実行するように登録します。

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. [!DNL Insight Server]が正しく実行されていることを確認するには、**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**&#x200B;をクリックします。 このコマンドの順序は、使用しているWindowsのバージョンによって異なります。

   1. サービスリストで、**[!DNL Adobe Insight Server]**&#x200B;のエントリを探し、ステータスが「開始」で、起動タイプが「自動」であることを確認します。
   1. [サービス]コントロールパネルを閉じます。

1. 開始のアップ中に[!DNL Insight Server]でエラーが発生したかどうかを確認するには、**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**&#x200B;をクリックします。 このコマンドの順序は、使用しているWindowsのバージョンによって異なります。

   1. [!DNL Event Viewer]ウィンドウの左ペインで、**[!UICONTROL Application]**&#x200B;ログを選択します。
   1. 右側のウィンドウで、[!DNL Source]列に「Adobe」が含まれているイベントを探します。
   1. 「Adobe」からエラーが見つかった場合は、重複を押しながらエラーをクリックして[!DNL Event Properties]ウィンドウを表示します。 このウィンドウには、エラーに関する詳細情報が表示されます。

1. [!DNL Applications]ログの調査が終了したら、イベントビューアを閉じます。

[!DNL Insight Server]のインストールが完了しました。 [!DNL Insight Server] は、連続的に実行するように設計されています。マシンを再起動すると、[!DNL Insight Server]が自動的に再起動します。 [!DNL Insight Server]を手動で開始して停止する必要がある場合は、Windowsの[サービス]コントロールパネルを使用して実行できます。 次の節で説明するように、[!DNL Insight Server]サービスを設定して、定期的に自動的に再起動することもできます。

## 自動的に再起動するサービスの設定{#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] は、中断なく実行を続けるように設計されています。通常、停止または開始されるのは、ソフトウェアのアップグレードや証明書の変更など、まれなタスクを実行する場合、または特定のシステムエラーがイベントした場合のみです。 [!DNL Insight Server]サービスは、通常のシステム操作中に停止または再起動する必要はありません。ただし、定期的に（毎日、毎週、毎月）サービスを再開するように設定すると、例えば、イベントメッセージを消去できます。

**サー [!DNL Insight Server] ビスが自動的に再起動されるように設定するには**

1. [!DNL Insight Server]をインストールしたディレクトリの[!DNL Components]フォルダーに移動します。

   例：[!DNL C:\Adobe\Server\Components]

1. メモ帳などのテキストエディターを使用して、[!DNL ScheduledRestart.cfg]という名前の新しいファイルを作成します。
1. [!DNL ScheduledRestart.cfg]ファイルに次のテキストを入力します。

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> この値の場合… </th> 
      <th colname="col2" class="entry">   </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>Month DD , YYYY HH :MM :SS TZone</i> </td> 
      <td colname="col2"> <p><span class="keyword"> Insight Server </span>を初めて再起動する時間です。 </p> <p>例：August 13, 2013 22:30:00 EST </p> <p> <p>注意： タイムゾーンを指定する必要があります。 タイムゾーンを指定しない場合、デフォルトではシステム時間に設定されません。 夏時間などの時計シフトポリシーを実装する場合は、適切なルールを含む<span class="filepath"> .dst </span>ファイルをBase\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span>マシンに保存する必要があります。 サポートされているタイムゾーンの略称と夏時間の導入に関するリストについては、<a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211">タイムゾーンコード</a>を参照してください。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequency</i> </td> 
      <td colname="col2"> <p>次のいずれかの値です。 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">month </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">週間 </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">日 </li> 
       </ul> </p> <p>「開始時間」で指定した初期時間の後に<span class="keyword"> Insight Server </span>を再起動する頻度を指定します。 </p> <p>例えば、<span class="keyword"> Insight Server </span>を週に1回再起動する場合は、この値を「week」に設定します。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. [!DNL ScheduledRestart.cfg]ファイルを保存します。

   [!DNL ScheduledRestart.cfg]ファイルが、[!DNL Insight Server]をインストールしたディレクトリの[!DNL Components]フォルダーにあることを確認します。
