---
description: 概念上、アドレスファイルは、ネットワーク上のマシン上のETC&bsol;HOSTSファイルと同じ目的を果たします。
title: ネットワーク位置
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
exl-id: 938217da-8935-4f2a-b5f8-9afc1dd489f3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 3%

---

# ネットワーク位置{#network-locations}

概念上、アドレスファイルは、ネットワーク上のマシン上のETC&amp;bsol;HOSTSファイルと同じ目的を果たします。

ただし、名前の単一のコレクションを記述するHOSTSファイルとは異なり、アドレスファイルにはネットワークロケーションと呼ばれる複数の名前のコレクションが含まれます。

ネットワークの場所は、アドレス定義の名前付きコレクションです。 コレクションの各アドレス定義は、共通名をIPアドレスに関連付けます。

アドレスファイルでは、ネットワークの場所はNetworkLocationと呼ばれる構造で定義されます。 次の例のNetworkLocationは、「MyCorporate Intranet」という名前のネットワークの場所を定義します。 IPアドレス10.2.1.70に共通名[!DNL VS01.myCompany.com]をマッピングするアドレス定義が含まれます。

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

上の例で示すように、NetworkLocation構造は、次の3つの主要なパラメーターで構成されます。

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
   <td colname="col2"> 0個以上のAddressDefinitionsを定義します。 各AddressDefinitionは、共通名をIPアドレスに関連付けます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> NetworkLocationに名前を割り当てます。 NetworkLocationに割り当てる名前は、アドレスファイル内で一意である必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p>このNetworkLocationにメンバが含まれる別のNetworkLocationの名前を指定します。 このパラメーターは、1つのNetworkLocationが別のNetworkLocationを拡張することを可能にします。 </p> <p>Parentパラメーターを「DNS」に設定して、NetworkLocationをクライアントの通常のDNSシステムに拡張できます。 </p> <p>例：親=文字列：DNS </p> <p>DNSが親の場合、クライアントは、NetworkLocationを介して名前を解決できない場合、クライアントコンピューターのDNSシステムを使用して共通名を解決しようとします。 </p> </td> 
  </tr> 
 </tbody> 
</table>
