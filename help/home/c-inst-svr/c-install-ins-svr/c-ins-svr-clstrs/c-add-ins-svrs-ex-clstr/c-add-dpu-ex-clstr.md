---
description: 通常は、処理し、Insight とレポートのユーザーがアクセスできるデータの量が、クラスターの現在の設定の容量を超えた場合に、Insight サーバー DPU を既存のクラスターに追加します。
title: 既存のクラスターへの Insight サーバー DPU の追加
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# 既存のクラスターへの Insight サーバー DPU の追加{#adding-an-insight-server-dpu-to-an-existing-cluster}

{{eol}}

通常は、処理し、Insight とレポートのユーザーがアクセスできるデータの量が、クラスターの現在の設定の容量を超えた場合に、Insight サーバー DPU を既存のクラスターに追加します。

## マスター・サーバの構成ファイルの更新 {#section-7c9a23754a994d73b722d53f999f0e82}

In [!DNL Insight]をクリックし、 [!DNL Server Files Manager] ご主人様に [!DNL Insight Server] ( 通常 [!DNL Insight Server] FSU) を実行し、クラスターに追加する各 DPU に対して次の操作を実行します。

1. マスター上のアドレスファイルを編集します [!DNL Insight Server] 新しい DPU の名前とアドレスを含めるには、 [アドレスファイルへの処理 Insight サーバーの追加](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). 新しい DPU の名前とアドレスを、クラスターの現在のグループに追加します。 [!DNL Insight Servers] が表示されます。

1. マスター上のアクセス制御ファイルを編集します [!DNL Insight Server] 新しい DPU の IP アドレスを含めるには、 [クラスタのアクセス制御ファイルの更新](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## 新しい Insight サーバー DPU のインストール {#section-8ce9a5957db24f94b3a3250caaccc7ba}

この作業は、Windows 32 ビットにのみ適用されます。

1. クラスター内の現在の DPU の 1 つから新しい DPU に次のディレクトリをコピーします。

   * [!DNL Insight Server] installation directory/bin/
   * [!DNL Insight Server] installation directory/Certificates/
   * [!DNL Insight Server] installation directory/Components/

1. 新しい DPU 用の電子証明書をダウンロードしてインストールする方法については、 [電子証明書のダウンロードとインストール](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. 新しい DPU で Windows のメモリ使用率パラメータを設定します。
1. 登録 [!DNL Insight Server] 新しい DPU マシン上の Windows サービスとして ( [Windows サービスとしての Insight サーバーの登録](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. トレースログをチェックして、DPU がマスターに同期されていることを確認します [!DNL Insight Server].
1. クラスタに追加する DPU ごとに、手順 1 ～ 6 を繰り返します。

## データセットプロファイルの処理サーバーへの新しい Insight サーバー DPU の追加 {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

新しい DPU がクラスター内の他の DPU と同じデータセットを処理する場合は、新しい DPU の共通名を [!DNL profile.cfg] マスター上のファイル [!DNL Insight Server] の説明に従って、 [Profile.cfg での処理サーバーの指定](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
