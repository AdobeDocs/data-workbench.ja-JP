---
description: Insightサーバーにインストールされるアドレスファイルには、4つの事前定義済みのネットワークの場所が含まれています。
solution: Insight
title: Insightサーバーにインストールされるアドレスファイル
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insightサーバーにインストールされるアドレスファイル{#the-address-file-installed-on-insight-server}

Insightサーバーにインストールされるアドレスファイルには、4つの事前定義済みのネットワークの場所が含まれています。

次のセクションの手順で、このファイルを設定する方法を説明します。

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

* NetworkLocation 0は空の名前のないネットワークの場所で、IPアドレスにの共通名を関連付けるた [!DNL Insight Server] めに編集します。 サーバーに複数のIPアドレスがある場合は、追加のNetworkLocationsを作成します。
* NetworkLocation 1はネットワークの [!DNL Insight] 場所です。 NetworkLocationパラメーターを明示的に設定しない場合、はこのネットワークの場 [!DNL Insight] 所を通じて共通名を解決します。

* NetworkLocation 2は、ネットワーク [!DNL Insight Server] の場所です。 クラスタ [!DNL Insight Servers] ー内で動作する場合は、このネットワークの場所を使用して、サーバー間通信の共通名を解決します。

* NetworkLocation 3は、サーバーのネ [!DNL Report] ットワークの場所です。 NetworkLocationパラメーターを明示的に設定しない場合、はこのネットワークの場 [!DNL Report] 所を通じて共通名を解決します。

## アドレスファイルを設定するには {#section-10caab9854a244e39b09071946f7bd27}

次の手順では、アドレスファイルを設定して、のネットワークの場所（またはネットワークの場所）を定義する方法を説明しま [!DNL Insight Server]す。

1. をインストール [!DNL Addresses] したディレクトリ内のフォルダーに移 [!DNL Insight Server] 動します(例： [!DNL C:\Adobe\Server\Addresses)])。

1. ファイルを探 [!DNL server.address] し、サーバーの共通名を反映するようにこのファイルの名前を変更します。 例えば、共通名が次の場合は、フ [!DNL server.mycompany.com]ァイルの名前を変更しま [!DNL server.mycompany.com.address]す。

1. 名前を変更したファイルをメモ帳などのテキストエディターで開きます。
1. NetworkLocation 0を編集し、次に示すようにの共通名とIPアドレス [!DNL Insight Server] を指定します。 サーバーに複数のIPアドレスがある場合は、NetworkLocation 0を使用して、ルーティング不可能なローカルネットワーク上のサーバーのIPアドレス（内部ネットワーク上の場所など）を指定します。

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
   <th colname="col2" class="entry">     </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>IP アドレス</i> </td> 
   <td colname="col2"> <p>Insightサーバーコンピューターの <span class="keyword"> 数値のIPア </span> ドレス。 </p> <p>例: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>共通名 </i> </td> 
   <td colname="col2"> <p><span class="keyword"> Insightサーバーのデジタル証明書に割り当てられる共通名で </span>す。 </p> <p>例： <span class="filepath"> server.mycompany.com </span></p> <p>注意：この名前は、証明書に表示されるとおりに入力してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>ネットワークロケーション名 </i> </td> 
   <td colname="col2"> <p>このNetworkLocationが表す共通名とIPアドレスのコレクションに割り当てる名前。 名前は、アドレスファイル内で一意である必要があります。 </p> <p>例：企業のイントラネット </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 追加のIPアド [!DNL Insight Server] レスがある場合は、各アドレスに対して追加のNetworkLocationを作成します。 （簡単な方法は、上で作成したNetworkLocationのコピーを作成し、そのコピー内のIPアドレスを更新することです）。

   新しいNetworkLocationをアドレスファイルの末尾に追加するか、既存のNetworkLocation定義の間に挿入できます。 (アドレスファイル内のNetworkLocationの位置は重要ではありません。ただし、 [!DNL Insight]、、お [!DNL Insight Server]よびサー [!DNL Report] バーのNetworkLocationsは通常、ファイルの末尾に配置されます)。

   必要なNetworkLocationsを追加した後、次の手順を実行して、ファイル内の項目の番号を付け直します。

   1. Locations構造の項目数を、ファイル内のNetworkLocation定義の合計数と一致するように更新します。 例えば、ファイルに4つのNetworkLocation定義が含まれている場合、Locations行は次のようになります。

      ```
      Locations = vector: 4 items
      ```

   1. NetworkLocationの項目番号を更新し、NetworkLocationsに連続した番号が付けられるようにします（0から始まる）。
   2つのIPアドレスを持つアドレスを定義するア [!DNL Insight Server] ドレスファイルの例については、この節の例を参照してください。

1. およびサー [!DNL Insight] バのネッ [!DNL Report] トワークの場所で、次に示すようにParentパラメーターを編集し、既定のネットワークの場所として使用するNetworkLocation [!DNL Insight] の名 [!DNL Report] 前を指定します。 （Parentパラメーターの設定時の外観の例については、この節の例を参照してください）。

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

   1つのIPア [!DNL Insight Server] ドレスを持ち、そのためにNetworkLocationが1つだけの場合は、ParentパラメーターをそのNetworkLocationにポイントします。 複数のIPアド [!DNL Insight Server] レスがある場合は、ParentパラメーターをNetworkLocationに指定し、最も頻繁に接続するアドレスを [!DNL Insight] 定義 [!DNL Report] します。

1. ネットワーク [!DNL Insight Server] の場所で、次に示すようにParentパラメーターを編集し、クラスター内で動作している場合に、サーバーが他のサーバーの共通名を解決するために使用するNetworkLocation [!DNL Insight Servers] を指すように指定します。 （このネットワークの場所は、がクラスター内で動作しない限り使用されませんが、単一のサーバー設定でも、Parentパラメーターをサーバーの内部IPアドレスを識別するネットワークの場所に指定することをお勧めします）。 [!DNL Insight Server]

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

次の例は、完成したアドレスファイルを示しています。 このファイルは、5つのネットワークの場所を定義します。

* NetworkLocation項目0と1は、「MyCorporateIntranet」と「Internet」という名前のネットワークの場所を定義します。これらのネットワークの場所は、という名前のサーバーの2つの異なるIPアドレスを定義しま [!DNL VS01.myCompany.com]す。
* NetworkLocation項目2は、ネットワークの [!DNL Insight] 場所です。 これは、が使用する既定のネットワークの場所で [!DNL Insight]す。 この例では、ネットワークの場 [!DNL Insight] 所は、「インターネット」のNetworkLocationからAddressDefinitionsを継承します。

* NetworkLocation項目3は、ネットワーク [!DNL Insight Server] の場所です。 これは、クラスター内の他のサー [!DNL Insight Server] バーと通信する際に使用されるデフォルトのネットワークの場所です。 この例では、ネットワークの場 [!DNL Insight Server] 所は、「MyCorporate Intranet」のNetworkLocationからAddressDefinitionsを継承します。

* NetworkLocation項目4は、サーバーのネッ [!DNL Report] トワークの場所です。 これは、が使用する既定のネットワークの場所で [!DNL Report]す。 この例では、サーバーのネッ [!DNL Report] トワークの場所は、「インターネット」のNetworkLocationからAddressDefinitionsを継承します。

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

