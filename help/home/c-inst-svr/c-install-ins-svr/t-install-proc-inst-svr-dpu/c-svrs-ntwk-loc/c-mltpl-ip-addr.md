---
description: クライアントが複数のネットワーク（例えば、企業のイントラネットやインターネット経由）を介してInsightサーバーにアクセスできる場合、アドレスファイルでは、サーバーのIPアドレスごとに別々のネットワークの場所を定義する必要があります。
solution: Analytics
title: Insight サーバーの複数の IP アドレス
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---


# Insight サーバーの複数の IP アドレス{#multiple-ip-addresses-for-an-insight-server}

クライアントが複数のネットワーク（例えば、企業のイントラネットやインターネット経由）を介してInsightサーバーにアクセスできる場合、アドレスファイルでは、サーバーのIPアドレスごとに別々のネットワークの場所を定義する必要があります。

例えば、サーバーのIPアドレス [!DNL VS01.myCompany.com] が内部ネットワーク上で10.2.1.70で、IPアドレスがインターネット上で65.196.125.167の場合、アドレスファイルには、次の例に示すように、各アドレスのネットワーク位置が含まれます。

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

ユーザーがサーバーに接続する際 [!DNL Insight Server]、（クライアントユーザーインターフェイスの）NetworkLocationパラメーターを使用して、サーバーの共通名を解決するネットワークの場所を指定します。 例えば、上に示した2つのNetworkLocationsを持つアドレスファイルを指定した場合、ユーザーはNetworkLocationパラメーターを「MyCorporate Intranet」に設定して内部ネットワーク経由で接続し、「Internet」に設定してインターネット経由でサーバーに接続します。 [!DNL Insight Server]
