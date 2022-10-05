---
description: Insight サーバーを起動し、Microsoft Windows サービスとして同時に登録する手順です。
title: Windows サービスとしての Insight サーバーの登録
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 6%

---

# Windows サービスとしての Insight サーバーの登録{#registering-insight-server-as-a-windows-service}

{{eol}}

Insight サーバーを起動し、Microsoft Windows サービスとして同時に登録する手順です。

>[!NOTE]
>
>[!DNL Insight Server] を初めて起動すると、デジタル証明書を登録するために、Adobe License Server に自動的に接続されます。登録プロセスを正常に完了するには、次の手順を実行する際に、コンピューターがインターネットに接続されている必要があります。

**開始するには [!DNL Insight Server] Windows サービスとして登録します。**

1. コマンドプロンプトを開き、をインストールしたフォルダー内の bin サブディレクトリに移動します。 [!DNL Insight Server].

   例：[!DNL C:\Adobe\Server\bin]

1. コマンドプロンプトで、次のコマンドを実行してを起動します。 [!DNL Insight Server] 同時に登録して、Microsoft Windows でサービスとして実行します。

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. 次の手順で確認します。 [!DNL Insight Server] が正しく実行されている場合は、「 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. このコマンドの順序は、使用している Windows のバージョンによって異なる場合があります。

   1. サービスリストで、 **[!DNL Adobe Insight Server]** 「開始済み」で、起動タイプが「自動」であることを確認します。
   1. [ サービス ] コントロールパネルを閉じます。

1. 次の手順で、 [!DNL Insight Server] 起動時にエラーが発生した場合は、「 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. このコマンドの順序は、使用している Windows のバージョンによって異なる場合があります。

   1. の左側のペイン [!DNL Event Viewer] ウィンドウで、 **[!UICONTROL Application]** ログ。
   1. 右側のウィンドウで、「Adobe」が [!DNL Source] 列。
   1. 「Adobe」からエラーが見つかった場合は、エラーをダブルクリックして [!DNL Event Properties] ウィンドウ このウィンドウには、エラーに関する詳細情報が表示されます。

1. あなたが [!DNL Applications] ログを開き、イベント・ビューアを閉じます。

のインストールが完了しました [!DNL Insight Server]. [!DNL Insight Server] は、継続的に実行するように設計されています。 マシンを再起動した場合、 [!DNL Insight Server] が自動的に再起動します。 を起動および停止する必要がある場合 [!DNL Insight Server] 手動で、Windows の [ サービス ] コントロールパネルを使用して設定できます。 次の節で説明するように、必要に応じてを設定できます。 [!DNL Insight Server] 定期的に自動的に再起動するサービス。

## 自動的に再起動するサービスの設定 {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] は、中断せずに実行を続けるように設計されています。 通常、ソフトウェアのアップグレードや証明書の変更など、まれなタスクを実行する場合や、特定のシステムエラーが発生した場合にのみ、停止または開始されます。 を停止または再起動する必要はありません。 [!DNL Insight Server] 通常のシステム運用中のサービスただし、定期的に（日別、週別、月別など）再起動するように、例えば、イベントメッセージを消去するようにサービスを設定できます。

**次の手順で [!DNL Insight Server] 自動的に再起動するサービス**

1. 次に移動： [!DNL Components] をインストールしたディレクトリ内のフォルダー [!DNL Insight Server].

   例：[!DNL C:\Adobe\Server\Components]

1. メモ帳などのテキストエディターを使用して、という名前の新しいファイルを作成します。 [!DNL ScheduledRestart.cfg].
1. 次のテキストを [!DNL ScheduledRestart.cfg] ファイル：

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
      <td colname="col1"> <i>Month DD, YYYY HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>必要な時間 <span class="keyword"> Insight サーバー </span> を初めて再起動する場合。 </p> <p>例：2013 年 8 月 14 日 22:30:00 EST </p> <p> <p>注意：タイムゾーンを指定する必要があります。 指定しない場合、タイムゾーンはデフォルトではシステム時間に設定されません。 夏時間などの時計シフティングを実装する場合は、 <span class="filepath"> .dst </span> ファイル内の <span class="keyword"> Insight サーバー </span> マシン。 サポートされるタイムゾーンの略語と夏時間の導入に関する情報については、 <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> タイムゾーンのコード </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>頻度</i> </td> 
      <td colname="col2"> <p>次のいずれかの値です。 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">month </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">週間 </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">日 </li> 
       </ul> </p> <p>頻度を指定するには <span class="keyword"> Insight サーバー </span> を、Start Time で指定した初期時間の後に再開します。 </p> <p>例えば、 <span class="keyword"> Insight サーバー </span> 週に 1 回再起動する場合は、この値を「week」に設定します。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 保存する [!DNL ScheduledRestart.cfg] ファイル。

   を確認します。 [!DNL ScheduledRestart.cfg] ファイルが [!DNL Components] をインストールしたディレクトリ内のフォルダー [!DNL Insight Server].
