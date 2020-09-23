---
description: 通常、Insightとレポートのユーザーが処理し、アクセスできるようにするデータ量が、クラスターの現在の設定の容量を超える場合は、InsightサーバーDPUを既存のクラスターに追加します。
solution: Analytics
title: 既存のクラスターへの Insight サーバー DPU の追加
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---


# 既存のクラスターへの Insight サーバー DPU の追加{#adding-an-insight-server-dpu-to-an-existing-cluster}

通常、Insightとレポートのユーザーが処理し、アクセスできるようにするデータ量が、クラスターの現在の設定の容量を超える場合は、InsightサーバーDPUを既存のクラスターに追加します。

## マスターサーバーの設定ファイルの更新 {#section-7c9a23754a994d73b722d53f999f0e82}

で、マスター [!DNL Insight](通常は [!DNL Server Files Manager] FSU) [!DNL Insight Server][!DNL Insight Server] のを開き、クラスターに追加する各DPUに対して次の操作を行います。

1. マスター上のアドレスファイルを編集し、新しいDPUの名前とアドレス [!DNL Insight Server] を含めます(「アドレスファイルへの処理インサイトサーバーの [追加](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)」を参照)。 クラスターの追加現在のグループに対する新しいDPUの名前とアドレスが表示さ [!DNL Insight Servers] れます。

1. マスター上のアクセス制御ファイルを編集し、新しいDPUのIPアドレス [!DNL Insight Server] が含まれるようにします。詳しくは、クラスター用のアクセス制御ファイルの [更新の説明に従ってください](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)。

## 新しいInsightサーバーDPUのインストール {#section-8ce9a5957db24f94b3a3250caaccc7ba}

このタスクはWindows 32ビットにのみ適用されます。

1. クラスター内の現在のDPUの1つから新しいDPUに次のディレクトリをコピーします。

   * [!DNL Insight Server] installation directory/bin/
   * [!DNL Insight Server] installation directory/Certificates/
   * [!DNL Insight Server] installation directory/Components/

1. デジタル証明書の [ダウンロードとインストールの説明に従って、新しいDPU用のデジタル証明書をダウンロードしてインストールします](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 新しいDPUでWindowsのメモリ使用率パラメーターを設定します。
1. 新しいDPUマシン [!DNL Insight Server] にWindowsサービスとして登録します(「Insight ServerをWindowsサービスとして [登録する](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)」を参照)。

1. トレースログを確認し、DPUがマスターと同期されていることを確認し [!DNL Insight Server]ます。
1. クラスターに追加するDPUごとに、手順1 ～ 6を繰り返します。

## データセットプロファイルの処理サーバーへの新しいInsightサーバーDPUの追加 {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

新しいDPUが、クラスター内の他のDPUと同じデータセットを処理する場合は、プロファイル.cfgでの処理サーバーの [!DNL profile.cfg] 指定の説明に従って、新しいDPUの共通名 [!DNL Insight Server] をマスター上の [ファイルに追加します](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)。
