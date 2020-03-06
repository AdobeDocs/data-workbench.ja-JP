---
description: Sensorは、サーバー上で使用する場合、有効なHTTPリクエストまたは応答ヘッダー、またはサーバーのAPIを通じて使用できる変数からイベントデータのフィールドを収集できます。
solution: Insight
title: 拡張可能フィールド
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 拡張可能フィールド{#extensible-fields}

Sensorは、サーバー上で使用する場合、有効なHTTPリクエストまたは応答ヘッダー、またはサーバーのAPIを通じて使用できる変数からイベントデータのフィールドを収集できます。

こうしたデータフィールドを収集するには、[!DNL txlogd.conf] の [!DNL Sensor] 設定ファイルに目的のヘッダーフィールドまたは変数を指定する必要があります。

* [リクエストヘッダー](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [サーバー変数](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## リクエストヘッダー {#section-22766692b45546d8bfc93dbe3bc9368f}

収集するリクエストヘッダーフィールド（Host、Accept-Encoding、Keep-Aliveなど）を指定する構文を次に示します [!DNL txlogd.conf]。

```
LogHeader RequestHeaderName
```

収集されたデータは、によって [!DNL Sensor] 作成されたファイル内の「cs(RequestHeaderName)」という名前のフィールドに [!DNL .vsl] 記録されま [!DNL data workbench server]す。 例えば、リクエストヘッダー「Host」から特定のリクエストヘッダー値を収集するには、に「LogHeader Host」と入力します [!DNL txlogd.conf]。 データは、イベントデータレコードの「cs(Host)」フィールドに記録されます。

## サーバー変数 {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] は、ファイルに含めるSpecialLogFieldエントリを使用して、応答ヘッダーまたはAPIアクセス可能なサーバー変数からデータのフィールドを収集で [!DNL txlogd.conf] きます。 また、「LogHeader」エントリに加えて、または「LogHeader」エントリの代わりに「SpecialLogField」エントリを使用して、リクエストヘッダーを収集することもできます。 リクエストヘ [ッダーを参照してくださ](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)い。 リクエストヘッダーオプションは、後方互換性を維持するために引き続き使用できます。

次に、「SpecialLogField」を指定する構文を示します [!DNL txlogd.conf]。

```
SpecialLogField cs(log field) = serverVariable stage
```

次の表に、「SpecialLogField」エントリのコンポーネントの説明を示します。

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
   <td colname="col2"> 収集したデータがイベントデータレコードと、Data Workbenchサーバーによって作成された <span class="filepath"> .vsl </span> ファイルに記録されるフ <span class="keyword"> ィールドの名前 </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>サーバーのAPIを通じて <span class="wintitle"> Sensorで使 </span> 用できる任意のサーバー変数 </p> <p>例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_logまたはvys_cookie </p> <p>ステージを指定するには、vys_logとvys_cookieに使用できるサーバ変数を知っている必要があります。 </p> <p>例：serverVariable response.p3pの場合、vys_logと入力します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

拡張可能なイベントデー [!DNL Sensor] タレコードフィールドを収集するための設定に関しては、アドビのコンサルティングサービスにお問い合わせください。
