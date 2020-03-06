---
description: Repeaterで使用するInsightサーバーのFSUをインストールし、設定する手順です。
solution: Insight
title: Repeater用のInsightサーバーFSUの設定
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Repeater用のInsightサーバーFSUの設定{#configuring-an-insight-server-fsu-for-repeater}

Repeaterで使用するInsightサーバーのFSUをインストールし、設定する手順です。

次のタスクを順に実行します。 FSUをリピータサーバとして使用するために必要な例外や変更は、 [!DNL Insight Server] 各手順の後に記録されます。

1. 『Insightサーバーのイ [!DNL Insight Server] ンストール』の説明に従って、プ [ログラムファイルをインストールしま](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd)す。

   これらのファイルをインストールしたマシンはRepeaterを実行するのに使用されるので、インストールディレクトリにはなどのわかりやすい名前を付けると便利で [!DNL D:\Adobe\Repeater]す。

1. デジタル証明書 [!DNL Insight Server] のダウンロードとインスト [ールの説明に従って、デジタル証明書をインストールします](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。

   Adobe License Serverにログインした後、指定したリピーターコンピューターのサーバー共通名に一致する証明書名を必ず探します。

1. 「ポート設定の確認」の説明に従 [!DNL Communications.cfg] って、ファイル内の [ポート設定を確認します](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)。

   割り当てられたポート（ポートとSSLポート）が、同じマシン上で実行されている別のプロセスで使用されている場合は、ポート割り当てを未使用のペアに変更する必要があります。

1. 必要に応じて、このマシンで収集および保 [!DNL Sensor] 存するデータのログディレクトリを変更します。 手順については、「イベントデ [ータ領域の監視」を参照してくださ](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)い。
1. Updating [!DNL Access Control.cfg] the Access Control Fileの説明に従って、からの管理ア [!DNL Insight Server] クセスを許可するフ [!DNL Insight] ァイルを変更します [](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)。
1. サーバーの [!DNL server.address] ネットワークの場所の定義に従って、サーバーのネッ [トワークの場所を定義するファイルを変更します](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)。
1. Windowsのメモリ使用率パラメータを設定します。
1. 「Windowsサ [!DNL Insight Server] ービスとしてのInsight Serverの登 [録」の説明に従って、Windowsサービスとして登録します](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。
