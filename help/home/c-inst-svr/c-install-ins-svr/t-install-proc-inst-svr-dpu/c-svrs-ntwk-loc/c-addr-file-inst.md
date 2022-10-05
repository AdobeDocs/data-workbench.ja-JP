---
description: Insight サーバーにインストールされるアドレスファイルには、事前に定義された 4 つのネットワーク位置が含まれています。
title: Insight サーバーにインストールされるアドレスファイル
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---

# Insight サーバーにインストールされるアドレスファイル{#the-address-file-installed-on-insight-server}

{{eol}}

Insight サーバーにインストールされるアドレスファイルには、事前に定義された 4 つのネットワーク位置が含まれています。

次の節の手順では、このファイルの設定方法について説明します。

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

* NetworkLocation 0 は空で名前のないネットワークの場所で、この場所を編集して、 [!DNL Insight Server] を IP アドレスに追加します。 サーバーに複数の IP アドレスがある場合は、追加の NetworkLocations を作成します。
* NetworkLocation 1 は [!DNL Insight] ネットワークの場所。 NetworkLocation パラメーターを明示的に設定しない場合は、 [!DNL Insight] は、このネットワークの場所を使用して共通名を解決します。

* NetworkLocation 2 は [!DNL Insight Server] ネットワークの場所。 条件 [!DNL Insight Servers] クラスタで動作し、このネットワークの場所を使用して、サーバ間通信の共通名を解決します。

* NetworkLocation 3 は [!DNL Report] サーバーのネットワークの場所。 NetworkLocation パラメーターを明示的に設定しない場合は、 [!DNL Report] は、このネットワークの場所を使用して共通名を解決します。

## アドレスファイルを設定するには {#section-10caab9854a244e39b09071946f7bd27}

次の手順では、アドレスファイルを設定して、ユーザーのネットワークの場所（またはネットワークの場所）を定義する方法について説明します [!DNL Insight Server].

1. 次に移動： [!DNL Addresses] をインストールしたディレクトリ内のフォルダー [!DNL Insight Server] ( 例： [!DNL C:\Adobe\Server\Addresses)].

1. を [!DNL server.address] ファイルの名前を変更し、サーバーの共通名を反映するようにこのファイルの名前を変更します。 例えば、共通名が [!DNL server.mycompany.com]の場合は、ファイル名を変更します [!DNL server.mycompany.com.address].

1. 名前を変更したファイルをメモ帳などのテキストエディターで開きます。
1. NetworkLocation 0 を編集して、 [!DNL Insight Server] 以下に示すように。 サーバーに複数の IP アドレスがある場合は、NetworkLocation 0 を使用して、ローカルでルーティング不可能なネットワーク上でのサーバーの IP アドレス（内部ネットワーク上での場所など）を指定します。

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
   <td colname="col2"> <p>の IP アドレス（数値） <span class="keyword"> Insight サーバー </span> マシン。 </p> <p>例：192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>共通名 </i> </td> 
   <td colname="col2"> <p>の電子証明書に割り当てられた共通名 <span class="keyword"> Insight サーバー </span>. </p> <p>例： <span class="filepath"> server.mycompany.com </span></p> <p>注意：この名前は、証明書に表示されるとおりに必ず入力してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>ネットワークの場所名 </i> </td> 
   <td colname="col2"> <p>この NetworkLocation が表す共通名と IP アドレスのコレクションに割り当てる名前を指定します。 名前は、アドレスファイル内で一意である必要があります。 </p> <p>例：企業イントラネット </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 次に、 [!DNL Insight Server] には、追加の IP アドレスがある場合は、各アドレスに対して追加の NetworkLocation を作成します。 （簡単な方法は、上で作成した NetworkLocation のコピーを作成し、コピー内の IP アドレスを更新することです）。

   新しい NetworkLocation をアドレスファイルの末尾に追加するか、既存の NetworkLocation 定義の間に挿入することができます。 ( アドレスファイル内の NetworkLocation の位置は重要ではありません。しかし、 [!DNL Insight], [!DNL Insight Server]、および [!DNL Report] サーバーの NetworkLocations は通常、ファイルの末尾に配置されます )。

   必要な NetworkLocations を追加したら、次の手順を実行してファイル内の項目の番号を変更します。

   1. ロケーション構造の項目数を更新し、ファイル内の NetworkLocation 定義の合計数と一致させます。 例えば、ファイルに 4 つの NetworkLocation 定義が含まれている場合、Locations 行は次のようになります。

      ```
      Locations = vector: 4 items
      ```

   1. NetworkLocations の項目番号を更新し、NetworkLocations に連続番号を付けます（0 から始まります）。
   例えば、 [!DNL Insight Server] 2 つの IP アドレスを使用する場合は、この節の例を参照してください。

1. 内 [!DNL Insight] および [!DNL Report] サーバーのネットワーク位置を編集する場合は、次に示すように Parent パラメータを編集して、 [!DNL Insight] および [!DNL Report] をデフォルトのネットワーク位置として使用します。 （Parent パラメーターの設定時の表示の例については、この節の例を参照してください）。

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

   次に、 [!DNL Insight Server] には単一の IP アドレスがあるため、NetworkLocation は 1 つだけです。Parent パラメータは、その NetworkLocation を指します。 次に、 [!DNL Insight Server] に複数の IP アドレスがある場合は、Parent パラメーターに、NetworkLocation で指定したアドレスを指定します [!DNL Insight] および [!DNL Report] クライアントは最も頻繁に接続します。

1. 内 [!DNL Insight Server] ネットワークの場所、次に示すように Parent パラメータを編集し、サーバーが他のの共通名を解決するために使用する NetworkLocation を指すようにします [!DNL Insight Servers] クラスター内で動作する場合。 ( ただし、このネットワークの場所は [!DNL Insight Server] クラスター内で動作する場合は、単一のサーバー設定でも、Parent パラメーターにサーバーの内部 IP アドレスを識別するネットワークの場所を指定することをお勧めします。)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

次の例は、完成したアドレスファイルを示しています。 このファイルは、5 つのネットワークの場所を定義します。

* NetworkLocation 項目 0 と 1 は、「MyCorporateIntranet」と「Internet」という名前のネットワークの場所を定義します。 これらのネットワークの場所は、次の名前を持つサーバーの 2 つの異なる IP アドレスを定義します [!DNL VS01.myCompany.com].
* NetworkLocation 項目 2 は [!DNL Insight] ネットワークの場所。 これは、 [!DNL Insight]. この例では、 [!DNL Insight] ネットワークの場所は、「インターネット」の NetworkLocation から AddressDefinitions を継承します。

* NetworkLocation 項目 3 は [!DNL Insight Server] ネットワークの場所。 これは既定のネットワークの場所です [!DNL Insight Server] は、クラスター内の他のサーバーと通信する際にを使用します。 この例では、 [!DNL Insight Server] ネットワークの場所は、「MyCorporate Intranet」NetworkLocation から AddressDefinitions を継承します。

* NetworkLocation 項目 4 は [!DNL Report] サーバーのネットワークの場所。 これは、 [!DNL Report]. この例では、 [!DNL Report] サーバのネットワークの場所は、&quot;Internet&quot;の NetworkLocation から AddressDefinitions を継承します。

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
