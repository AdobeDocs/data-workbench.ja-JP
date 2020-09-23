---
description: Insight Serverクラスター上で実行するようにデータセットプロファイルを設定した場合、クラスター内のすべてのマシンが、そのプロファイルーのすべてのデータセット設定ファイルを共有します。
solution: Analytics
title: クラスターで実行するためのプロファイルの設定
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 4%

---


# クラスターで実行するためのプロファイルの設定{#configuring-a-profile-to-run-on-a-cluster}

Insight Serverクラスター上で実行するようにデータセットプロファイルを設定した場合、クラスター内のすべてのマシンが、そのプロファイルーのすべてのデータセット設定ファイルを共有します。

したがって、これらのファイル内のパラメーターのエントリは、クラスター内のすべてに適用でき [!DNL Insight Servers] る必要があります。 例えば、読み取るログファイルの場所、で使用する参照ファイル [!DNL Insight Server]、およびによるデータ出力の場所は、クラスター内のすべてのマシンで同じにする必要 [!DNL Insight Server] があります。

クラスターのマスターに対してすべての設定タスクを実行し [!DNL Insight Server]ます。これは、設定ファイルの編集 [!DNL Insight Server] に使用するマスターです。 マスター上で保存された構成ファイルに対する変更は、すべて、クラスター内の処理上のファイルに対して自動的 [!DNL Insight Server][!DNL Insight Servers] に同期されます。

クラスター上でデータセットプロファイルを実行するに [!DNL Insight Server] は、次のプロセスをリストに表示された順序で実行する必要があります。

1. [イベントデータを処理するInsightサーバーの決定](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [プロファイル.cfgでの処理サーバーの指定](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （必要に応じて）プロファイルのデータセット設定ファイルの [変更](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## イベントデータを処理するInsightサーバーの決定 {#section-59b8e3f2b34f49739d544c8740a62fba}

クラスタープロセスイベントデータのすべて [!DNL Insight Servers] を含める必要はありません。 クラスター内の1つ [!DNL Insight Server] を、ソースファイル(VSLおよびログファイル)を格納し、そのファイルをクラスター内のすべてのデータ処理ユニット（処理サーバー）に提供するファイルサーバーユニットとして指定できます。 この設定は、1つのイベントデータリポジトリのメリットを提供し、クラスター内のすべての処理サーバーの処理能力を活用します。 処理サーバーはデータファイルを分割し、同じファイルが複数回処理されないことを保証します。

ファイルサーバーユニットとして実行す [!DNL Insight Server] るタグの指定について詳しくは、『 *データセット設定ガイド*』の「ログ処理設定ファイル」という章を参照してください。

ソースデータファイルを1つのファイルサーバーユニットではなく、各処理サーバーに格納する場合は、各処理サーバー間でファイルを等しく分割する必要があります。 各処理サーバーにデータセットのソースファイルをすべて格納するわけではありません。 同じファイルの複数のコピーが複数の処理サーバーで使用できる場合、データは複数回（各マシンに1回ずつ）読み取られ、データに歪みが生じます。

どのログファイルを処理する [!DNL Insight Servers] べきかの判断については、Adobeコンサルティングにお問い合わせください。

## プロファイル.cfgでの処理サーバーの指定 {#section-99664e072c21462f91fbafb6d893fcf9}

フ [!DNL profile.cfg] ァイルで、プロファイルのデータを処理する処理サーバーを指定します。

**プロファイル.cfgファイルにアクセスするには**

プロファイル設定ファイルには、でアクセス [!DNL Profile Manager] し [!DNL Insight]ます。

1. データセットプロファイルで作業している間に、ワークスペース内で右クリックし、 [!DNL Profile Manager] / **[!UICONTROL Admin]** >をクリックするか、 **[!UICONTROL Profile]****[!UICONTROL Profile Manager]**[!DNL Admin] タブのプロファイル管理ワークスペースを開いて、ワークスペースを開きます。

1. で、の横のチェックマーク [!DNL Profile Manager]を右クリックし、 [!DNL profile.cfg] をクリックし **[!UICONTROL Make Local]**&#x200B;ます。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** /をクリックし **[!UICONTROL in Insight]**&#x200B;ます。 プロファイル設定ウィンドウが表示されます。

**処理サーバーを追加するには**

1. ファイル内でをクリックし [!DNL profile.cfg] 、をクリックして内容 **[!UICONTROL Profile]****[!UICONTROL Processing Servers]** を表示します。

1. 右クリック **[!UICONTROL Processing Servers]** し、「>」をクリックし **[!UICONTROL Add new]** ま **[!UICONTROL Processing Server]**&#x200B;す。

1. Common Nameパラメーターに、クラスター内の最初の処理サーバーの共通名を入力します。 例：[!DNL server1.mycompany.com]
1. 手順2と3を繰り返して、クラスター内のすべての処理サーバーの共通名を追加します。

   >[!NOTE]
   >
   >マスターがデータを [!DNL Insight Server] 処理する場合は、データも追加する必要があります。

1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

1. の横の [!DNL User] 列のチェックマークを右クリックし [!DNL profile.cfg]ます。 Click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## プロファイルのデータセット設定ファイルの変更 {#section-99bf9248e4e5483cb518f453b0a2f278}

**データセット設定ファイルを変更するには**

データセット設定ファイル(、 [!DNL Log Processing.cfg]、データセットインクルードファイルな [!DNL Transformation.cfg]ど)を変更する必要がある場合は、マスター上でのみ行ってくだ [!DNL Log Processing Mode.cfg][!DNL Insight Server]さい。

1. 変更するファイルにアクセスします。

   ファイルへのアクセス方法については、『 *データセット設定ガイド*』を参照してください。
1. 変更を加えます。設定ファイル内のパラメーターの詳細については、『 *データセット設定ガイド* 』を参照してください。
1. ファイルを保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. ファイル名の横の [!DNL User] 列のチェックマークを右クリックします。
   1. をクリック **[!UICONTROL Save to]** し、目的のプロファイルを選択します。

>[!NOTE]
>
>[!DNL Insight] クラスター上で実行されているデータセットプロファイルにアクセスするユーザーは、 [!DNL Insight Server] 設定ファイル( [!DNL Insight][!DNL insight.cfg])内のマスターのみを識別します。 ユーザーの視点から見ると、 [!DNL Insight] プロファイルは1つ [!DNL Insight Server] (マスター [!DNL Insight Server])でしかアクセスできません。ただし、アナリストからのクエリ要求は、クラスター内の任意のに送信 [!DNL Insight Servers] できます。

クラスタ [!DNL Insight Server] ーは、ファイルサーバーユニット(FSU)と呼ばれる1 [!DNL .vsl] 台の [!DNL Sensor][!DNL Insight Server] マシン上で（ログファイルの）集中ストレージを許可します。 FSUのインストールについて詳しくは、「InsightサーバーFSUの [インストール手順](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)」を参照してください。 FSUの設定について詳しくは、『 *データセット設定ガイド*』を参照してください。
