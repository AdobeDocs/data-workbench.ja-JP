---
description: Dataset ディレクトリには、ソフトウェアの動作や、ご利用のアドビ環境の追加機能を利用するうえで必要な補足的なファイルが格納されます。
solution: Analytics
title: その他のファイル
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 56%

---


# その他のファイル{#other-files}

Dataset ディレクトリには、ソフトウェアの動作や、ご利用のアドビ環境の追加機能を利用するうえで必要な補足的なファイルが格納されます。

* **[!DNL Client.cfg:]** プロファイルのDatasetディレクトリ内の [!DNL Client.cfg] ファイルは、 [!DNL Base] ソフトウェアの動作に必要です。 [!DNL Client.cfg] ファイル内のパラメーターを削除したり変更を加えたりすることは避けてください。

* **[!DNL Cluster.cfg:]** プロファイルのDatasetディレクトリ内の [!DNL Cluster.cfg] ファイルは、 [!DNL Base] ソフトウェアの動作に必要です。 Data Workbench サーバークラスターでデータセットを処理するように設定する場合、[!DNL Cluster.cfg] ファイルで Normalize Server パラメーターのみを編集する必要があります。Normalize Server パラメーターを編集する方法については、[クラスターにおける中央の正規化サーバーの作成](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)を参照してください。

* **[!DNL Insight Transform.cfg]および[!DNL Insight Transform Mode.cfg]:** 変換機能を使用している場合は、その [!DNL Transform.cfg] プロファイルのDatasetディレクトリに、Data Workbench [!DNL TransformMode.cfg][!DNL Transform] とData Workbenchの2つの追加設定ファイルがあります。 For information about these files and their parameters, see [Transform Functionality](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* **PAServer.cfg** ファイル：Insight Server に予測分析クラスタリングジョブを送信する場合は、サーバー側でクラスタリング送信を処理するように [!DNL PAServer.cfg] ファイルを設定する必要があります。The custom profile should inherit the [!DNL PAServer.cfg] from the Predictive Analytics profile ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Set a *Master Server* in this file and save the [!DNL PAServer.cfg] to the implementation site.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```

