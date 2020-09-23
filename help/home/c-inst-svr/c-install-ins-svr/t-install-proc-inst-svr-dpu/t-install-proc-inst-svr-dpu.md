---
description: InsightサーバーDPUをインストールし、管理用に設定する手順について詳しく説明します。
solution: Analytics
title: Insight サーバー DPU のインストール手順
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---


# Insight サーバー DPU のインストール手順{#installation-procedures-for-an-insight-server-dpu}

InsightサーバーDPUをインストールし、管理用に設定する手順について詳しく説明します。

DPUをインストールして設定するには、次の [!DNL Insight Server] タスクを順に実行する必要があります。

1. プログラムファイルをインストールし [!DNL Insight Server] ます。 See [Installing the Insight Server Program Files](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Download and install the [!DNL Insight Server] digital certificate. See [Downloading and Installing the Digital Certificates](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. ファイル内のポート設定を確認し [!DNL Communications.cfg] ます。 See [Checking the Port Settings](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. からの管理アクセスを許可する [!DNL Access Control.cfg] ファイルを変更 [!DNL Insight Server] し [!DNL Insight]ます。 See [Updating the Access Control File](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. サーバーのネットワークの場所を定義する [!DNL server.address] ファイルを変更します。 See [Defining the Server&#39;s Network Location](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. （オプション）処理済みデータの保存場所を指定するように [!DNL Disk Files.cfg] ファイルを変更します。 See [Configuring the Location of the Dataset (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. プロファイルと参照ファイルをインストールします。 See [Installing Profiles and Lookup Files](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Microsoft Windowsのメモリ使用率パラメータを設定します。
1. Windowsサービス [!DNL Insight Server] として登録します。 See [Registering Insight Server as a Windows Service](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
