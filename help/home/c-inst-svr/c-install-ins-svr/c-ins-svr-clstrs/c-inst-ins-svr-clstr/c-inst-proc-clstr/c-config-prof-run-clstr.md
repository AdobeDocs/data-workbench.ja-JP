---
description: Insightサーバークラスター上で実行するようにデータセットプロファイルを設定すると、クラスター内のすべてのマシンが、そのプロファイルのすべてのデータセット設定ファイルを共有します。
title: クラスターで実行するためのプロファイルの設定
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 4%

---

# クラスターで実行するためのプロファイルの設定{#configuring-a-profile-to-run-on-a-cluster}

Insightサーバークラスター上で実行するようにデータセットプロファイルを設定すると、クラスター内のすべてのマシンが、そのプロファイルのすべてのデータセット設定ファイルを共有します。

したがって、これらのファイル内のパラメーターのエントリは、クラスター内のすべての[!DNL Insight Servers]に適用できる必要があります。 例えば、読み取るログファイルの場所、[!DNL Insight Server]で使用する参照ファイル、[!DNL Insight Server]で出力されるデータの場所は、クラスター内のすべてのマシンで同じである必要があります。

構成ファイルの編集に使用する[!DNL Insight Server]である、クラスターのマスター[!DNL Insight Server]上で、すべての構成タスクを実行します。 マスター[!DNL Insight Server]上で行われた保存済みの設定ファイルの変更は、クラスター内の処理[!DNL Insight Servers]上のファイルに自動的に同期されます。

[!DNL Insight Server]クラスター上でデータセットプロファイルを実行するには、以下の手順をリストに記載されている順序で実行する必要があります。

1. [イベントデータを処理するInsightサーバーの決定](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Profile.cfgでの処理サーバーの指定](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. （必要に応じて） [プロファイルのデータセット設定ファイルの変更](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## イベントデータを処理するInsightサーバーの特定{#section-59b8e3f2b34f49739d544c8740a62fba}

クラスター内の[!DNL Insight Servers]すべてがイベントデータを処理する必要はありません。 クラスター内の1つの[!DNL Insight Server]を、ソースファイル(VSLおよびログファイル)を格納し、そのファイルをクラスター内のすべてのデータ処理ユニット（処理サーバー）に提供するファイルサーバーユニットとして指定できます。 この設定は、単一のイベントデータリポジトリのメリットを提供し、クラスター内のすべての処理サーバーの処理能力を活用します。 処理サーバーはデータファイルを分割し、同じファイルが複数回処理されないことを保証します。

ファイルサーバーユニットとして実行する[!DNL Insight Server]の指定について詳しくは、『データセット設定ガイド&#x200B;*』の「ログ処理設定ファイル」の章を参照してください。*

ソースデータファイルを1台のファイルサーバーユニットではなく、各処理サーバーに格納する場合は、各処理サーバー間でファイルを等しく分割する必要があります。 各処理サーバーにデータセットのソースファイルをすべて保存しないでください。 同じファイルの複数のコピーが複数の処理サーバーで使用可能な場合、データは複数回（各マシンで1回）読み取られ、データが歪曲されます。

ログファイルを処理する[!DNL Insight Servers]の決定については、Adobeコンサルティングにお問い合わせください。

## Profile.cfgでの処理サーバーの指定{#section-99664e072c21462f91fbafb6d893fcf9}

[!DNL profile.cfg]ファイルで、プロファイルのデータを処理する処理サーバーを指定します。

**profile.cfgファイルにアクセスするには**

[!DNL Insight]の[!DNL Profile Manager]を使用して、プロファイル設定ファイルにアクセスします。

1. データセットプロファイル内で右クリックして[!DNL Profile Manager]を開くには、ワークスペース内で&#x200B;**[!UICONTROL Admin]** / **[!UICONTROL Profile]** / **[!UICONTROL Profile Manager]**&#x200B;をクリックするか、[!DNL Admin]タブで「プロファイル管理」ワークスペースを開きます。

1. [!DNL Profile Manager]で、[!DNL profile.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。 プロファイル設定ウィンドウが表示されます。

**処理サーバーを追加するには**

1. [!DNL profile.cfg]ファイルで、「**[!UICONTROL Profile]**」をクリックし、「**[!UICONTROL Processing Servers]**」をクリックして内容を表示します。

1. **[!UICONTROL Processing Servers]**&#x200B;を右クリックし、**[!UICONTROL Add new]** / **[!UICONTROL Processing Server]**&#x200B;をクリックします。

1. Common Nameパラメーターに、クラスター内の最初の処理サーバーの共通名を入力します。 例：[!DNL server1.mycompany.com]
1. 手順2と3を繰り返して、クラスター内のすべての処理サーバーの共通名を追加します。

   >[!NOTE]
   >
   >マスター[!DNL Insight Server]がデータを処理する場合は、データも追加する必要があります。

1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

1. [!DNL profile.cfg]の横の[!DNL User]列のチェックマークを右クリックします。 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]***&#x200B;をクリックします。

## プロファイル{#section-99bf9248e4e5483cb518f453b0a2f278}のデータセット設定ファイルの変更

**データセット設定ファイルを変更するには**

データセット設定ファイル（[!DNL Log Processing.cfg]、[!DNL Transformation.cfg]、データセットインクルードファイル、[!DNL Log Processing Mode.cfg]など）を変更する必要がある場合は、マスター[!DNL Insight Server]上でのみ変更します。

1. 変更するファイルにアクセスします。

   ファイルへのアクセス方法については、『データセット設定ガイド&#x200B;*』を参照してください。*
1. 変更を加えます。設定ファイル内のパラメーターに関する詳細については、『*データセット設定ガイド*』を参照してください。
1. ファイルを保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

   1. ファイル名の横の[!DNL User]列のチェックマークを右クリックします。
   1. **[!UICONTROL Save to]**&#x200B;をクリックし、目的のプロファイルを選択します。

>[!NOTE]
>
>[!DNL Insight] クラスター上で実行するデータセットプロファイルにアクセスするユーザーは、設定ファ [!DNL Insight Server] イル( )内の [!DNL Insight] マスターのみを識 [!DNL insight.cfg]別します。[!DNL Insight]ユーザーの視点から見ると、プロファイルは1つの[!DNL Insight Server]（マスター[!DNL Insight Server]）でのみアクセスできます。ただし、アナリストからのクエリ要求は、クラスター内の[!DNL Insight Servers]のいずれかに送信できます。

[!DNL Insight Server]クラスターは、ファイルサーバーユニット(FSU)と呼ばれる1台の[!DNL Insight Server]マシン上に（[!DNL Sensor]からの）[!DNL .vsl]ログファイルの集中保存を許可します。 FSUのインストールについて詳しくは、 [InsightサーバーFSUのインストール手順](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)を参照してください。 FSUの設定について詳しくは、『*データセット設定ガイド*』を参照してください。
