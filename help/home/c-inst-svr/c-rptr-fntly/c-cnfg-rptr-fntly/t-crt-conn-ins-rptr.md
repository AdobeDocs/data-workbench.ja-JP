---
description: ネットワークファイアウォールがInsightコンピューターからリピーターサーバーへのアクセスを妨げない場合は、リピーターサーバーとInsightの間に接続を作成して、Insightを使用してリピーターサーバーを管理できます。
solution: Insight
title: Insightとリピーター間の接続の作成
uuid: dccce83a-8708-4763-a19a-64d905a9f624
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insightとリピーター間の接続の作成{#creating-a-connection-between-insight-and-repeater}

ネットワークファイアウォールがInsightコンピューターからリピーターサーバーへのアクセスを妨げない場合は、リピーターサーバーとInsightの間に接続を作成して、Insightを使用してリピーターサーバーを管理できます。

**リピータサーバとの間に接[!DNL Insight]続を作成するには**

1. で、タ [!DNL Insight]ブのサムネー [!DNL Admin] ルをクリックし **[!UICONTROL Configure Connections to Servers]** て、サーバーへの接続を設定ワークスペースを開きます。
1. ウィンドウ [!DNL Insight.cfg] で右クリックし、「>」 **[!UICONTROL Servers]** をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Server]**&#x200B;す。
1. 新しいサーバーの場合は、次のパラメーターを設定します。

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
   <td colname="col2">（オプション）このInsightのユーザーインターフェイスでリピ <span class="keyword"> ーター</span> ・サーバーを表すために使用する名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> <p>リピータサーバのホスト名または数値のIPアドレス。 </p> <p>例： <span class="filepath"> Repeater.mycompany.com</span> または192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> <p>複数の証明書がある場合を除いてオプションです。The name of the file that contains the digital certificate for this copy of <span class="keyword"> Insight</span>. (これは、 <span class="keyword"> Insightのインストール時にダウンロードしたファイル</span>)。 </p> <p>例：<span class="filepath">Samantha Smith.pem</span></p> <p>If you leave this parameter blank, <span class="keyword"> Insight</span> uses whatever certificate is present. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSLサーバー </p> <p>共通名 </p> </td> 
   <td colname="col2">リピータサーバに割り当てられる共通名。 この名前は、ライセンス証明書内のリピータサーバに割り当てられた共通名と一致する必要があります。 リピータの証明書ファイル(<span class="filepath"> Certificates\server_cert.pem</span>)にアクセスできる場合は、メモ帳などのテキストエディターでファイルを開いて、共通名を見つけることができます。 共通名は、証明書のCNフィールドで識別されます。 </td> 
  </tr> 
 </tbody> 
</table>

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**. [!DNL Insight] は、指定した設定を使用してリピータサーバへの接続を試みます。 接続が確立されると、緑色のサーバーアイコンがインターフェイスに表示さ [!DNL Servers Manager] れます。 接続が確立できない場合は、赤いアイコンが表示されます。

   For more information about the [!DNL Servers Manager] interface, see the * [!DNL Insight] User Guide*.

