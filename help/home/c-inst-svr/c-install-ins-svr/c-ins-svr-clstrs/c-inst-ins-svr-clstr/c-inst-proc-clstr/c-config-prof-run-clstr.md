---
description: データセットプロファイルをInsightサーバークラスター上で実行するように設定すると、クラスター内のすべてのコンピューターが、そのプロファイルのすべてのデータセット設定ファイルを共有します。
solution: Insight
title: クラスターで実行するプロファイルの設定
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# クラスターで実行するプロファイルの設定{#configuring-a-profile-to-run-on-a-cluster}

データセットプロファイルをInsightサーバークラスター上で実行するように設定すると、クラスター内のすべてのコンピューターが、そのプロファイルのすべてのデータセット設定ファイルを共有します。

したがって、これらのファイル内のパラメーターのエントリは、クラスター内のすべてに適用で [!DNL Insight Servers] きる必要があります。 例えば、読み取るログファイルの場所、が使用する参照ファイル、およびによるデータ出力の場所は、クラスター内のすべてのマシンで同じである [!DNL Insight Server][!DNL Insight Server] 必要があります。

設定ファイルの編集に使用する、クラスターのマ [!DNL Insight Server]スター上で、すべ [!DNL Insight Server] ての設定タスクを実行します。 マスター上で保存された構成ファイルに対する変更は、 [!DNL Insight Server] すべてクラスター内の処理上のファイルに自動的に [!DNL Insight Servers] 同期されます。

クラスター上でデータセットプロファイルを実 [!DNL Insight Server] 行するには、次のプロセスをリストに示す順序で実行する必要があります。

1. [イベントデータを処理するInsightサーバーの決定](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Profile.cfgでの処理サーバーの指定](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （必要に応じて）プロ [ファイルのデータセット設定ファイルの変更](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## イベントデータを処理するInsightサーバーの決定 {#section-59b8e3f2b34f49739d544c8740a62fba}

クラスター内のすべてのプロセスイ [!DNL Insight Servers] ベントデータを含める必要はありません。 クラスター内の1つ [!DNL Insight Server] を、ソースファイル（VSLおよびログファイル）を格納し、そのファイルをクラスター内のすべてのデータ処理ユニット（処理サーバー）に提供するファイルサーバーユニットとして指定できます。 この設定は、単一のイベントデータリポジトリのメリットを提供し、クラスタ内のすべての処理サーバの処理能力を活用します。 処理サーバは、データファイルを分割し、同じファイルが複数回処理されないことを保証します。

ファイルサーバーユニットとし [!DNL Insight Server] て実行するファイルの指定について詳しくは、『データセット設定ガイド』の「ログ処理設定ファイル」の章 *を参照してください*。

1つのファイルサーバーユニットではなく、各処理サーバーにソースデータファイルを格納する場合は、処理サーバー間でファイルを等しく分割する必要があります。 各処理サーバーにデータセットのソースファイルをすべて保存しないでください。 同じファイルの複数のコピーが複数の処理サーバーで使用可能な場合、データは（各マシンで1回ずつ）複数回読み取られ、データが歪曲されます。

どのログファイルを処理する [!DNL Insight Servers] かを決定する際には、アドビのコンサルティングにお問い合わせください。

## Profile.cfgでの処理サーバーの指定 {#section-99664e072c21462f91fbafb6d893fcf9}

ファイル [!DNL profile.cfg] 内で、プロファイルのデータを処理する処理サーバーを指定します。

**profile.cfgファイルにアクセスするには**

プロファイル設定ファイルには、のを使用してアクセ [!DNL Profile Manager] スしま [!DNL Insight]す。

1. データセットプロファイル内で作業してい [!DNL Profile Manager] る間に、ワークスペース内で右クリックし、/ **[!UICONTROL Admin]** >をクリックするか、 **[!UICONTROL Profile]** タブのプロファイル管理ワークスペースを開き **[!UICONTROL Profile Manager]**[!DNL Admin] ます。

1. で、の横 [!DNL Profile Manager]のチェックマークを右クリックし、をク [!DNL profile.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL in Insight]**&#x200B;す。 プロファイル設定ウィンドウが表示されます。

**処理サーバーを追加するには**

1. ファイル内 [!DNL profile.cfg] でをクリックし、 **[!UICONTROL Profile]**&#x200B;をクリックし **[!UICONTROL Processing Servers]** てその内容を表示します。

1. 右クリックし、/ **[!UICONTROL Processing Servers]** をクリ **[!UICONTROL Add new]** ックしま **[!UICONTROL Processing Server]**&#x200B;す。

1. 「共通名」パラメーターに、クラスター内の最初の処理サーバーの共通名を入力します。 次に例を示します。[!DNL server1.mycompany.com]
1. 手順2と3を繰り返し、クラスター内のすべての処理サーバーの共通名を追加します。

   >[!NOTE]
   >
   >マスターがデータを [!DNL Insight Server] 処理する場合は、データも追加する必要があります。

1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

1. の横の列のチェックマークを右ク [!DNL User] リックしま [!DNL profile.cfg]す。 Click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## プロファイルのデータセット設定ファイルの変更 {#section-99bf9248e4e5483cb518f453b0a2f278}

**データセット設定ファイルを変更するには**

データセット設定ファイル(、、データセットインクルード [!DNL Log Processing.cfg]ファ [!DNL Transformation.cfg]イルなど)を変更する必要が [!DNL Log Processing Mode.cfg]ある場合は、マスター上でのみ変更を行いま [!DNL Insight Server]す。

1. 変更するファイルにアクセスします。

   ファイルへのアクセス方法については、『データセット設定ガ *イド』を参照してください*。
1. 変更を加えます。設定ファイル *内のパラメーターの詳細については* 、『データセット設定ガイド』を参照してください。
1. ファイルを保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. ファイル名の横の列のチェックマ [!DNL User] ークを右クリックします。
   1. をクリック **[!UICONTROL Save to]** し、目的のプロファイルを選択します。

>[!NOTE]
>
>[!DNL Insight] クラスター上で実行されているデータセットプロファイルにアクセスするユーザーは、設定ファイル( [!DNL Insight Server] )内のマスター [!DNL Insight] のみを識別するこ [!DNL insight.cfg]とができます。 ユーザーの観点から見 [!DNL Insight] ると、プロファイルは1つ（マスター） [!DNL Insight Server] でのみアクセ [!DNL Insight Server]スでき、ただし、アナリストからのクエリ要求は、クラスター内の任意の要素に [!DNL Insight Servers] 送信できます。

クラス [!DNL Insight Server] タは、ファイルサーバーユニット(FSU)と呼ばれ [!DNL .vsl] る1台のマシンに( [!DNL Sensor]ログファイルの) [!DNL Insight Server] 一元的な保存を許可します。 FSUのインストールについて詳しくは、『InsightサーバーFSU [のインストール手順』を参照してください](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)。 FSUの設定について詳しくは、『データセット設定ガイド』を *参照してください*。
