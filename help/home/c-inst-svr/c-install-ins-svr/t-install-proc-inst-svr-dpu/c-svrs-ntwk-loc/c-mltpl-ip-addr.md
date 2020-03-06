---
description: クライアントが複数のネットワーク（企業のイントラネットやインターネットなど）を介してInsightサーバーにアクセスできる場合、アドレスファイルで各サーバーのIPアドレスに対して別々のネットワークの場所を定義する必要があります。
solution: Insight
title: Insightサーバーの複数のIPアドレス
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insightサーバーの複数のIPアドレス{#multiple-ip-addresses-for-an-insight-server}

クライアントが複数のネットワーク（企業のイントラネットやインターネットなど）を介してInsightサーバーにアクセスできる場合、アドレスファイルで各サーバーのIPアドレスに対して別々のネットワークの場所を定義する必要があります。

例えば、サーバーの [!DNL VS01.myCompany.com] IPアドレスが内部ネットワーク上で10.2.1.70で、IPアドレスがインターネット上で65.196.125.167の場合、アドレスファイルには次の例に示すように、各アドレスのネットワークの場所が含まれます。

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

ユーザーがに接続する [!DNL Insight Server]と、クライアントユーザーインターフェイスのNetworkLocationパラメーターを使用して、サーバーの共通名を解決するネットワークの場所を指定します。 例えば、上に示した2つのNetworkLocationsを持つアドレスファイルを指定した場合、NetworkLocationパラメーターを「MyCorporate Intranet」に設定して内部ネットワーク経由で接続し、「 [!DNL Insight Server] Internet」に設定してインターネット経由でサーバーに接続します。
