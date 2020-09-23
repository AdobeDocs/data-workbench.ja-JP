---
description: Sensorは、サーバー上で使用する場合、有効なHTTPリクエストまたは応答ヘッダー、またはサーバーのAPI経由で利用可能な変数からイベントデータのフィールドを収集できます。
solution: Analytics
title: 拡張可能なフィールド
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 7%

---


# 拡張可能なフィールド{#extensible-fields}

Sensorは、サーバー上で使用する場合、有効なHTTPリクエストまたは応答ヘッダー、またはサーバーのAPI経由で利用可能な変数からイベントデータのフィールドを収集できます。

こうしたデータフィールドを収集するには、[!DNL txlogd.conf] の [!DNL Sensor] 設定ファイルに目的のヘッダーフィールドまたは変数を指定する必要があります。

* [リクエストヘッダー](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [サーバー変数](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## リクエストヘッダー {#section-22766692b45546d8bfc93dbe3bc9368f}

収集するリクエストヘッダーフィールド（Host、Accept-Encoding、Keep-Aliveなど）を指定する構文を次に示し [!DNL txlogd.conf]ます。

```
LogHeader RequestHeaderName
```

収集されたデータは、によって作成さ [!DNL Sensor] れた [!DNL .vsl] ファイル内の「cs(RequestHeaderName)」というフィールドに記録され [!DNL data workbench server]ます。 例えば、リクエストヘッダー「Host」から特定のリクエストヘッダー値を収集するには、に「LogHeader Host」と入力し [!DNL txlogd.conf]ます。 データは、イベントデータレコード内のフィールド「cs(Host)」に記録されます。

## サーバー変数 {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] は、 [!DNL txlogd.conf] ファイルに含めるSpecialLogFieldエントリを使用して、応答ヘッダーまたはAPIアクセス可能なサーバー変数からデータのフィールドを収集できます。 「LogHeader」エントリに加えて、または「LogHeader」エントリの代わりに「SpecialLogField」エントリを使用して、リクエストヘッダーを収集することもできます。 詳しくは、 [リクエストヘッダーを参照してください](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)。 リクエストヘッダーオプションは、後方互換性を維持するために使用できます。

次に、 [!DNL txlogd.conf]

```
SpecialLogField cs(log field) = serverVariable stage
```

次の表に、「SpecialLogField」エントリのコンポーネントについて説明します。

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コンポーネント </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs（logフィールド） </td> 
   <td colname="col2"> 収集したデータがイベントデータレコードに記録されるフィールドの名前、および <span class="filepath"> Data Workbenchサーバーによって作成された </span> .vsl <span class="keyword"> ファイル </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>サーバーのAPI経由で <span class="wintitle"> Sensor </span> で使用できるサーバー変数 </p> <p>例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_logまたはvys_cookie </p> <p>ステージを指定するには、vys_logとvys_cookieに使用できるサーバ変数を知っている必要があります。 </p> <p>例：serverVariable response.p3pの場合、vys_logと入力します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

拡張可能なイベントデータレコードフィールド [!DNL Sensor] を収集するための設定については、Adobeコンサルティングサービスにお問い合わせください。
