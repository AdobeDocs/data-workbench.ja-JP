---
description: Insight サーバー FSU をインストールしてリピーターで使用するように設定する手順です。
title: Insight サーバー FSU のリピーター用の設定
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# Insight サーバー FSU のリピーター用の設定{#configuring-an-insight-server-fsu-for-repeater}

{{eol}}

Insight サーバー FSU をインストールしてリピーターで使用するように設定する手順です。

次の作業を順に実行します。 次の操作を行うために必要な例外または変更 [!DNL Insight Server] FSU は、各ステップの後にリピータサーバとして使用できます。

1. のインストール [!DNL Insight Server] の説明に従ってプログラムファイルを [Insight サーバーのインストール](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   これらのファイルをインストールしたマシンはリピーターを実行するために使用されるので、インストールディレクトリに次のようなわかりやすい名前を付けると便利です。 [!DNL D:\Adobe\Repeater].

1. のインストール [!DNL Insight Server] の説明に従って、電子証明書 [電子証明書のダウンロードとインストール](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   Adobeライセンスサーバにログインした後、指定されたリピータマシンのサーバ共通名と一致する証明書名を必ず探してください。

1. でポート設定を確認します。 [!DNL Communications.cfg] の説明に従ってファイルを作成します。 [ポート設定の確認](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   割り当てられたポート（ポートと SSL ポート）が同じマシン上で実行されている別のプロセスで使用される場合は、ポート割り当てを未使用のペアに変更する必要があります。

1. 必要に応じて、 [!DNL Sensor] 収集してこのマシンに保存するデータ。 手順については、 [イベントデータ容量の監視](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. を変更します。 [!DNL Access Control.cfg] ～への管理アクセスを許可するファイル [!DNL Insight Server] から [!DNL Insight] の説明に従って、 [アクセス制御ファイルの更新](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. を変更します。 [!DNL server.address] ファイル： [サーバーのネットワーク位置の定義](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. Windows のメモリ使用率パラメータを設定します。
1. 登録 [!DNL Insight Server] as a Windows サービス ( [Windows サービスとしての Insight サーバーの登録](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
