---
description: Repeaterで使用するInsightサーバーのFSUをインストールして設定する手順です。
solution: Analytics
title: Insight サーバー FSU のリピーター用の設定
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---


# Insight サーバー FSU のリピーター用の設定{#configuring-an-insight-server-fsu-for-repeater}

Repeaterで使用するInsightサーバーのFSUをインストールして設定する手順です。

次のタスクを順番に実行します。 FSUをリピータサーバとして使用できるようにする必要がある例外または変更は、各ステップの後に記録されます。 [!DNL Insight Server]

1. 「Insightサーバーのインストール」の説明に従って、 [!DNL Insight Server] プログラムファイルを [インストールします](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd)。

   これらのファイルをインストールしたマシンはリピータを実行するのに使用されるので、インストールディレクトリには、のようなわかりやすい名前を付けると便利で [!DNL D:\Adobe\Repeater]す。

1. デジタル証明書の [!DNL Insight Server] ダウンロードとインストールの説明に従って、 [デジタル証明書をインストールします](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。

   Adobeライセンスサーバーにログインした後、指定されたリピーターマシンのサーバー共通名に一致する証明書名を必ず探してください。

1. 「ポート設定の [!DNL Communications.cfg] 確認 [](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)」の説明に従って、ファイル内のポート設定を確認します。

   割り当てられたポート（ポートとSSLポート）が、同じマシン上で実行されている別のプロセスで使用される場合は、ポートの割り当てを未使用のペアに変更する必要があります。

1. 必要に応じて、このマシンで収集および保存する [!DNL Sensor] データのログディレクトリを変更します。 手順については、「 [イベントデータ領域の監視](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)」を参照してください。
1. アクセス制御ファイルの [!DNL Access Control.cfg] 更新の説明に従って、からの管理者アクセスを許可す [!DNL Insight Server] るようにファイルを変更します [!DNL Insight][](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)。
1. サーバーのネットワーク [!DNL server.address] の場所の [](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)定義で定義したとおりに、サーバーのネットワークの場所を定義するようにファイルを変更します。
1. Windowsのメモリ使用率パラメータを設定します。
1. Windowsサービス [!DNL Insight Server] として登録します(「Insight ServerをWindowsサービスとして [登録する](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)」を参照)。
