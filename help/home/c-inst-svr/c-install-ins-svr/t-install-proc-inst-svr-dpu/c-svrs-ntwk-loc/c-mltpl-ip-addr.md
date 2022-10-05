---
description: クライアントが複数のネットワークを通じて Insight サーバーにアクセスできる場合（例えば、企業のイントラネットやインターネットを通じて）、アドレスファイルでサーバーの IP アドレスごとに別のネットワークの場所を定義する必要があります。
title: Insight サーバーの複数の IP アドレス
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
exl-id: 71654a60-af82-45f2-826b-29ecc7127b0b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Insight サーバーの複数の IP アドレス{#multiple-ip-addresses-for-an-insight-server}

{{eol}}

クライアントが複数のネットワークを通じて Insight サーバーにアクセスできる場合（例えば、企業のイントラネットやインターネットを通じて）、アドレスファイルでサーバーの IP アドレスごとに別のネットワークの場所を定義する必要があります。

例えば、サーバーの場合 [!DNL VS01.myCompany.com] の内部ネットワークの IP アドレスが 10.2.1.70 で、IP アドレスが 65.196.125.167 の場合、アドレスファイルには、次の例に示すように、各アドレスのネットワーク位置が含まれます。

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
1 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 65.196.125.167
      Name = string: VS01.myCompany.com
  Name = string: Internet
  Parent = string:
```

ユーザーが [!DNL Insight Server]を使用する場合は、（クライアントユーザーインターフェイスの）NetworkLocation パラメーターを使用して、サーバーの共通名を解決するネットワークの場所を指定します。 例えば、上記の 2 つの NetworkLocations を持つアドレスファイルを指定した場合、ユーザーは、NetworkLocation パラメーターを&quot;MyCorporate Intranet&quot;に設定して、 [!DNL Insight Server] 内部ネットワークを通じて、また「インターネット」に接続し、インターネットを通じてサーバーに接続します。
