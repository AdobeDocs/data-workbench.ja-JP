---
description: センサーは、サーバー上で使用する場合、有効なHTTPリクエストヘッダーや応答ヘッダー、またはサーバーのAPIを通じてイベントデータのフィールドを収集できます。
title: 拡張可能なフィールド
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 7%

---

# 拡張可能なフィールド{#extensible-fields}

センサーは、サーバー上で使用する場合、有効なHTTPリクエストヘッダーや応答ヘッダー、またはサーバーのAPIを通じてイベントデータのフィールドを収集できます。

こうしたデータフィールドを収集するには、[!DNL txlogd.conf] の [!DNL Sensor] 設定ファイルに目的のヘッダーフィールドまたは変数を指定する必要があります。

* [リクエストヘッダー](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [サーバー変数](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## リクエストヘッダー{#section-22766692b45546d8bfc93dbe3bc9368f}

[!DNL txlogd.conf]で収集するリクエストヘッダーフィールド（例えば、ホスト、Accept-Encoding、Keep-Aliveなど）を指定する構文を次に示します。

```
LogHeader RequestHeaderName
```

収集されたデータは、[!DNL Sensor]によって、[!DNL data workbench server]によって作成された[!DNL .vsl]ファイルの「cs(RequestHeaderName)」フィールドに記録されます。 例えば、リクエストヘッダー「Host」から特定のリクエストヘッダー値を収集するには、[!DNL txlogd.conf]に「LogHeader Host」と入力します。 データは、イベントデータレコードの「cs(Host)」フィールドに記録されます。

## サーバー変数{#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] では、ファイルに含めるSpecialLogFieldエントリを使用して、応答ヘッダーやAPIでアクセス可能なサーバー変数からデータのフィールドを収集 [!DNL txlogd.conf] できます。また、「LogHeader」エントリに加えて、またはの代わりに「SpecialLogField」エントリを使用して、要求ヘッダーを収集することもできます。 [リクエストヘッダー](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)を参照してください。 リクエストヘッダーオプションは、後方互換性を維持するために使用できます。

[!DNL txlogd.conf]で「SpecialLogField」を指定する構文を次に示します。

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
   <td colname="col2"> 収集したデータがイベントデータレコードに記録されるフィールドの名前と、 <span class="keyword"> data workbenchサーバー</span>によって作成された<span class="filepath"> .vsl </span>ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>サーバーのAPIを介して<span class="wintitle"> Sensor </span>で使用できるサーバー変数 </p> <p>例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ステージ </td> 
   <td colname="col2"> <p>vys_logまたはvys_cookie </p> <p>ステージを指定するには、vys_logとvys_cookieに使用できるサーバー変数を把握しておく必要があります。 </p> <p>例：serverVariable response.p3pの場合、 vys_logと入力します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

拡張可能なイベントデータレコードフィールドを収集するための[!DNL Sensor]の設定については、Adobeコンサルティングサービスにお問い合わせください。
