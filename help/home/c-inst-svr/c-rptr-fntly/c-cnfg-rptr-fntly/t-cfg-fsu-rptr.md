---
description: Repeaterで使用するInsightサーバーのFSUをインストールして設定する手順です。
title: Insight サーバー FSU のリピーター用の設定
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# Insight サーバー FSU のリピーター用の設定{#configuring-an-insight-server-fsu-for-repeater}

Repeaterで使用するInsightサーバーのFSUをインストールして設定する手順です。

次のタスクを順番に実行します。 [!DNL Insight Server] FSUをリピータサーバとして使用できるようにするために必要な例外や変更は、各ステップの後に記録されます。

1. [Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd)のインストールの説明に従って、[!DNL Insight Server]プログラムファイルをインストールします。

   これらのファイルをインストールしたマシンはRepeaterを実行するのに使用されるので、インストールディレクトリに[!DNL D:\Adobe\Repeater]のようなわかりやすい名前を付けると便利です。

1. [デジタル証明書のダウンロードとインストール](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)の説明に従って、[!DNL Insight Server]デジタル証明書をインストールします。

   Adobeライセンスサーバーにログインした後、指定されたリピーターマシンのサーバー共通名に一致する証明書名を必ず探してください。

1. [ポート設定の確認](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)の説明に従って、[!DNL Communications.cfg]ファイルのポート設定を確認します。

   割り当てられたポート（ポートとSSLポート）が、同じマシン上で実行されている別のプロセスで使用される場合は、ポートの割り当てを未使用のペアに変更する必要があります。

1. 必要に応じて、[!DNL Sensor]データを収集してこのマシンに保存するログディレクトリを変更します。 手順については、「[イベントデータスペースの監視](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)」を参照してください。
1. [アクセス制御ファイルの更新](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)の説明に従って、[!DNL Insight]から[!DNL Insight Server]への管理アクセスを許可するように[!DNL Access Control.cfg]ファイルを変更します。
1. [!DNL server.address]ファイルを変更して、[サーバーのネットワークの場所の定義](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)で定義したとおりに、サーバーのネットワークの場所を定義します。
1. Windowsのメモリ使用率パラメータを設定します。
1. [WindowsサービスとしてのInsight Serverの登録](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)の説明に従い、[!DNL Insight Server]をWindowsサービスとして登録します。
