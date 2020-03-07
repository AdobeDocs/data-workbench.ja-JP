---
description: Dataset ディレクトリには、ソフトウェアの動作や、ご利用のアドビ環境の追加機能を利用するうえで必要な補足的なファイルが格納されます。
solution: Analytics
title: その他のファイル
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# その他のファイル{#other-files}

Dataset ディレクトリには、ソフトウェアの動作や、ご利用のアドビ環境の追加機能を利用するうえで必要な補足的なファイルが格納されます。

* **[!DNL Client.cfg:]** プロフ [!DNL Client.cfg] ァイルのDatasetディレクトリ内のファイル [!DNL Base] は、ソフトウェアの操作に必要です。 [!DNL Client.cfg] ファイル内のパラメーターを削除したり変更を加えたりすることは避けてください。

* **[!DNL Cluster.cfg:]** プロフ [!DNL Cluster.cfg] ァイルのDatasetディレクトリ内のファイル [!DNL Base] は、ソフトウェアの操作に必要です。 Data Workbench サーバークラスターでデータセットを処理するように設定する場合、[!DNL Cluster.cfg] ファイルで Normalize Server パラメーターのみを編集する必要があります。Normalize Server パラメーターを編集する方法については、[クラスターにおける中央の正規化サーバーの作成](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)を参照してください。

* **[!DNL Insight Transform.cfg]および[!DNL Insight Transform Mode.cfg]:**変換機能を使用している場合は、プロファイルのDatasetディレクトリに、Data WorkbenchとData Workbench[!DNL Transform.cfg]の2つ[!DNL TransformMode.cfg]の追加の設定ファイルがあ[!DNL Transform]ります。 For information about these files and their parameters, see[Transform Functionality](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* **PAServer.cfg** ファイル：Insight Server に予測分析クラスタリングジョブを送信する場合は、サーバー側でクラスタリング送信を処理するように [!DNL PAServer.cfg] ファイルを設定する必要があります。The custom profile should inherit the [!DNL PAServer.cfg] from the Predictive Analytics profile ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Set a *Master Server* in this file and save the [!DNL PAServer.cfg] to the implementation site.   >
   >
   >
   ```>
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```  >
   >



