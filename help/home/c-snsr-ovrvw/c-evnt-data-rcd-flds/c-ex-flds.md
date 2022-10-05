---
description: センサーをサーバーで使用すると、は、サーバーの API を通じて有効な HTTP リクエストまたは応答ヘッダー、または変数からイベントデータのフィールドを収集できます。
title: 拡張可能なフィールド
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 8%

---

# 拡張可能なフィールド{#extensible-fields}

{{eol}}

センサーをサーバーで使用すると、は、サーバーの API を通じて有効な HTTP リクエストまたは応答ヘッダー、または変数からイベントデータのフィールドを収集できます。

こうしたデータフィールドを収集するには、[!DNL txlogd.conf] の [!DNL Sensor] 設定ファイルに目的のヘッダーフィールドまたは変数を指定する必要があります。

* [リクエストヘッダー](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [サーバー変数](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## リクエストヘッダー {#section-22766692b45546d8bfc93dbe3bc9368f}

収集するリクエストヘッダーフィールド（例えば、ホスト、Accept-Encoding、Keep-Alive など）を指定する構文を次に示します。 [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

収集したデータは、 [!DNL Sensor] を [!DNL .vsl] が作成したファイル [!DNL data workbench server]. 例えば、リクエストヘッダー「Host」から特定のリクエストヘッダー値を収集するには、「LogHeader Host」と入力します。 [!DNL txlogd.conf]. データは、イベントデータレコードの「cs(Host)」フィールドに記録されます。

## サーバー変数 {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] では、 [!DNL txlogd.conf] ファイル。 また、「LogHeader」エントリに加えて、またはの代わりに、「SpecialLogField」エントリを使用して、リクエストヘッダーを収集することもできます。 詳しくは、 [リクエストヘッダー](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). リクエストヘッダーオプションは、後方互換性を確保するために引き続き使用できます。

次に、 [!DNL txlogd.conf]:

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
   <td colname="col1"> cs（log フィールド） </td> 
   <td colname="col2"> イベントデータレコードと <span class="filepath"> .vsl </span> が作成したファイル <span class="keyword"> data workbench サーバー </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>使用可能な任意のサーバー変数 <span class="wintitle"> センサー </span> サーバーの API を通じて </p> <p>例：response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>vys_log または vys_cookie </p> <p>ステージを指定するには、vys_log と vys_cookie に使用できるサーバ変数を把握しておく必要があります。 </p> <p>例：serverVariable response.p3p の場合、 vys_log と入力します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

設定に関するヘルプ [!DNL Sensor] 拡張可能なイベントデータレコードフィールドを収集するには、Adobeコンサルティングサービスにお問い合わせください。
