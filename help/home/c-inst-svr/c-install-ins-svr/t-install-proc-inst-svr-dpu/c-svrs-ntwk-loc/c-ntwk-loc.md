---
description: 概念的には、アドレスファイルは、ネットワーク化されたマシン上のETC\HOSTSファイルと同じ目的を果たします。
solution: Insight
title: ネットワークの場所
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ネットワークの場所{#network-locations}

概念的には、アドレスファイルは、ネットワーク化されたマシン上のETC\HOSTSファイルと同じ目的を果たします。

ただし、名前の単一のコレクションを記述するHOSTSファイルとは異なり、アドレスファイルにはネットワークロケーションと呼ばれる複数の名前のコレクションが含まれます。

ネットワークの場所は、アドレス定義の名前付きのコレクションです。 コレクション内の各アドレス定義は、共通名とIPアドレスを関連付けます。

アドレスファイルでは、NetworkLocationと呼ばれる構造体でネットワークの場所が定義されます。 次の例のNetworkLocationは、「MyCorporate Intranet」という名前のネットワークの場所を定義します。共通名をIPアドレス「10.2.1.70」 [!DNL VS01.myCompany.com] にマップするアドレス定義が含まれます。

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

上の例で示したように、NetworkLocation構造は3つの主要なパラメーターで構成されます。

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
   <td colname="col2"> 0個以上のAddressDefinitionsを定義します。 各AddressDefinionは、共通名をIPアドレスに関連付けます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> NetworkLocationに名前を割り当てます。 NetworkLocationに割り当てる名前は、アドレスファイル内で一意である必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p>このNetworkLocationに含まれるメンバの別のNetworkLocationの名前を指定します。 このパラメーターは、あるNetworkLocationを別のNetworkLocationに拡張することを有効にします。 </p> <p>Parentパラメーターを「DNS」に設定して、NetworkLocationをクライアントの通常のDNSシステムに拡張できます。 </p> <p>例：親=文字列：DNS </p> <p>DNSが親の場合、クライアントはNetworkLocationを通じて名前を解決できない場合、クライアントコンピューターのDNSシステムを使用して共通名の解決を試みます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

