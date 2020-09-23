---
description: 追加のファイルサーバーにソースデータを保存する場合や、マスターInsightサーバーのバックアップを設定する場合は、InsightサーバーのFSUを既存のクラスターに追加します。
solution: Analytics
title: 既存のクラスターへの Insight サーバー FSU の追加
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---


# 既存のクラスターへの Insight サーバー FSU の追加{#adding-an-insight-server-fsu-to-an-existing-cluster}

追加のファイルサーバーにソースデータを保存する場合や、マスターInsightサーバーのバックアップを設定する場合は、InsightサーバーのFSUを既存のクラスターに追加します。

既存のクラスターに [!DNL Insight Server] FSUを追加するには、次の手順を実行する必要があります。

1. [マスターサーバーの設定ファイルの更新](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [新しいInsightサーバーFSUのインストール](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [新しいInsightサーバーFSUの設定](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## マスターサーバーの設定ファイルの更新 {#section-b5f21f2edb35493da4475de2cdeefca1}

で、マスター [!DNL Insight](通常は [!DNL Server Files Manager] FSU) [!DNL Insight Server][!DNL Insight Server] のを開き、クラスターに追加する各FSUに対して次の操作を行います。

1. マスター上のアドレスファイルを編集し、新しいFSUの名前とアドレス [!DNL Insight Server] を含めます(「アドレスファイルへの処理インサイトサーバーの [追加](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)」を参照)。 クラスターの追加現在のグループに対する新しいFSUの名前とアドレスが表示さ [!DNL Insight Servers] れます。

1. マスター上のアクセス制御ファイルを編集し、新しいFSUのIPアドレス [!DNL Insight Server] を含めます(クラスター用のアクセス制御ファイルの [更新の説明に従います](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b))。

## 新しいInsightサーバーFSUのインストール {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 現在のFSU上に、インストールディレクトリのzipファイルを作成し、新しいFSUにその [!DNL Insight Server] ファイルをコピーします。
1. ソフトウェアを配置する場所にファイルを解凍し [!DNL Insight Server] ます。
1. デジタル証明書のダウンロードとインストールの説明に従って、新しいFSU用のデジタル証明書をダウンロ [ードしてインストールします](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 新しいFSUにWindowsのメモリ使用率パラメータを設定します。
1. サーバーのネットワーク場所の [!DNL .address] 定義の説明に従って、FSUの名前を反映するように [](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)ファイル名を変更します。

1. 新しいFSUのドライブ構造がプライマリFSUのドライブ構造と異なる場合は、 [!DNL Disk Files.cfg] ファイルを編集する必要があります。

   1. Open the [!DNL Disk Files.cfg] file on the new FSU.
   1. データセットデータ領域の [監視の説明に従って、プライマリFSUのドライブに一致するように設定を更新します](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03)。
   1. ファイルをローカルに、またはサーバーに保存します。

1. 新しいFSUマシン [!DNL Insight Server] にWindowsサービスとして登録します(「Insight ServerをWindowsサービスとして [登録する](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)」を参照)。

1. クラスターに追加するFSUごとに、手順1 ～ 6を繰り返します。

## 新しいInsightサーバーFSUの設定 {#section-c39334c5bd754d5b98d41ad094333108}

以下の手順では、特定の設定タスクの手順を示します。 新しいFSUの実装に適した手順に従います。

**ソースデータストレージ用にFSUを設定するには**

新しいFSUにクラスター上で実行するデータセットの追加のソースデータが格納される場合は、『データセット設定ガイド』の「ログ処理設定ファイル」の章で [!DNL Insight Server] File Server Unitの設定に説明されているように、ファイルサーバー設定プロセスを完了する必要があります **。

**新しいFSUにマスターFSUのバックアップを作成するには[!DNL Insight Server]**

新しいFSUをマスターのバックアップにする場合 [!DNL Insight Server] は（クラスターのFSUとして機能する）、新しい（バックアップ）FSUの同期ファイルを変更して、マスターFSUと同期させる必要があります。

1. バックアップ [!DNL Insight Server] FSUで、を使用してフォルダ内の [!DNL Server Files Manager] ファイルを [!DNL Synchronize.cfg] フォルダにコピーし [!DNL Components for Processing Servers][!DNL Components] ます。

1. フォルダ内の [!DNL Synchronize.cfg] ファイルを開き [!DNL Components] ま [!DNL Insight]す。

1. Componentsディレクトリの場所を指定するSynchronizeDirを探します。 「Directories」に複数の同期ディレクトリが表示される場合があるので、必要なサーバを見つけるには、サーバ番号をクリックして、その内容を表示する必要がある場合があります。
1. 次の例に示すように、SynchronizeDirエントリを編集し、2つ目のSynchronizeDirエントリを追加します。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 変更したファイルを新しい名前(例えば、クラスター内のDPU上の [!DNL FSU_Synchronize.cfg][!DNL Synchronize.cfg] ファイルと混同しないように)で保存します。

1. を使用して、名前を変更したファイルのローカルコピーをサーバーに保存します。 [!DNL Server Files Manager] バックアップFSUは、識別されたディレクトリ内のファイルをマスターFSUからダウンロードし、これらのファイルが変更された場合に、その更新されたコピーをマスター [!DNL Insight Server][!DNL Insight Server] FSUから動的に取得する。

