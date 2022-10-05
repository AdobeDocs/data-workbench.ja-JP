---
description: Insight サーバー DPU をインストールし、管理用に設定する手順について詳しく説明します。
title: Insight サーバー DPU のインストール手順
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
exl-id: 0bdfb598-d7eb-4e49-8d9b-4f362c3a62e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Insight サーバー DPU のインストール手順{#installation-procedures-for-an-insight-server-dpu}

{{eol}}

Insight サーバー DPU をインストールし、管理用に設定する手順について詳しく説明します。

をインストールして設定するには、以下を実行します。 [!DNL Insight Server] DPU では、次のタスクを順に実行する必要があります。

1. のインストール [!DNL Insight Server] プログラムファイル。 詳しくは、 [Insight サーバープログラムファイルのインストール](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. をダウンロードしてインストールする [!DNL Insight Server] 電子証明書。 詳しくは、 [電子証明書のダウンロードとインストール](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. でポート設定を確認します。 [!DNL Communications.cfg] ファイル。 詳しくは、 [ポート設定の確認](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. を変更します。 [!DNL Access Control.cfg] ～への管理アクセスを許可するファイル [!DNL Insight Server] から [!DNL Insight]. 詳しくは、 [アクセス制御ファイルの更新](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. を変更します。 [!DNL server.address] ファイルを使用して、サーバーのネットワークの場所を定義します。 詳しくは、 [サーバーのネットワーク位置の定義](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. （オプション） [!DNL Disk Files.cfg] ファイル：処理済みデータの保存場所を指定します。 詳しくは、 [データセット (temp.db) の場所の設定](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. プロファイルと参照ファイルをインストールします。 詳しくは、 [プロファイルと参照ファイルのインストール](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Microsoft Windows のメモリ使用率パラメーターを設定します。
1. 登録 [!DNL Insight Server] を Windows サービスとして使用する。 詳しくは、 [Windows サービスとしての Insight サーバーの登録](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
