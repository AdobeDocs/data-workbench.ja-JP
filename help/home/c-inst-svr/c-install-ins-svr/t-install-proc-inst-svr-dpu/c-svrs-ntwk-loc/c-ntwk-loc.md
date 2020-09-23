---
description: 概念的には、アドレスファイルは、ネットワーク接続されたマシン上のETC&bsol;HOSTSファイルと同じ目的を果たします。
solution: Analytics
title: ネットワーク位置
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 3%

---


# ネットワーク位置{#network-locations}

概念的には、アドレスファイルは、ネットワーク接続されたマシン上のETC&amp;bsol;HOSTSファイルと同じ目的を果たします。

ただし、名前の単一のコレクションを表すHOSTSファイルとは異なり、アドレスファイルにはネットワークロケーションと呼ばれる名前の集合が複数含まれます。

ネットワークの場所は、アドレス定義の名前付きコレクションです。 コレクション内の各アドレス定義は、共通名とIPアドレスを関連付けます。

アドレスファイルでは、NetworkLocationと呼ばれる構造体にネットワークの場所が定義されています。 次の例のNetworkLocationは、「MyCorporate Intranet」という名前のネットワークの場所を定義します。 共通名をIPアドレス「10.2.1.70」 [!DNL VS01.myCompany.com] にマップするアドレス定義が含まれます。

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

上の例に示すように、NetworkLocation構造は、3つの主なパラメーターで構成されています。

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 住所 </td> 
   <td colname="col2"> 0個以上のAddressDefinitionsを定義します。 各AddressDefinitionは、共通名をIPアドレスに関連付けます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> NetworkLocationに名前を割り当てます。 NetworkLocationに割り当てる名前は、アドレスファイル内で一意である必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p>このNetworkLocationにメンバが含まれる別のNetworkLocationの名前を指定します。 このパラメーターは、あるNetworkLocationで別のNetworkLocationを拡張できるようにします。 </p> <p>Parentパラメーターを"DNS"に設定して、NetworkLocationをクライアントの通常のDNSシステムに拡張できます。 </p> <p>例：Parent = string:DNS </p> <p>DNSが親の場合、クライアントはNetworkLocationを介して名前を解決できない場合に、クライアントコンピューターのDNSシステムを使用して共通名を解決しようとします。 </p> </td> 
  </tr> 
 </tbody> 
</table>
