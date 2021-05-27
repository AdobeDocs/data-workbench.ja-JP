---
description: ソースデータを追加のファイルサーバーに保存する場合や、マスターInsightサーバーのバックアップを設定する場合は、InsightサーバーのFSUを既存のクラスターに追加できます。
title: 既存のクラスターへの Insight サーバー FSU の追加
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 既存のクラスターへの Insight サーバー FSU の追加{#adding-an-insight-server-fsu-to-an-existing-cluster}

ソースデータを追加のファイルサーバーに保存する場合や、マスターInsightサーバーのバックアップを設定する場合は、InsightサーバーのFSUを既存のクラスターに追加できます。

[!DNL Insight Server] FSUを既存のクラスターに追加するには、次の手順を実行する必要があります。

1. [マスター・サーバの構成ファイルの更新](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [新しいInsightサーバーFSUのインストール](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [新しいInsightサーバーFSUの設定](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## マスター・サーバの構成ファイルの更新{#section-b5f21f2edb35493da4475de2cdeefca1}

[!DNL Insight]で、マスター[!DNL Insight Server]（通常は[!DNL Insight Server] FSU）の[!DNL Server Files Manager]を開き、クラスターに追加する各FSUに対して次の操作を実行します。

1. [アドレスファイル](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)への処理インサイトサーバーの追加の説明に従って、マスター[!DNL Insight Server]のアドレスファイルを編集し、新しいFSUの名前とアドレスを含めます。 新しいFSUの名前とアドレスを、クラスターの現在の[!DNL Insight Servers]が表示されているグループに追加します。

1. マスター[!DNL Insight Server]上のアクセス制御ファイルを編集し、[クラスターのアクセス制御ファイルの更新](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)の説明に従って、新しいFSUのIPアドレスを含めます。

## 新しいInsightサーバーFSUのインストール{#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 現在のFSUで、[!DNL Insight Server]インストールディレクトリのzipファイルを作成し、新しいFSUにファイルをコピーします。
1. [!DNL Insight Server]ソフトウェアを配置する場所にファイルを解凍します。
1. [電子証明書のダウンロードとインストール](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)の説明に従って、新しいFSU用の電子証明書をダウンロードしてインストールします。
1. 新しいFSUでWindowsのメモリ使用率パラメータを設定します。
1. [サーバーのネットワーク位置の定義](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)の説明に従って、FSUの名前を反映するように[!DNL .address]ファイルの名前を変更します。

1. 新しいFSUのドライブ構造がプライマリFSUのドライブ構造と異なる場合は、[!DNL Disk Files.cfg]ファイルを編集する必要があります。

   1. 新しいFSUの[!DNL Disk Files.cfg]ファイルを開きます。
   1. [データセットデータ空間の監視](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03)の説明に従って、プライマリFSUのドライブと一致するように設定を更新します。
   1. ファイルをローカルに、またはサーバーに保存します。

1. [WindowsサービスとしてのInsightサーバーの登録](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)の説明に従って、[!DNL Insight Server]を新しいFSUマシンにWindowsサービスとして登録します。

1. クラスターに追加するFSUごとに、手順1 ～ 6を繰り返します。

## 新しいInsightサーバーFSUの設定{#section-c39334c5bd754d5b98d41ad094333108}

以下の手順は、特定の設定タスクの手順を示しています。 新しいFSUの実装に適した手順に従います。

**ソースデータストレージ用にFSUを設定するには**

新しいFSUにクラスターで実行するデータセットの追加のソースデータが格納されている場合は、『*データセット設定ガイド*』の「ログ処理設定ファイル」の章にある「[!DNL Insight Server]ファイルサーバーユニットの設定」で説明されているファイルサーバー設定プロセスを完了する必要があります。

**新しいFSUにマスターFSUのバックアップを作成する [!DNL Insight Server] には**

新しいFSUをマスター[!DNL Insight Server]のバックアップにする場合は（クラスターのFSUとして機能）、新しい（バックアップ）FSUの同期ファイルを変更して、マスターFSUと同期する必要があります。

1. バックアップ[!DNL Insight Server] FSUで、[!DNL Server Files Manager]を使用して[!DNL Components for Processing Servers]フォルダー内の[!DNL Synchronize.cfg]ファイルを[!DNL Components]フォルダーにコピーします。

1. [!DNL Insight]の[!DNL Synchronize.cfg]ファイル（[!DNL Components]フォルダー内）を開きます。

1. Componentsディレクトリの場所を指定するSynchronizeDirを探します。 「ディレクトリ」の下には複数の同期ディレクトリが表示される場合があります。そのため、目的のサーバを見つけるには、その中の多くのディレクトリの内容を（サーバ番号をクリックして）表示する必要がある場合があります。
1. 次の例に示すように、 SynchronizeDirエントリを編集し、2つ目のSynchronizeDirエントリを追加します。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 変更したファイルを新しい名前（[!DNL FSU_Synchronize.cfg]など）で保存し、クラスター内のDPU上の[!DNL Synchronize.cfg]ファイルと混同しないようにします。

1. [!DNL Server Files Manager]を使用して、名前を変更したファイルのローカルコピーをサーバーに保存します。 バックアップFSUは、識別されたディレクトリ内のファイルをマスタ[!DNL Insight Server] FSUからダウンロードし、これらのファイルの更新されたコピーをマスタ[!DNL Insight Server] FSUから変更時に動的に検索します。
