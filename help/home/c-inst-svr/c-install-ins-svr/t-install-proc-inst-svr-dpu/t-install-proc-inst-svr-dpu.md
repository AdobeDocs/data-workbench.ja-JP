---
description: InsightサーバーDPUをインストールし、管理用に設定する手順について詳しく説明します。
title: Insight サーバー DPU のインストール手順
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
exl-id: 0bdfb598-d7eb-4e49-8d9b-4f362c3a62e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Insight サーバー DPU のインストール手順{#installation-procedures-for-an-insight-server-dpu}

InsightサーバーDPUをインストールし、管理用に設定する手順について詳しく説明します。

[!DNL Insight Server] DPUをインストールして設定するには、次のタスクを順に実行する必要があります。

1. [!DNL Insight Server]プログラムファイルをインストールします。 「[Insightサーバープログラムファイルのインストール](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)」を参照してください。
1. [!DNL Insight Server]電子証明書をダウンロードしてインストールします。 [電子証明書のダウンロードとインストール](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)を参照してください。
1. [!DNL Communications.cfg]ファイルのポート設定を確認します。 [ポート設定の確認](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)を参照してください。
1. [!DNL Access Control.cfg]ファイルを変更し、[!DNL Insight]から[!DNL Insight Server]への管理アクセスを許可します。 [アクセス制御ファイルの更新](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)を参照してください。
1. [!DNL server.address]ファイルを変更して、サーバーのネットワークの場所を定義します。 [サーバのネットワーク位置の定義](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)を参照してください。
1. （オプション）[!DNL Disk Files.cfg]ファイルを変更して、処理されたデータの保存場所を指定します。 [データセット(temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)の場所の設定を参照してください。
1. プロファイルと参照ファイルをインストールします。 [プロファイルと参照ファイルのインストール](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc)を参照してください。
1. Microsoft Windowsのメモリ使用率のパラメータを設定します。
1. [!DNL Insight Server]をWindowsサービスとして登録します。 [WindowsサービスとしてのInsightサーバーの登録](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)を参照してください。
