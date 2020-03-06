---
description: InsightサーバーDPUをインストールし、管理用に設定する手順を詳しく説明します。
solution: Insight
title: InsightサーバーDPUのインストール手順
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# InsightサーバーDPUのインストール手順{#installation-procedures-for-an-insight-server-dpu}

InsightサーバーDPUをインストールし、管理用に設定する手順を詳しく説明します。

DPUをインストールして設定す [!DNL Insight Server] るには、次のタスクを順に実行する必要があります。

1. プログラムファイル [!DNL Insight Server] をインストールします。 詳しくは、 [Insightサーバープログラムファイルのインストールを参照してくださ](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)い。
1. Download and install the [!DNL Insight Server] digital certificate. デジタル証 [明書のダウンロードとインストールを参照してください](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. ファイル内のポート設定を確認 [!DNL Communications.cfg] します。 「ポー [ト設定の確認](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)」を参照
1. ファイルを変 [!DNL Access Control.cfg] 更して、からの管理アクセスを許可 [!DNL Insight Server] しま [!DNL Insight]す。 Updating the [Access Control Fileを参照してください](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)。
1. ファイルを変 [!DNL server.address] 更して、サーバーのネットワークの場所を定義します。 「サー [バのネットワークの場所の定義」を参照してください](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)。
1. （オプション）処理済みのデ [!DNL Disk Files.cfg] ータが保存される場所を指定するようにファイルを変更します。 詳し [くは、データセットの場所の設定(temp.db)を参照してください](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)。
1. プロファイルと参照ファイルをインストールします。 詳しくは、プ [ロファイルと参照ファイルのインストールを参照してくださ](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc)い。
1. Microsoft Windowsのメモリ使用率のパラメータを設定します。
1. Windowsサー [!DNL Insight Server] ビスとして登録します。 詳しくは、 [Insight ServerをWindowsサービスとして登録するを参照してください](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。
