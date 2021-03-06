---
description: 通常は、処理し、InsightとReportのユーザーがアクセスできるようにするデータ量が、クラスターの現在の設定の容量を超えた場合に、InsightサーバーのDPUを既存のクラスターに追加します。
title: 既存のクラスターへの Insight サーバー DPU の追加
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# 既存のクラスターへの Insight サーバー DPU の追加{#adding-an-insight-server-dpu-to-an-existing-cluster}

通常は、処理し、InsightとReportのユーザーがアクセスできるようにするデータ量が、クラスターの現在の設定の容量を超えた場合に、InsightサーバーのDPUを既存のクラスターに追加します。

## マスター・サーバの構成ファイルの更新{#section-7c9a23754a994d73b722d53f999f0e82}

[!DNL Insight]で、マスター[!DNL Insight Server]（通常は[!DNL Insight Server] FSU）の[!DNL Server Files Manager]を開き、クラスターに追加する各DPUに対して次の操作を実行します。

1. [アドレスファイル](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)への処理インサイトサーバーの追加の説明に従って、マスター[!DNL Insight Server]のアドレスファイルを編集し、新しいDPUの名前とアドレスを含めます。 新しいDPUの名前とアドレスを、クラスターの現在の[!DNL Insight Servers]が表示されているグループに追加します。

1. マスター[!DNL Insight Server]上のアクセス制御ファイルを編集し、[クラスターのアクセス制御ファイルの更新](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)の説明に従って、新しいDPUのIPアドレスを含めます。

## 新しいInsightサーバーDPUのインストール{#section-8ce9a5957db24f94b3a3250caaccc7ba}

この作業はWindows 32ビットにのみ適用されます。

1. クラスター内の現在のDPUの1つから新しいDPUに次のディレクトリをコピーします。

   * [!DNL Insight Server] installation directory/bin/
   * [!DNL Insight Server] installation directory/Certificates/
   * [!DNL Insight Server] installation directory/Components/

1. [電子証明書のダウンロードとインストール](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)の説明に従って、新しいDPU用の電子証明書をダウンロードしてインストールします。
1. 新しいDPUでWindowsのメモリ使用率パラメータを設定します。
1. [WindowsサービスとしてのInsightサーバーの登録](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)の説明に従って、[!DNL Insight Server]を新しいDPUマシンにWindowsサービスとして登録します。

1. トレースログを調べ、DPUがマスター[!DNL Insight Server]に同期されていることを確認します。
1. クラスターに追加するDPUごとに、手順1 ～ 6を繰り返します。

## データセットプロファイルの処理サーバーへの新しいInsightサーバーDPUの追加{#section-cdc6c3913b9f4010b5e17cc7ec85e849}

新しいDPUがクラスター内の他のDPUと同じデータセットを処理する場合は、[Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)での処理サーバーの指定の説明に従って、マスター[!DNL Insight Server]上の[!DNL profile.cfg]ファイルに新しいDPUの共通名を追加します。
