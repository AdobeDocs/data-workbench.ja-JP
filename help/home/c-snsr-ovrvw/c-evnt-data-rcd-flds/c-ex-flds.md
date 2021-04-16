---
description: Sensorは、サーバー上で使用する場合、有効なHTTPリクエストまたは応答ヘッダー、またはサーバーのAPI経由で利用可能な変数からイベントデータのフィールドを収集できます。
title: 拡張可能なフィールド
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 7%

---

# 拡張可能なフィールド{#extensible-fields}

Sensorは、サーバー上で使用する場合、有効なHTTPリクエストまたは応答ヘッダー、またはサーバーのAPI経由で利用可能な変数からイベントデータのフィールドを収集できます。

こうしたデータフィールドを収集するには、[!DNL txlogd.conf] の [!DNL Sensor] 設定ファイルに目的のヘッダーフィールドまたは変数を指定する必要があります。

* [リクエストヘッダー](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [サーバー変数](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## 要求ヘッダー{#section-22766692b45546d8bfc93dbe3bc9368f}

[!DNL txlogd.conf]で収集するリクエストヘッダーフィールド（Host、Accept-Encoding、Keep-Aliveなど）を指定するための構文を次に示します。

```
LogHeader RequestHeaderName
```

収集されたデータは、[!DNL Sensor]によって、[!DNL data workbench server]によって作成された[!DNL .vsl]ファイル内の&quot;cs(RequestHeaderName)&quot;というフィールドに記録されます。 例えば、リクエストヘッダー「Host」から特定のリクエストヘッダー値を収集するには、[!DNL txlogd.conf]に「LogHeader Host」と入力します。 データは、イベントデータレコード内のフィールド「cs(Host)」に記録されます。

## サーバー変数{#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] は、 [!DNL txlogd.conf] ファイルに含めるSpecialLogFieldエントリを使用して、応答ヘッダーまたはAPIアクセス可能なサーバー変数からデータのフィールドを収集できます。「LogHeader」エントリに加えて、または「LogHeader」エントリの代わりに「SpecialLogField」エントリを使用して、リクエストヘッダーを収集することもできます。 「[リクエストヘッダー](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)」を参照してください。 リクエストヘッダーオプションは、後方互換性を維持するために使用できます。

次に、[!DNL txlogd.conf]で「SpecialLogField」を指定する構文を示します。

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
   <td colname="col2"> 収集したデータがイベントデータレコードに記録されるフィールドの名前、および<span class="keyword"> data workbenchサーバー</span>によって作成された<span class="filepath"> .vsl </span>ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p><span class="wintitle"> Sensor </span>がサーバーのAPIを介して使用できるサーバー変数 </p> <p>例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_logまたはvys_cookie </p> <p>ステージを指定するには、vys_logとvys_cookieに使用できるサーバ変数を知っている必要があります。 </p> <p>例：serverVariable response.p3pの場合、vys_logと入力します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

拡張可能なイベントデータレコードフィールドを収集するための[!DNL Sensor]の設定については、Adobeコンサルティングサービスにお問い合わせください。
