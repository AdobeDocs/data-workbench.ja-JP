---
description: Dataset ディレクトリには、ソフトウェアの動作や、ご利用のアドビ環境の追加機能を利用するうえで必要な補足的なファイルが格納されます。
title: その他のファイル
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 57%

---

# その他のファイル{#other-files}

{{eol}}

Dataset ディレクトリには、ソフトウェアの動作や、ご利用のアドビ環境の追加機能を利用するうえで必要な補足的なファイルが格納されます。

* **[!DNL Client.cfg:]** この [!DNL Client.cfg] ファイルを [!DNL Base] ソフトウェアを操作するにはプロファイルが必要です。 [!DNL Client.cfg] ファイル内のパラメーターを削除したり変更を加えたりすることは避けてください。

* **[!DNL Cluster.cfg:]** この [!DNL Cluster.cfg] ファイルを [!DNL Base] ソフトウェアを操作するにはプロファイルが必要です。 Data Workbench サーバークラスターでデータセットを処理するように設定する場合、[!DNL Cluster.cfg] ファイルで Normalize Server パラメーターのみを編集する必要があります。Normalize Server パラメーターを編集する方法については、[クラスターにおける中央の正規化サーバーの作成](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)を参照してください。

* **[!DNL Insight Transform.cfg]および [!DNL Insight Transform Mode.cfg]:** 変換機能を使用する場合、Data Workbench という 2 つの追加の設定ファイルがあります [!DNL Transform.cfg] と data workbench [!DNL TransformMode.cfg]( [!DNL Transform] プロファイル。 これらのファイルとそのパラメーターについては、 [変換機能](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* **PAServer.cfg** ファイル：Insight Server に予測分析クラスタリングジョブを送信する場合は、サーバー側でクラスタリング送信を処理するように [!DNL PAServer.cfg] ファイルを設定する必要があります。カスタムプロファイルは [!DNL PAServer.cfg] 予測分析プロファイル ( [!DNL Server\Profiles\Predictive Analytics\Dataset]) をクリックします。

   >[!IMPORTANT]
   >
   >を設定します。 *マスターサーバ* このファイルで、 [!DNL PAServer.cfg] を実装サイトに追加します。
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
