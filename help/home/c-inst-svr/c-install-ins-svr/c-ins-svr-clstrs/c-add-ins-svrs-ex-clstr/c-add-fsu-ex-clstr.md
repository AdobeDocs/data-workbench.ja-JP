---
description: ソースデータを追加のファイルサーバーに保存する場合や、マスター Insight サーバーのバックアップを設定する場合は、既存のクラスターに Insight サーバー FSU を追加する必要があります。
title: 既存のクラスターへの Insight サーバー FSU の追加
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 既存のクラスターへの Insight サーバー FSU の追加{#adding-an-insight-server-fsu-to-an-existing-cluster}

{{eol}}

ソースデータを追加のファイルサーバーに保存する場合や、マスター Insight サーバーのバックアップを設定する場合は、既存のクラスターに Insight サーバー FSU を追加する必要があります。

次の手順で [!DNL Insight Server] 既存のクラスタに対して FSU を実行するには、次の手順を実行する必要があります。

1. [マスター・サーバの構成ファイルの更新](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [新しい Insight サーバー FSU のインストール](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [新しい Insight サーバー FSU の設定](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## マスター・サーバの構成ファイルの更新 {#section-b5f21f2edb35493da4475de2cdeefca1}

In [!DNL Insight]をクリックし、 [!DNL Server Files Manager] ご主人様に [!DNL Insight Server] ( 通常 [!DNL Insight Server] (FSU) を参照し、クラスターに追加する各 FSU に対して次の操作を実行します。

1. マスター上のアドレスファイルを編集します [!DNL Insight Server] 新しい FSU の名前とアドレスを含めるには、 [アドレスファイルへの処理 Insight サーバーの追加](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). 新しい FSU の名前とアドレスを、クラスターの現在のグループに追加します。 [!DNL Insight Servers] が表示されます。

1. マスター上のアクセス制御ファイルを編集します [!DNL Insight Server] 新しい FSU の IP アドレスを含めるには、 [クラスタのアクセス制御ファイルの更新](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## 新しい Insight サーバー FSU のインストール {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 現在の FSU で、 [!DNL Insight Server] インストールディレクトリを開き、新しい FSU にファイルをコピーします。
1. ファイルを、 [!DNL Insight Server] ソフトウェア
1. 新しい FSU 用の電子証明書をダウンロードしてインストールする ( [電子証明書のダウンロードとインストール](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. 新しい FSU で Windows のメモリ使用率パラメータを設定します。
1. 名前を変更 [!DNL .address] FSU の名前を反映したファイル ( [サーバーのネットワーク位置の定義](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. 新しい FSU のドライブ構造がプライマリ FSU のドライブ構造と異なる場合は、 [!DNL Disk Files.cfg] ファイル。

   1. を開きます。 [!DNL Disk Files.cfg] ファイルを新しい FSU 上に置く。
   1. プライマリ FSU のドライブと一致するように設定を更新します。詳しくは、 [データセットデータ容量の監視](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. ファイルをローカルとサーバーに保存します。

1. 登録 [!DNL Insight Server] 新しい FSU マシン上の Windows サービスとして ( [Windows サービスとしての Insight サーバーの登録](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. クラスタに追加する FSU ごとに、手順 1 ～ 6 を繰り返します。

## 新しい Insight サーバー FSU の設定 {#section-c39334c5bd754d5b98d41ad094333108}

次の手順では、特定の設定タスクの手順を説明します。 新しい FSU の実装に適した手順に従います。

**ソースデータストレージ用に FSU を設定するには**

新しい FSU にクラスター上で実行されているデータセットの追加のソースデータが格納されている場合は、 [!DNL Insight Server] の「ログ処理構成ファイル」章の「ファイル・サーバー・ユニット」 *データセット設定ガイド*.

**新しい FSU にマスターのバックアップを作成するには [!DNL Insight Server] FSU**

新しい FSU をマスターのバックアップにする場合 [!DNL Insight Server] （クラスタの FSU として機能）新しい（バックアップ）FSU 上の同期ファイルを変更して、マスター FSU と同期させる必要があります。

1. バックアップ時 [!DNL Insight Server] FSU、 [!DNL Server Files Manager] コピーする [!DNL Synchronize.cfg] ファイルを [!DNL Components for Processing Servers] フォルダーを [!DNL Components] フォルダー。

1. を開きます。 [!DNL Synchronize.cfg] ファイル ( [!DNL Components] ) [!DNL Insight].

1. Components ディレクトリの場所を指定する SynchronizeDir を探します。 「ディレクトリ」の下に複数の同期ディレクトリが表示される場合があるので、その多くの同期ディレクトリの内容を（サーバ番号をクリックして）表示して、目的のサーバを見つける必要がある場合があります。
1. 次の例に示すように、SynchronizeDir エントリを編集し、2 つ目の SynchronizeDir エントリを追加します。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 変更したファイルを次のような新しい名前で保存します。 [!DNL FSU_Synchronize.cfg] だから君はそれを混乱させないように [!DNL Synchronize.cfg] クラスター内の DPU 上のファイル。

1. 以下を使用： [!DNL Server Files Manager] をクリックして、名前を変更したファイルのローカルコピーをサーバに保存します。 バックアップ FSU は、識別されたディレクトリ内のファイルをマスターからダウンロードします [!DNL Insight Server] FSU を作成し、更新されたこれらのファイルのコピーをマスターから動的に取得 [!DNL Insight Server] FSU を変更します。
