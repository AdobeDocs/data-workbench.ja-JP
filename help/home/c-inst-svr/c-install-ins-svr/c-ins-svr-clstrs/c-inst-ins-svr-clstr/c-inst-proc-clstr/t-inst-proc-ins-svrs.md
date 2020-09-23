---
description: 処理Insightサーバーは、Componentsディレクトリの内容を除いて、マスターInsightサーバーと同じです。
solution: Analytics
title: 処理 Insight サーバーのインストールと設定
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---


# 処理 Insight サーバーのインストールと設定{#installing-and-configuring-the-processing-insight-servers}

処理Insightサーバーは、Componentsディレクトリの内容を除いて、マスターInsightサーバーと同じです。

処理のComponentsディレクトリには、処理用に特別に設定され [!DNL Insight Server] たファイルの特殊なセットが含まれ [!DNL Insight Servers]ます。 これらのファイルは、マスター上のComponents for Processing Serversディレクトリから生成され [!DNL Insight Server]ます。

処理をインストールする場合 [!DNL Insight Server]は、次の手順を実行してComponentsディレクトリを設定します。

1. 処理の元のComponentsディレクトリを削除し [!DNL Insight Server]ます。
1. Components for Processing Serversディレクトリの名前をComponentsに変更します。
1. Componentsディレクトリ [!DNL Synchronize.cfg] のを変更して、マスターを指すようにし [!DNL Insight Server]ます。

**処理をインストールして設定するには[!DNL Insight Server]**

1. Insightサーバー [!DNL Insight Server] プログラムファイルのインストールの説明に従って、プログラムファイルを [インストールします](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)。 マスターで使用したディレクトリ構造を重複してくだ [!DNL Insight Server]さい。 例えば、をマスターにインストール [!DNL Insight Server] した場合は、を処理 [!DNL C:\Adobe\Server] にもインストールする必要があ [!DNL Insight Server][!DNL C:\Adobe\Server][!DNL Insight Servers] ります。
1. この特定の処理に対してAdobeが発行したデジタル証明書をインストール [!DNL Insight Server]します。 手順については、「デジタル証明書の [ダウンロードとインストール](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) 」を参照してください。
1. Windowsエクスプローラを使用して、処理で次の操作を行いま [!DNL Insight Server]す。

   1. Delete the **[!UICONTROL Components]** folder.
   1. フォルダーの名前を「Components」に変更し [!DNL Components for Processing Servers] ます。

1. メモ帳などのテキストエディターを使用して、処理のComponentsディレクトリにある [!DNL Synchronize.cfg] ファイルを開き [!DNL Insight Server]ます。
1. 次の追加ファイルフラグメントに示すように、このファイルの2行目 [!DNL Insight Server] のマスター（プライマリ）のIPアドレス。 このファイル内の他の項目は編集しないでください。

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
1. 「Insight ServerをWindowsサービス [!DNL Insight Server] として [登録する」の説明に従って、を開始します](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。

   これで、 [!DNL Insight Server] クラスターのインストールが完了しました。 次に、次の節の説明に従って、クラスター上で実行するデータセットプロファイルを設定します。

