---
description: 処理 Insight サーバーは、Components ディレクトリのコンテンツを除いて、マスター Insight サーバーと同じです。
title: 処理 Insight サーバーのインストールと設定
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# 処理 Insight サーバーのインストールと設定{#installing-and-configuring-the-processing-insight-servers}

{{eol}}

処理 Insight サーバーは、Components ディレクトリのコンテンツを除いて、マスター Insight サーバーと同じです。

処理の Components ディレクトリ [!DNL Insight Server] には、処理用に特別に設定されたファイルの特別なセットが含まれます [!DNL Insight Servers]. これらのファイルは、マスター上の Components for Processing Servers ディレクトリから派生します [!DNL Insight Server].

処理をインストールする場合 [!DNL Insight Server]を使用する場合は、次の手順を実行して Components ディレクトリを設定します。

1. 処理時に元の Components ディレクトリを削除 [!DNL Insight Server].
1. 「処理サーバーのコンポーネント」ディレクトリの名前を「コンポーネント」に変更します。
1. を変更します。 [!DNL Synchronize.cfg] Components ディレクトリ内で、マスターを指すようにします。 [!DNL Insight Server].

**処理をインストールして設定するには[!DNL Insight Server]**

1. のインストール [!DNL Insight Server] の説明に従ってプログラムファイルを [Insight サーバープログラムファイルのインストール](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). マスターで使用されていたディレクトリ構造を必ず複製してください [!DNL Insight Server]. 例えば、 [!DNL Insight Server] が [!DNL C:\Adobe\Server] 主人に [!DNL Insight Server]にインストールする必要があります。 [!DNL C:\Adobe\Server] 処理中 [!DNL Insight Servers] 同様に。
1. この特定の処理用にAdobeが発行した電子証明書をインストールします [!DNL Insight Server]. 詳しくは、 [電子証明書のダウンロードとインストール](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) 」を参照してください。
1. Windows エクスプローラーを使用して、処理で次の操作を行います [!DNL Insight Server]:

   1. を削除します。 **[!UICONTROL Components]** フォルダー。
   1. 名前を変更 [!DNL Components for Processing Servers] フォルダーからコンポーネントへ。

1. メモ帳などのテキストエディターを使用して、 [!DNL Synchronize.cfg] ファイルを作成します。 [!DNL Insight Server].
1. マスター（プライマリ）の IP アドレスを追加する [!DNL Insight Server] をこのファイルの 2 行目に追加します（次のファイルフラグメントで示します）。 このファイル内の他の項目は編集しないでください。

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
1. を開始します。 [!DNL Insight Server] の説明に従って、 [Windows サービスとしての Insight サーバーの登録](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   これで、のインストールが完了しました [!DNL Insight Server] クラスター。 次に、次の節で説明するように、クラスター上で実行するデータセットプロファイルを設定します。
