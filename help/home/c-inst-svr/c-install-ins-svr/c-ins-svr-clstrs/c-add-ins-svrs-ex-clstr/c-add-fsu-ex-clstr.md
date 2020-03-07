---
description: 追加のファイルサーバーにソースデータを保存する場合や、マスターInsightサーバーのバックアップを設定する場合は、InsightサーバーのFSUを既存のクラスターに追加します。
solution: Insight
title: 既存のクラスターへのInsightサーバーFSUの追加
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 既存のクラスターへのInsightサーバーFSUの追加{#adding-an-insight-server-fsu-to-an-existing-cluster}

追加のファイルサーバーにソースデータを保存する場合や、マスターInsightサーバーのバックアップを設定する場合は、InsightサーバーのFSUを既存のクラスターに追加します。

FSUを既存のクラ [!DNL Insight Server] スターに追加するには、次の手順を実行する必要があります。

1. [マスター・サーバ上の構成ファイルの更新](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [新しいInsightサーバーFSUのインストール](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [新しいInsightサーバーFSUの設定](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## マスター・サーバ上の構成ファイルの更新 {#section-b5f21f2edb35493da4475de2cdeefca1}

で、マ [!DNL Insight]スタ [!DNL Server Files Manager] ー(通常は [!DNL Insight Server][!DNL Insight Server] FSU)のを開き、クラスターに追加する各FSUに対して次の手順を実行します。

1. マスター上のアドレスファイルを編集し、 [!DNL Insight Server] 新しいFSUの名前とアドレスを含めます(「アドレスファイルへの処 [理インサイトサーバーの追加」を参照)](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)。 新しいFSUの名前とアドレスを、クラスターの現在のグループが表示されているグループに追 [!DNL Insight Servers] 加します。

1. マスター上のアクセス制御ファイルを編集し、 [!DNL Insight Server] Updating the Access Control File for [a Clusterの説明に従って、新しいFSUのIPアドレスを含めます](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)。

## 新しいInsightサーバーFSUのインストール {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 現在のFSU上で、インストールディレクトリのzipファイルを作 [!DNL Insight Server] 成し、そのファイルを新しいFSUにコピーします。
1. ソフトウェアを配置する場所にファイルを解凍し [!DNL Insight Server] ます。
1. 新しいFSU用のデジタル証明書をダウンロードし、「デジタル証明書のダウンロードとイ [ンストール」の説明に従ってインストールします](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 新しいFSUでWindowsのメモリ使用率パラメータを設定します。
1. サーバーのネットワーク [!DNL .address] ロケーションの定義の説明に従って、FSUの名前を反映す [るようにファイルの名前を変更します](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)。

1. 新しいFSUのドライブ構造がプライマリFSUのドライブ構造と異なる場合は、ファイルを編集する必要があり [!DNL Disk Files.cfg] ます。

   1. Open the [!DNL Disk Files.cfg] file on the new FSU.
   1. 「データセットデータ領域の監視」の説明に従って、プライマリFSUのドライブに合わ [せて設定を更新します](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03)。
   1. ファイルをローカルに、またはサーバーに保存します。

1. 新しいFSU [!DNL Insight Server] マシンでWindowsサービスとして登録します(「Windowsサービスとし [てのInsight Serverの登録」を参照](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540))。

1. クラスターに追加するFSUごとに、手順1 ～ 6を繰り返します。

## 新しいInsightサーバーFSUの設定 {#section-c39334c5bd754d5b98d41ad094333108}

次の手順で、特定の設定タスクの手順を説明します。 新しいFSUの導入に適した手順に従います。

**ソースデータストレージ用にFSUを設定するには**

新しいFSUがクラスターで実行中のデータセットの追加のソースデータを格納する場合は、『データセット設定ガイド』の「ログ処理設定ファイル」の章で説明されているように、ファイルサーバー設定プロセスを完了する必要が [!DNL Insight Server] あります **。

**新しいFSUにマスターFSUのバックアップを作成する[!DNL Insight Server]には**

新しいFSUをマスターのバックアップにする場合（クラスターのFSUとして機能する）、新しい [!DNL Insight Server] （バックアップ）FSU上の同期ファイルを変更して、マスターFSUと同期させる必要があります。

1. バックアップ [!DNL Insight Server] FSUで、を使用し [!DNL Server Files Manager] て、フォルダ内 [!DNL Synchronize.cfg] のファイルをフ [!DNL Components for Processing Servers] ォルダにコ [!DNL Components] ピーします。

1. にあるフ [!DNL Synchronize.cfg] ァイル(フォルダ内 [!DNL Components] )を開きま [!DNL Insight]す。

1. Componentsディレクトリの場所を指定するSynchronizeDirを探します。 「ディレクトリ」の下に複数の同期ディレクトリが表示される場合があるので、必要なサーバを見つけるには、その中の多くの同期ディレクトリの内容を（サーバ番号をクリックして）表示する必要があります。
1. 次の例に示すように、SynchronizeDirエントリを編集し、2番目のSynchronizeDirエントリを追加します。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 変更したファイルを新しい名前(例えば、クラ [!DNL FSU_Synchronize.cfg] スター内のDPU上のファイルと混同しない [!DNL Synchronize.cfg] ように)で保存します。

1. を使用し [!DNL Server Files Manager] て、名前を変更したファイルのローカルコピーをサーバに保存します。 バックアップFSUは、識別されたディレクトリ内のファイルをマスタ [!DNL Insight Server] FSUからダウンロードし、これらのファイルが変更された場合に、その更新されたコピーをマスタ [!DNL Insight Server] FSUから動的に検索する。

