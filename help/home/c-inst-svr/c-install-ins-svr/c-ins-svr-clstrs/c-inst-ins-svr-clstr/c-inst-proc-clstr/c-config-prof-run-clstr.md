---
description: Insight サーバークラスターで実行するようにデータセットプロファイルを設定すると、クラスター内のすべてのマシンが、そのプロファイルのすべてのデータセット設定ファイルを共有します。
title: クラスターで実行するためのプロファイルの設定
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 4%

---

# クラスターで実行するためのプロファイルの設定{#configuring-a-profile-to-run-on-a-cluster}

{{eol}}

Insight サーバークラスターで実行するようにデータセットプロファイルを設定すると、クラスター内のすべてのマシンが、そのプロファイルのすべてのデータセット設定ファイルを共有します。

したがって、これらのファイルのパラメーターのエントリは、すべての [!DNL Insight Servers] クラスター内で使用します。 例えば、読み取るログファイルの場所、 [!DNL Insight Server]、および [!DNL Insight Server] クラスタ内のすべてのマシンで同じである必要があります。

クラスターのマスター上ですべての構成タスクを実行します [!DNL Insight Server]( これは [!DNL Insight Server] を使用して設定ファイルを編集します。 マスター上で行われたすべての保存済み設定ファイルの変更 [!DNL Insight Server] は、処理中のファイルに自動的に同期されます [!DNL Insight Servers] クラスター内で使用します。

に対してデータセットプロファイルを実行するには、以下を実行します。 [!DNL Insight Server] クラスタの場合は、次の処理をリストの順序で実行する必要があります。

1. [イベントデータを処理する Insight サーバーの決定](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Profile.cfg での処理サーバーの指定](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （必要に応じて） [プロファイルのデータセット設定ファイルの変更](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## イベントデータを処理する Insight サーバーの決定 {#section-59b8e3f2b34f49739d544c8740a62fba}

必ずしも [!DNL Insight Servers] クラスタープロセスイベントデータ内。 1 つを指定できます [!DNL Insight Server] クラスタ内で、ソースファイル (VSLおよびログファイル ) を保存し、クラスタ内のすべてのデータ処理ユニット（処理サーバー）にファイルを提供するファイルサーバーユニットとして。 この設定は、単一のイベントデータリポジトリのメリットを提供し、クラスター内のすべての処理サーバーの処理能力を活用します。 処理サーバーはデータファイルを分割し、同じファイルが複数回処理されないことを保証します。

を指定する方法の詳細 [!DNL Insight Server] ファイルサーバーユニットとして実行するには、 *データセット設定ガイド*.

1 つのファイルサーバーユニットではなく、各処理サーバーにソースデータファイルを格納する場合は、ファイルを処理サーバー間で均等に分割する必要があります。 各処理サーバーにデータセットのソースファイルをすべて保存しないでください。 同じファイルの複数のコピーが複数の処理サーバーで使用できる場合、データは（各マシンで 1 回ずつ）複数回読み取られ、データが歪曲されます。

どれを選ぶかを判断する際に役立つ情報 [!DNL Insight Servers] ログファイルを処理する場合は、Adobeコンサルティングにお問い合わせください。

## Profile.cfg での処理サーバーの指定 {#section-99664e072c21462f91fbafb6d893fcf9}

内 [!DNL profile.cfg] ファイルを編集するには、プロファイルのデータを処理する処理サーバーを指定します。

**profile.cfg ファイルにアクセスするには**

プロファイル設定ファイルにアクセスするには、 [!DNL Profile Manager] in [!DNL Insight].

1. データセットプロファイル内で、 [!DNL Profile Manager] ワークスペース内で右クリックし、 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**&#x200B;または、 [!DNL Admin] タブをクリックします。

1. 内 [!DNL Profile Manager]、の横のチェックマークを右クリックします。 [!DNL profile.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. プロファイル設定ウィンドウが表示されます。

**処理サーバーを追加するには、以下を実行します。**

1. 内 [!DNL profile.cfg] ファイルを選択し、 **[!UICONTROL Profile]**&#x200B;を選択し、「 **[!UICONTROL Processing Servers]** コンテンツを表示する。

1. 右クリック **[!UICONTROL Processing Servers]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. 共通名パラメーターに、クラスター内の最初の処理サーバーの共通名を入力します。 例：[!DNL server1.mycompany.com]
1. 手順 2 と 3 を繰り返し、クラスター内のすべての処理サーバーの共通名を追加します。

   >[!NOTE]
   >
   >マスター [!DNL Insight Server] でデータを処理する場合は、データも追加する必要があります。

1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

1. チェックマーク ( [!DNL User] 隣の列 [!DNL profile.cfg]. クリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## プロファイルのデータセット設定ファイルの変更 {#section-99bf9248e4e5483cb518f453b0a2f278}

**データセット設定ファイルを変更するには**

データセット設定ファイル ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg]、データセットインクルードファイル、 [!DNL Log Processing Mode.cfg]など )、マスター上でのみ実行します。 [!DNL Insight Server].

1. 変更するファイルにアクセスします。

   ファイルにアクセスする手順については、 *データセット設定ガイド*.
1. 変更を加えます。詳しくは、 *データセット設定ガイド* 設定ファイル内のパラメーターに関する詳細。
1. ファイルを保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. チェックマーク ( [!DNL User] 列をクリックします。
   1. クリック **[!UICONTROL Save to]** をクリックし、目的のプロファイルを選択します。

>[!NOTE]
>
>[!DNL Insight] クラスター上で実行されているデータセットプロファイルにアクセスするユーザーは、マスターのみを識別します [!DNL Insight Server] 内 [!DNL Insight] 設定ファイル ( [!DNL insight.cfg]) をクリックします。 の観点から [!DNL Insight] ユーザー、プロファイルは 1 つのみでアクセス可能 [!DNL Insight Server] ( 主人 [!DNL Insight Server]);ただし、アナリストからのクエリリクエストは、任意の [!DNL Insight Servers] クラスター内で使用します。

An [!DNL Insight Server] クラスターは、次の集中的なストレージを許可します： [!DNL .vsl] ログファイル ( [!DNL Sensor]) を単一の [!DNL Insight Server] FSU(File Server Unit) と呼ばれるマシン FSU のインストールについては、 [Insight サーバー FSU のインストール手順](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). FSU の設定について詳しくは、 *データセット設定ガイド*.
