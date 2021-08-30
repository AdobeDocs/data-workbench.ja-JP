---
description: Data Workbenchでは、ファイルを書き出して、統合Adobe Experience Cloudの一部としてプロファイルおよびオーディエンスの書き出しと統合できます。
title: マスターマーケティングプロファイルエクスポート
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
exl-id: 9fc89815-d31d-41a7-a0c0-de1e84b24baa
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 67%

---

# マスターマーケティングプロファイルエクスポート{#master-marketing-profile-export}

Data Workbenchでは、ファイルを書き出して、統合されたAdobe Experience Cloudの一部としてProfiles &amp; Audiencesと統合できます。

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

プロファイルとExperience Cloudは、[!DNL Adobe Experience Cloud]のコアサービスである[オーディエンスIDサービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)の一部です。 Profiles &amp; Audiencesのエクスポートを使用すると、すべての訪問者に割り当てられ、[Audience Manager](https://docs.adobe.com/content/help/ja-JP/experience-cloud/user-guides/home.html)で使用される一意のExperience CloudID(ECID)を使用して、Experience Cloud全体でオーディエンスを共有できます。 MMPとAdobe Targetの両方のエクスポートを生成するには、[!DNL ExportIntegration.exe]アプリケーション([!DNL E:\Server\Scripts])を使用します。

**プロファイルとオーディエンスを使用するためのFSUサーバーの設定**

1. FSU サーバーにアクセスします。
1. MMPExport.cfg ファイルを開きます`Server/Admin/Export/MMPExport.cfg` を参照してください。
1. 必要に応じて、すべてのフィールドに値を入力します。次に例を示します。

   >[!NOTE]
   >
   >MMP/AAMの統合では、Amazonのs3バケットを利用してデータを転送します。
   >
   >
   >MMP（s3）転送に必要な s3 情報は Audience Manager チームから入手できます。

   ```
   Sample MMPExport.cfg
   MMP Export Configuration = MMPExportConfiguration: 
   s3 Bucket = string: aws_bucket_for_mmp 
   s3 Object Directory = string: test/files/ 
   s3 Region = string: us-east-1 
   s3 Access Key = string: ZZKI62OO5YBA 
   s3 Secret Key = string: ioqwa3OpNE5 
   data Provider Name = string: 895 
   client ID = string: mcprofile2-test 
   client Secret = string: saea1287617212987q 
   username = string: mmptest 
   password = string: pass 
   numRecordsPerChunk = int:  
   numThreads = int:  
   maxRetriesOnSendFailure = unsigned int:
   ```

   >[!NOTE]
   >
   >また、[!DNL MMPExport.cfg]ファイルを使用して、すべてのレコードを取得し、それらをセットに分割し、レコードのチャンクを作成できます。 これらのレコードチャンクは、その後 Amazon S3 にエクスポートされます。レコードのチャンクを作成するには、次の3つの必須パラメーターが必要です。[!DNL numRecordsPerChunk]、[!DNL numThreads]、および[!DNL maxRetriesOnSendFailure]。

**パラメーターの定義**

<table id="table_DDEFBC45895A4663973F9C2EB9052FEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>s3 Bucket</i> </td> 
   <td colname="col2"> エクスポートの転送先の AWS s3 バケット。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Object Directory</i> </td> 
   <td colname="col2"> s3 ファイルを保存するためのパス。サブディレクトリをサポートします。 <p> <p>重要：スペースとマルチバイト文字をパスに含めることはできません。エクスポートでエラーが発生します（ハイフンは含めることができます）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Region</i> </td> 
   <td colname="col2"> エクスポートの送信先の AWS s3 リージョン。例えば、us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Access Key</i> </td> 
   <td colname="col2"> AWS s3 アクセスキー </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Secret Key</i> </td> 
   <td colname="col2"> AWS s3 シークレットキー </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>data Provider Name</i> </td> 
   <td colname="col2"> AAM にセグメントと特性をそれぞれ保存するために使用されるフォルダー名。顧客ごとに一意である必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>client ID</i> </td> 
   <td colname="col2"> 顧客が MMP 用にプロビジョニングされるときに提供される一意のクライアント ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>client Secret</i> </td> 
   <td colname="col2"> <p><i></i>顧客が MMP に対してプロビジョニングされたときに割り当てられる一意のクライアントシークレットです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>username</i> </td> 
   <td colname="col2"> MMP のユーザー名 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>パスワード</i> </td> 
   <td colname="col2"> MMP のパスワード </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numRecordsPerChunk</i> </td> 
   <td colname="col2"> <p>チャンクのサイズをレコード数で指定します。 </p> <p>実装では、ユーザー指定の値を最小= 1000レコード&amp;nbsp;（～50 KBチャンク）&amp;nbsp；および最大= 50000レコード（～2.5 MBチャンク）にクリップします。&amp;nbsp；ユーザーがこの設定プロパティを指定しない場合は、デフォルト値の10000が使用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThreads</i> </td> 
   <td colname="col2"> <p>チャンク送信部の並列度を指定します。1 スレッドから 24 スレッドまでの値が指定可能で、デフォルト値は 12 スレッドです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailure</i> </td> 
   <td colname="col2"> <p>チャンクの送信に失敗した場合に行う再試行の回数を指定します。デフォルト値は 0 で、再試行を行わないことを意味します。 </p> <p>再試行から次の再試行までの間に、2 秒間のスリープ間隔を置きます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**クライアントからの MMP エクスポートの生成**

1. クライアントから、ワークスペースを開き、**[!UICONTROL Tools]****[!UICONTROL Detail Table]**&#x200B;を右クリックします。
1. **レベル**&#x200B;を追加します。
1. ヘッダーを右クリックし、「**属性を追加**」を選択します。
1. ヘッダーを右クリックし、「**新しいマスターマーケティングプロファイルエクスポート**」を選択します。 ![](assets/mmp_mmp_export.png)
1. 「**Query**」を展開します。

   ![](assets/mmp_mmp_query.png)

1. 「**MMP Configuration**」を展開します。
1. （必須）「**MMP Segment Name**」と「**MMP Visitor ID Field**」を入力します。これらのパラメーターを空のままにすることはできません。
1. **MMP Segment Name** は、MMP で定義されているセグメント ID と一致する必要があります。
1. **MMP Visitor ID** は、手順 4 で定義した、**訪問者 ID** に対応する属性列です。
1. これらのフィールドに入力したら、エクスポートのヘッダーを右クリックし、「User\.export」として「**保存**」を選択して、エクスポートを保存できます。
1. **管理者**／**プロファイルマネージャー**&#x200B;を開き、エクスポートをプロファイルに保存します。

   すべてのデータを正しく入力している場合は、FSU にエクスポートファイル（[!DNL Server/Exports]）が生成され、さらに、[!DNL MMPExport.cfg] 内の情報を使用して、AWS にエクスポートが転送されます。このログは[!DNL Server/Trace/]に記録されています。 例： [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

```
Query = SegmentExportQuery: 
Command = string: ExportIntegration.exe 
Command Arguments = string: \"%file%.cfg\" \"%file%\" 
Filter = string: 
Level = string: Page View 
MMP Configuration = MMPConfiguration: 
MMP Segment Name = string: 12345 
MMP Visitor ID Field = string: Tracking ID 
Oneshot = bool: true 
Output Fields = vector: 3 items 
0 = ColumnDefinition: 
Column Name = string: 
Field Name = string: Tracking ID 
1 = ColumnDefinition: 
Column Name = string: 
Field Name = string: PID 
2 = ColumnDefinition: 
Column Name = string: 
Field Name = string: SID 
Output File = string: MMPTest.txt 
Output Format = string: %1%\t%2%\t%3%\r\n 
Schedule End Time = string: 
Schedule Every = string: 
Schedule Start Time = string: 
Time Limit (sec) = double: 1800 
```

| 設定の詳細 | 説明 |
|---|---|
| MMP Segment ID | 必須。これは、Audience Manager で最初に定義した識別子です。 |
| MMP Visitor ID Field | ECIDをマッピングします。 |
