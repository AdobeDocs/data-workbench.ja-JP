---
description: ネットワークファイアウォールが Insight マシンからリピーターサーバーにアクセスするのを防ぐことができない場合は、リピーターサーバーと Insight の間に接続を作成して、Insight を使用してリピーターサーバーを管理できます。
title: Insight とリピーターとの接続の作成
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 9%

---

# Insight とリピーターとの接続の作成{#creating-a-connection-between-insight-and-repeater}

{{eol}}

ネットワークファイアウォールが Insight マシンからリピーターサーバーにアクセスするのを防ぐことができない場合は、リピーターサーバーと Insight の間に接続を作成して、Insight を使用してリピーターサーバーを管理できます。

**次の間に接続を作成するには [!DNL Insight] およびリピータサーバ**

1. In [!DNL Insight]、 [!DNL Admin] タブで、 **[!UICONTROL Configure Connections to Servers]** 「サーバーへの接続を設定」ワークスペースを開くためのサムネール。
1. 内 [!DNL Insight.cfg] ウィンドウ、右クリック **[!UICONTROL Servers]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. 新しいサーバーに対して、次のパラメーターを設定します。

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> ... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2">（オプション）これを使用する名前です。 <span class="keyword"> Insight</span> を使用して、リピータサーバをユーザインターフェイスで表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> <p>リピーターサーバーのホスト名または数値 IP アドレス。 </p> <p>例： <span class="filepath"> Repeater.mycompany.com</span> または 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> <p>複数の証明書がある場合を除いてオプションです。このコピーの電子証明書を含むファイルの名前 <span class="keyword"> Insight</span>. ( これは、のインストール時にダウンロードしたファイルです。 <span class="keyword"> Insight</span>.) </p> <p>例：<span class="filepath">Samantha Smith.pem</span></p> <p>このパラメーターを空白のままにした場合、 <span class="keyword"> Insight</span> は、存在する証明書を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL サーバー </p> <p>共通名 </p> </td> 
   <td colname="col2">リピーターサーバーに割り当てられる共通名。 この名前は、ライセンス証明書内でリピーターサーバーに割り当てられている共通名と一致する必要があります。 リピーターの証明書ファイル (<span class="filepath"> Certificates\server_cert.pem</span>を参照 )、メモ帳などのテキストエディターでファイルを開くと、共通名を見つけることができます。 共通名は、証明書の CN フィールドで識別されます。 </td> 
  </tr> 
 </tbody> 
</table>

1. 右クリックしてファイルを保存 **[!UICONTROL (modified)]** をクリックし、 **[!UICONTROL Save]**. [!DNL Insight] 指定した設定を使用して、リピーターサーバへの接続が試みられます。 接続が確立されると、緑色のサーバアイコンが [!DNL Servers Manager] インターフェイス。 接続を確立できない場合は、赤いアイコンが表示されます。

   詳しくは、 [!DNL Servers Manager] インターフェイスに関しては、* [!DNL Insight] ユーザーガイド*。
