---
description: 通常、処理し、Insightとレポートのユーザーがアクセスできるデータ量が、クラスターの現在の設定の容量を超えた場合に、InsightサーバーDPUを既存のクラスターに追加します。
solution: Insight
title: 既存のクラスターへのInsightサーバーDPUの追加
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 既存のクラスターへのInsightサーバーDPUの追加{#adding-an-insight-server-dpu-to-an-existing-cluster}

通常、処理し、Insightとレポートのユーザーがアクセスできるデータ量が、クラスターの現在の設定の容量を超えた場合に、InsightサーバーDPUを既存のクラスターに追加します。

## マスター・サーバ上の構成ファイルの更新 {#section-7c9a23754a994d73b722d53f999f0e82}

で、マ [!DNL Insight]スター [!DNL Server Files Manager] (通常は [!DNL Insight Server][!DNL Insight Server] FSU)のを開き、クラスターに追加する各DPUに対して次の手順を実行します。

1. マスター上のアドレスファイルを編集し、新 [!DNL Insight Server] しいDPUの名前とアドレスを含めます。詳しくは、処理インサイトサーバー [のアドレスファイルへの追加を参照してください](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)。 新しいDPUの名前とアドレスを、クラスターの現在のグループが表示されているグループに追 [!DNL Insight Servers] 加します。

1. マスター上のアクセス制御ファイルを編集し、新 [!DNL Insight Server] しいDPUのIPアドレスを含めます(「クラスターのア [クセス制御ファイルの更新」を参照)](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)。

## 新しいInsightサーバーDPUのインストール {#section-8ce9a5957db24f94b3a3250caaccc7ba}

このタスクは、Windows 32 bitにのみ適用されます。

1. クラスター内の現在のDPUの1つから新しいDPUに次のディレクトリをコピーします。

   * [!DNL Insight Server] installation directory/bin/
   * [!DNL Insight Server] installation directory/Certificates/
   * [!DNL Insight Server] installation directory/Components/

1. 新しいDPU用のデジタル証明書をダウンロードし、「デジタル証明書のダウンロードとイ [ンストール」の説明に従ってインストールします](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 新しいDPUでWindowsのメモリ使用率パラメーターを設定します。
1. 新しいDPU [!DNL Insight Server] マシンでWindowsサービスとして登録します(「Windowsサービスとし [てのInsight Serverの登録」を参照](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540))。

1. トレースログを確認し、DPUがマスターと同期していることを確認しま [!DNL Insight Server]す。
1. クラスターに追加するDPUごとに、手順1 ～ 6を繰り返します。

## データセットプロファイルの処理サーバーへの新しいInsightサーバーDPUの追加 {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

新しいDPUがクラスター内の他のDPUと同じデータセットを処理する場合は、Profile.cfgでの処理サーバーの指定の説明に従って、新しいDPUの共通名をマスター上のファ [!DNL profile.cfg] イ [!DNL Insight Server] ルに追加します [](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)。
