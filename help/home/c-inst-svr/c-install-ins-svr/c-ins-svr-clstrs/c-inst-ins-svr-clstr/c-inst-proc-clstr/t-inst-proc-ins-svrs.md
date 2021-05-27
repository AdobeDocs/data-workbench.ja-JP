---
description: 処理Insightサーバーは、コンポーネントディレクトリのコンテンツを除いて、マスターInsightサーバーと同じです。
title: 処理 Insight サーバーのインストールと設定
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# 処理 Insight サーバーのインストールと設定{#installing-and-configuring-the-processing-insight-servers}

処理Insightサーバーは、コンポーネントディレクトリのコンテンツを除いて、マスターInsightサーバーと同じです。

処理[!DNL Insight Server]のComponentsディレクトリには、[!DNL Insight Servers]を処理するために特別に設定されたファイルのセットが含まれます。 これらのファイルは、マスター[!DNL Insight Server]上のComponents for Processing Serversディレクトリから派生します。

[!DNL Insight Server]処理をインストールする場合は、次の手順を実行してComponentsディレクトリを設定します。

1. 処理[!DNL Insight Server]上の元のComponentsディレクトリを削除します。
1. 「処理サーバーのコンポーネント」ディレクトリの名前を「コンポーネント」に変更します。
1. Componentsディレクトリの[!DNL Synchronize.cfg]を変更して、マスター[!DNL Insight Server]を指すようにします。

**処理をインストールして設定するには[!DNL Insight Server]**

1. [Insightサーバープログラムファイルのインストール](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)の説明に従って、[!DNL Insight Server]プログラムファイルをインストールします。 マスター[!DNL Insight Server]で使用されたディレクトリ構造を必ず複製してください。 例えば、[!DNL Insight Server]がマスター[!DNL Insight Server]の[!DNL C:\Adobe\Server]にインストールされている場合は、[!DNL Insight Servers]上の[!DNL C:\Adobe\Server]にもインストールする必要があります。
1. この特定の処理用にAdobeが発行した電子証明書をインストールします[!DNL Insight Server]。 手順については、[電子証明書のダウンロードとインストール](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)を参照してください。
1. Windowsエクスプローラーを使用して、処理[!DNL Insight Server]で次の操作を実行します。

   1. **[!UICONTROL Components]**&#x200B;フォルダーを削除します。
   1. [!DNL Components for Processing Servers]フォルダーの名前をComponentsに変更します。

1. メモ帳などのテキストエディターを使用して、処理[!DNL Insight Server]のComponentsディレクトリにある[!DNL Synchronize.cfg]ファイルを開きます。
1. 次のファイルフラグメントに示すように、このファイルの2行目にマスター（プライマリ）[!DNL Insight Server]のIPアドレスを追加します。 このファイル内の他の要素は編集しないでください。

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
1. [WindowsサービスとしてのInsightサーバーの登録](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)の説明に従って、[!DNL Insight Server]を起動します。

   これで、[!DNL Insight Server]クラスターのインストールが完了しました。 次に、次の節の説明に従って、クラスターで実行するデータセットプロファイルを設定します。
