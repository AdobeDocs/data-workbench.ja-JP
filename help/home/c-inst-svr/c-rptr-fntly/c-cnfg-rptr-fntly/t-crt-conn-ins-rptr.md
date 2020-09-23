---
description: ネットワークファイアウォールがInsightマシンからリピーターサーバーにアクセスできない場合は、リピーターサーバーとInsightの間に接続を作成して、Insightを使用してリピーターサーバーを管理できます。
solution: Analytics
title: Insight とリピーターとの接続の作成
uuid: dccce83a-8708-4763-a19a-64d905a9f624
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 9%

---


# Insight とリピーターとの接続の作成{#creating-a-connection-between-insight-and-repeater}

ネットワークファイアウォールがInsightマシンからリピーターサーバーにアクセスできない場合は、リピーターサーバーとInsightの間に接続を作成して、Insightを使用してリピーターサーバーを管理できます。

**リピータサーバとの接続[!DNL Insight]を作成するには**

1. で、 [!DNL Insight]タブの [!DNL Admin]**[!UICONTROL Configure Connections to Servers]** サムネールをクリックして、サーバーへの接続を設定ワークスペースを開きます。
1. ウィンドウで右クリックし、「 [!DNL Insight.cfg] >」 **[!UICONTROL Servers]** をクリックし **[!UICONTROL Add new]** ま **[!UICONTROL Server]**&#x200B;す。
1. 新しいサーバーに対して、次のパラメーターを入力します。

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
   <td colname="col2">（オプション）この <span class="keyword"> Insightのユーザーインターフェイスでリピーターサーバーを表すために使用する名前</span> 。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> <p>リピータサーバのホスト名または数値のIPアドレス。 </p> <p>例： <span class="filepath"> Repeater.mycompany.com</span> または192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> <p>複数の証明書がある場合を除いてオプションです。The name of the file that contains the digital certificate for this copy of <span class="keyword"> Insight</span>. (これは、 <span class="keyword"> Insightのインストール時にダウンロードしたファイルです</span>)。 </p> <p>例：<span class="filepath">Samantha Smith.pem</span></p> <p>If you leave this parameter blank, <span class="keyword"> Insight</span> uses whatever certificate is present. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Server </p> <p>共通名 </p> </td> 
   <td colname="col2">リピータサーバに割り当てられる共通名。 この名前は、ライセンス証明書内のリピータサーバに割り当てられている共通名と一致する必要があります。 リピーターの証明書ファイル(<span class="filepath"> Certificates\server_cert.pem</span>)にアクセスできる場合は、メモ帳などのテキストエディターを使用してファイルを開くと、共通名が見つかります。 共通名は、証明書のCNフィールドで識別されます。 </td> 
  </tr> 
 </tbody> 
</table>

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**. [!DNL Insight] は、指定した設定を使用してリピーターサーバーに接続を試みます。 接続が確立されると、インター [!DNL Servers Manager] フェイスに緑のサーバーアイコンが表示されます。 接続を確立できない場合は、赤いアイコンが表示されます。

   For more information about the [!DNL Servers Manager] interface, see the * [!DNL Insight] User Guide*.

