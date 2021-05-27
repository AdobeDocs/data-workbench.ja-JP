---
description: Insightサーバーにインストールされるアドレスファイルには、4つの定義済みネットワークの場所が含まれています。
title: Insight サーバーにインストールされるアドレスファイル
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---

# Insight サーバーにインストールされるアドレスファイル{#the-address-file-installed-on-insight-server}

Insightサーバーにインストールされるアドレスファイルには、4つの定義済みネットワークの場所が含まれています。

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

* NetworkLocation 0は、[!DNL Insight Server]の共通名をIPアドレスに関連付けるために編集する、空の名前のないネットワークの場所です。 サーバーに複数のIPアドレスがある場合は、追加のNetworkLocationsを作成します。
* NetworkLocation 1は[!DNL Insight]ネットワークの場所です。 NetworkLocationパラメーターを明示的に設定しない場合、[!DNL Insight]は、このネットワークの場所を使用して共通名を解決します。

* NetworkLocation 2は、[!DNL Insight Server]ネットワークの場所です。 [!DNL Insight Servers]がクラスタで動作する場合、このネットワークの場所を使用して、サーバ間通信の共通名を解決します。

* NetworkLocation 3は、[!DNL Report]サーバのネットワークの場所です。 NetworkLocationパラメーターを明示的に設定しない場合、[!DNL Report]は、このネットワークの場所を使用して共通名を解決します。

## アドレスファイル{#section-10caab9854a244e39b09071946f7bd27}を設定するには

次の手順では、[!DNL Insight Server]のネットワークの場所（またはネットワークの場所）を定義するためのアドレスファイルの設定方法を説明します。

1. [!DNL Insight Server]をインストールしたディレクトリ内の[!DNL Addresses]フォルダーに移動します（例：[!DNL C:\Adobe\Server\Addresses)]）。

1. [!DNL server.address]ファイルを探し、サーバーの共通名を反映するようにこのファイル名を変更します。 例えば、共通名が[!DNL server.mycompany.com]の場合、ファイル名を[!DNL server.mycompany.com.address]に変更します。

1. 名前を変更したファイルをメモ帳などのテキストエディターで開きます。
1. NetworkLocation 0を編集して、[!DNL Insight Server]の共通名とIPアドレスを以下のように指定します。 サーバーに複数のIPアドレスがある場合は、NetworkLocation 0を使用して、ルーティング不可能なローカルネットワーク上でのサーバーのIPアドレス（内部ネットワーク上での場所など）を指定します。

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
   <th colname="col1" class="entry"> この値の場合 </th> 
   <th colname="col2" class="entry">   </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>IP アドレス</i> </td> 
   <td colname="col2"> <p><span class="keyword"> Insightサーバー</span>マシンの数値IPアドレス。 </p> <p>例: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>共通名  </i> </td> 
   <td colname="col2"> <p><span class="keyword"> Insightサーバー</span>のデジタル証明書に割り当てられる共通名。 </p> <p>例：<span class="filepath"> server.mycompany.com </span></p> <p>注意：この名前は、証明書に表示されるとおりに必ず入力してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>ネットワークの場所名  </i> </td> 
   <td colname="col2"> <p>このNetworkLocationが表す共通名とIPアドレスのコレクションに割り当てる名前を指定します。 名前は、アドレスファイル内で一意である必要があります。 </p> <p>例：企業イントラネット </p> </td> 
  </tr> 
 </tbody> 
</table>

1. [!DNL Insight Server]に追加のIPアドレスがある場合は、各アドレスに追加のNetworkLocationを作成します。 （これを行う簡単な方法は、上で作成したNetworkLocationのコピーを作成し、コピー内のIPアドレスを更新することです）。

   新しいNetworkLocationをアドレスファイルの末尾に追加するか、既存のNetworkLocation定義の間に挿入することができます。 (アドレスファイル内でのNetworkLocationの位置は重要ではありません。ただし、 [!DNL Insight] 、 [!DNL Insight Server] 、 [!DNL Report]サーバーのNetworkLocationsは通常、ファイルの最後に配置されます)。

   必要なNetworkLocationsを追加したら、次の手順を実行して、ファイル内の項目の番号を変更します。

   1. Locations構造の項目数を更新し、ファイル内のNetworkLocation定義の合計数と一致させます。 例えば、ファイルに4つのNetworkLocation定義が含まれている場合、Locations行は次のようになります。

      ```
      Locations = vector: 4 items
      ```

   1. NetworkLocationsに連続番号が付けられるように、NetworkLocation項目番号を更新します（0から始まります）。
   2つのIPアドレスを持つ[!DNL Insight Server]を定義するアドレスファイルの例については、この節の例を参照してください。

1. [!DNL Insight]と[!DNL Report]サーバーのネットワークの場所で、次に示すようにParentパラメーターを編集し、[!DNL Insight]と[!DNL Report]がデフォルトのネットワークの場所として使用するNetworkLocationの名前を指定します。 （ Parentパラメーターの設定時の表示例については、この節の例を参照してください）。

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

   [!DNL Insight Server]のIPアドレスが1つだけで、NetworkLocationが1つしかない場合は、そのNetworkLocationをParentパラメーターに指定します。 [!DNL Insight Server]に複数のIPアドレスがある場合は、[!DNL Insight]および[!DNL Report]クライアントが最も頻繁に接続するアドレスを定義するNetworkLocationをParentパラメーターに指定します。

1. [!DNL Insight Server]ネットワークの場所で、次に示すようにParentパラメーターを編集し、クラスター内で動作する際に、他の[!DNL Insight Servers]の共通名を解決するためにサーバーが使用するNetworkLocationを指すようにします。 （このネットワークの場所は、[!DNL Insight Server]がクラスターで動作しない限り使用しませんが、単一のサーバー設定でも、Parentパラメーターにサーバーの内部IPアドレスを識別するネットワークの場所を指定することをお勧めします）。

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

次の例は、完了したアドレスファイルを示しています。 このファイルは、5つのネットワークの場所を定義します。

* NetworkLocation項目0と1は、「MyCorporateIntranet」と「Internet」という名前のネットワークの場所を定義します。 これらのネットワークの場所は、[!DNL VS01.myCompany.com]という名前のサーバーに対して2つの異なるIPアドレスを定義します。
* NetworkLocation項目2は[!DNL Insight]ネットワークの場所です。 これは、[!DNL Insight]が使用するデフォルトのネットワークの場所です。 この例では、[!DNL Insight]ネットワークの場所は、「インターネット」NetworkLocationからAddressDefinitionsを継承します。

* NetworkLocation項目3は[!DNL Insight Server]ネットワークの場所です。 これは、クラスタ内の他のサーバと通信する際に[!DNL Insight Server]が使用するデフォルトのネットワークの場所です。 この例では、[!DNL Insight Server]ネットワークの場所は、「MyCorporate Intranet」NetworkLocationからAddressDefinitionsを継承します。

* NetworkLocation項目4は、[!DNL Report]サーバーのネットワークの場所です。 これは、[!DNL Report]が使用するデフォルトのネットワークの場所です。 この例では、[!DNL Report]サーバーのネットワーク位置は、「インターネット」のNetworkLocationからAddressDefinitionsを継承します。

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
