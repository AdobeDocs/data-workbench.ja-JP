---
description: 処理するInsightサーバーは、Componentsディレクトリの内容を除いて、マスターInsightサーバーと同じです。
solution: Insight
title: 処理インサイトサーバーのインストールと設定
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 処理インサイトサーバーのインストールと設定{#installing-and-configuring-the-processing-insight-servers}

処理するInsightサーバーは、Componentsディレクトリの内容を除いて、マスターInsightサーバーと同じです。

処理のComponentsディレクトリには、処理用 [!DNL Insight Server] に特別に設定されたファイルの特殊なセットが含まれていま [!DNL Insight Servers]す。 これらのファイルは、マスター上のComponents for Processing Serversディレクトリから取得されま [!DNL Insight Server]す。

処理をインストールする場 [!DNL Insight Server]合は、次の手順を実行してComponentsディレクトリを設定します。

1. 処理の元のComponentsディレクトリを削除しま [!DNL Insight Server]す。
1. 「Components for Processing Servers」ディレクトリの名前を「Components」に変更します。
1. Componentsディレクトリ [!DNL Synchronize.cfg] 内のを変更して、マスターを指すようにしま [!DNL Insight Server]す。

**処理をインストールして設定するには[!DNL Insight Server]**

1. 『Insightサーバープ [!DNL Insight Server] ログラムファイルのインスト [ール』の説明に従って、プログラムファイルをインストールしま](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)す。 マスターで使用されたディレクトリ構造を必ず複製してくださ [!DNL Insight Server]い。 例えば、がマスタ [!DNL Insight Server] ー上にインスト [!DNL C:\Adobe\Server] ールされてい [!DNL Insight Server]る場合は、処理上にもインスト [!DNL C:\Adobe\Server] ールする必要が [!DNL Insight Servers] あります。
1. この特定の処理用にアドビが発行したデジタル証明書をインストールしま [!DNL Insight Server]す。 手順につい [ては、デジタル証明書のダウンロードとインストール](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) （英語のみ）を参照してください。
1. Windowsエクスプローラーを使用して、処理で次の操作を行いま [!DNL Insight Server]す。

   1. Delete the **[!UICONTROL Components]** folder.
   1. フォルダーの名前を「 [!DNL Components for Processing Servers] Components」に変更します。

1. メモ帳などのテキストエディターを使用して、処理のComponents [!DNL Synchronize.cfg] ディレクトリにあるファイルを開きま [!DNL Insight Server]す。
1. 次のファイルフラグメントに示すように、マ [!DNL Insight Server] スター（プライマリ）のIPアドレスをこのファイルの2行目に追加します。 このファイル内の他の項目は編集しないでください。

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. ファイルを保存します。
1. 「Windowsサービスと [!DNL Insight Server] してのInsight Server [の登録」の説明に従って、を起動します](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。

   これで、クラスターのインストールが完了し [!DNL Insight Server] ました。 次に、次の節の説明に従って、クラスター上で実行するデータセットプロファイルを設定します。

