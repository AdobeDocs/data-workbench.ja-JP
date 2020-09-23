---
description: Insightサーバーにインストールされるアドレスファイルには、4つの定義済みのネットワークの場所が含まれています。
solution: Analytics
title: Insight サーバーにインストールされるアドレスファイル
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---


# Insight サーバーにインストールされるアドレスファイル{#the-address-file-installed-on-insight-server}

Insightサーバーにインストールされるアドレスファイルには、4つの定義済みのネットワークの場所が含まれています。

次の節の手順では、このファイルを設定する方法を説明します。

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0は、IPアドレスにの共通名を関連付けるために編集する、空の名前のないネットワークの場所 [!DNL Insight Server] です。 サーバーに複数のIPアドレスがある場合は、NetworkLocationsを追加作成します。
* NetworkLocation 1は、ネット [!DNL Insight] ワークの場所です。 NetworkLocationパラメーターを明示的に設定しない場合、は、このネットワークの場所を通じて共通名を [!DNL Insight] 解決します。

* NetworkLocation 2は、 [!DNL Insight Server] ネットワークの場所です。 クラスターで [!DNL Insight Servers] 動作する場合は、このネットワークの場所を使用して、サーバー間通信の共通名を解決します。

* NetworkLocation 3は、 [!DNL Report] サーバーのネットワークの場所です。 NetworkLocationパラメーターを明示的に設定しない場合、は、このネットワークの場所を通じて共通名を [!DNL Report] 解決します。

## アドレスファイルを設定するには {#section-10caab9854a244e39b09071946f7bd27}

次の手順では、アドレスファイルを構成して、のネットワークの場所（またはネットワークの場所）を定義する方法を説明し [!DNL Insight Server]ます。

1. インストールしたディレクトリ内の [!DNL Addresses] フォルダーに移動し [!DNL Insight Server] ます(例えば、 [!DNL C:\Adobe\Server\Addresses)])。

1. ファイルを探し、この [!DNL server.address] ファイルの名前を変更して、サーバーの共通名を反映します。 例えば、共通名がの場合 [!DNL server.mycompany.com]は、ファイル名を変更し [!DNL server.mycompany.com.address]ます。

1. 名前を変更したファイルをメモ帳などのテキストエディターで開きます。
1. NetworkLocation 0を編集し、次に示すように、の共通名とIPアドレス [!DNL Insight Server] を指定します。 サーバーに複数のIPアドレスがある場合は、NetworkLocation 0を使用して、ルーティング不可能なローカルネットワーク上のサーバーのIPアドレス（内部ネットワーク上のサーバーの場所など）を指定します。

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> この値の場合… </th> 
   <th colname="col2" class="entry">   </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>IP アドレス</i> </td> 
   <td colname="col2"> <p>Insightサーバーコンピューターの数値のIPアドレス <span class="keyword"> で </span> す。 </p> <p>例: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>共通名 </i> </td> 
   <td colname="col2"> <p>Insightサーバーのデジタル証明書に割り当てられる共通名 <span class="keyword"> で </span>す。 </p> <p>例： <span class="filepath"> server.mycompany.com </span></p> <p>注意：この名前は、証明書に表示されるとおりに入力してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>ネットワークの場所名 </i> </td> 
   <td colname="col2"> <p>このNetworkLocationが表す共通名とIPアドレスのコレクションに割り当てる名前です。 名前は、アドレスファイル内で一意である必要があります。 </p> <p>例：社内イントラネット </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 追加のIPアドレス [!DNL Insight Server] がある場合は、各アドレスに対してNetworkLocationを追加作成します。 （これを簡単に行うには、上記で作成したNetworkLocationのコピーを作成し、そのコピー内のIPアドレスを更新します）。

   新しいNetworkLocationは、アドレスファイルの末尾に追加するか、既存のNetworkLocation定義の間に挿入できます。 (アドレスファイル内でのNetworkLocationの位置は重要ではありません。ただし、 [!DNL Insight]、、 [!DNL Insight Server]および [!DNL Report] Server NetworkLocationsは、通常、ファイルの末尾に配置されます)。

   必要なNetworkLocationsを追加した後、次の手順を実行してファイル内の項目を再番号付けします。

   1. Locations構造の項目数を更新して、ファイル内のNetworkLocation定義の合計数と一致させます。 たとえば、ファイルに4つのNetworkLocation定義が含まれている場合、Locations行は次のようになります。

      ```
      Locations = vector: 4 items
      ```

   1. NetworkLocationsに連続番号が付けられるよう（0から始まる）に、NetworkLocation項目番号を更新します。
   2つのIPアドレスを持つアドレスを定義するアドレスファイルの例につ [!DNL Insight Server] いては、この節の例を参照してください。

1. お [!DNL Insight] よび [!DNL Report] サーバーのネットワークの場所で、次に示すようにParentパラメーターを編集して、NetworkLocationの名前を指定します。この名前は、デフォルトのネットワークの場所 [!DNL Insight] として [!DNL Report] 使用されます。 （Parentパラメーターを設定した場合の外観の例については、この節の例を参照してください）。

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
   
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   IPアドレス [!DNL Insight Server] が1つで、したがってNetworkLocationが1つだけの場合は、ParentパラメーターにそのNetworkLocationを指定します。 複数のIPアドレス [!DNL Insight Server] がある場合は、Parentパラメーターに、最も頻繁に接続するアドレスを定義するNetworkLocationを指定し [!DNL Insight] ま [!DNL Report] す。

1. ネットワークの場所で、次に示すようにParentパラメーターを編集し、クラスター内で動作している場合に、サーバーが他ののの共通名を解決するために使用するNetworkLocation [!DNL Insight Server][!DNL Insight Servers] を指し示します。 （このネットワークの場所は、クラスター内で動作しない限り使用しませんが、単一のサーバー設定でも、Parentパラメーターに、サーバーの内部IPアドレスを識別するネットワークの場所を示すことをお勧めします）。 [!DNL Insight Server]

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

次の例は、完了したアドレスファイルを示しています。 このファイルは、5つのネットワークの場所を定義します。

* NetworkLocation項目0と1は、「MyCorporateIntranet」および「Internet」という名前のネットワークの場所を定義します。 これらのネットワークの場所では、という名前のサーバーに対して2つの異なるIPアドレスを定義 [!DNL VS01.myCompany.com]します。
* NetworkLocation項目2は、ネット [!DNL Insight] ワークの場所です。 これは、で使用される既定のネットワークの場所で [!DNL Insight]す。 この例では、ネット [!DNL Insight] ワークの場所は、「インターネット」のNetworkLocationからAddressDefinitionsを継承します。

* NetworkLocation項目3は、ネット [!DNL Insight Server] ワークの場所です。 これは、クラスター内の他のサーバーと通信する場合に [!DNL Insight Server] 使用されるデフォルトのネットワークの場所です。 この例では、ネット [!DNL Insight Server] ワークの場所は、「MyCorporate Intranet」のNetworkLocationからAddressDefinitionsを継承します。

* NetworkLocation項目4は、 [!DNL Report] Serverのネットワークの場所です。 これは、で使用される既定のネットワークの場所で [!DNL Report]す。 この例では、サー [!DNL Report] バーのネットワークの場所は、「インターネット」のNetworkLocationからAddressDefinitionsを継承します。

   ```
   Locations = vector: 5 items 
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
   
     2 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight 
       Parent = string: Internet 
   
     3 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight Server 
       Parent = string: MyCorporateIntranet 
   
     4 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Report Server 
       Parent = string: Internet
   ```

