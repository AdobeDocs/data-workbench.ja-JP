---
description: 概念上、アドレスファイルは、ネットワーク上の ETC&bsol;HOSTS ファイルと同じ目的を果たします。
title: ネットワーク位置
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
exl-id: 938217da-8935-4f2a-b5f8-9afc1dd489f3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 3%

---

# ネットワーク位置{#network-locations}

{{eol}}

概念上、アドレスファイルは、ネットワーク上の ETC&amp;bsol;HOSTS ファイルと同じ目的を果たします。

ただし、名前の 1 つのコレクションを表す HOSTS ファイルとは異なり、アドレスファイルには、ネットワークの場所と呼ばれる複数の名前のコレクションが含まれます。

ネットワークの場所は、アドレス定義の名前付きのコレクションです。 コレクションの各アドレス定義は、共通名と IP アドレスを関連付けます。

アドレスファイルでは、NetworkLocation と呼ばれる構造でネットワークの場所が定義されます。 次の例の NetworkLocation は、「MyCorporate Intranet」という名前のネットワークの場所を定義します。 共通名をマッピングするアドレス定義が含まれます [!DNL VS01.myCompany.com] を IP アドレス「10.2.1.70」に追加します。

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

上記の例で示すように、NetworkLocation 構造は、次の 3 つの主要なパラメーターで構成されます。

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> アドレス </td> 
   <td colname="col2"> 0 個以上の AddressDefinitions を定義します。 各 AddressDefinition は、共通名を IP アドレスに関連付けます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> NetworkLocation に名前を割り当てます。 NetworkLocation に割り当てる名前は、アドレスファイル内で一意である必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p>この NetworkLocation にメンバが含まれる別の NetworkLocation の名前を指定します。 このパラメータは、ある NetworkLocation が別の NetworkLocation を拡張できるようにします。 </p> <p>NetworkLocation をクライアントの通常の DNS システムに拡張するには、Parent パラメータを"DNS"に設定します。 </p> <p>例：親=文字列：DNS </p> <p>DNS が親の場合、クライアントは NetworkLocation を介して名前を解決できない場合に、クライアントコンピュータの DNS システムを使用して共通名を解決しようとします。 </p> </td> 
  </tr> 
 </tbody> 
</table>
