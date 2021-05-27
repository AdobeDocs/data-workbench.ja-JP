---
description: ネットワークファイアウォールがInsightマシンからリピーターサーバーにアクセスするのを妨げない場合は、リピーターサーバーとInsightの間に接続を作成して、Insightを使用してリピーターサーバーを管理できます。
title: Insight とリピーターとの接続の作成
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 9%

---

# Insight とリピーターとの接続の作成{#creating-a-connection-between-insight-and-repeater}

ネットワークファイアウォールがInsightマシンからリピーターサーバーにアクセスするのを妨げない場合は、リピーターサーバーとInsightの間に接続を作成して、Insightを使用してリピーターサーバーを管理できます。

**とリピータサーバー間の接 [!DNL Insight] 続を作成するには**

1. [!DNL Insight]の「[!DNL Admin]」タブで、**[!UICONTROL Configure Connections to Servers]**&#x200B;サムネールをクリックして「サーバーへの接続を設定」ワークスペースを開きます。
1. [!DNL Insight.cfg]ウィンドウで&#x200B;**[!UICONTROL Servers]**&#x200B;を右クリックし、**[!UICONTROL Add new]** / **[!UICONTROL Server]**&#x200B;をクリックします。
1. 新しいサーバーの場合は、次のパラメーターを入力します。

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
   <td colname="col2">（オプション）この<span class="keyword"> Insight</span>で、ユーザーインターフェイスでリピーターサーバーを表すために使用する名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> <p>リピーターサーバーのホスト名または数値IPアドレス。 </p> <p>例：<span class="filepath"> Repeater.mycompany.com</span>または192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> <p>複数の証明書がある場合を除いてオプションです。<span class="keyword"> Insight</span>のこのコピーのデジタル証明書を含むファイルの名前。 （これは、<span class="keyword"> Insight</span>のインストール時にダウンロードしたファイルです）。 </p> <p>例：<span class="filepath">Samantha Smith.pem</span></p> <p>このパラメーターを空白のままにすると、<span class="keyword"> Insight</span>は、存在する証明書を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Server </p> <p>共通名 </p> </td> 
   <td colname="col2">リピーターサーバーに割り当てられる共通名。 この名前は、ライセンス証明書内のリピーターサーバーに割り当てられている共通名と一致する必要があります。 リピーターの証明書ファイル(<span class="filepath"> Certificates\server_cert.pem</span>)にアクセスできる場合は、メモ帳などのテキストエディターでファイルを開くと、共通名を見つけることができます。 共通名は、証明書のCNフィールドで識別されます。 </td> 
  </tr> 
 </tbody> 
</table>

1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックして、ファイルを保存します。 [!DNL Insight] は、指定した設定を使用してリピーターサーバーへの接続を試みます。接続が確立されると、[!DNL Servers Manager]インターフェイスに緑色のサーバアイコンが表示されます。 接続を確立できない場合は、赤いアイコンが表示されます。

   [!DNL Servers Manager]インターフェイスの詳細については、『ユーザーガイド』を参照してください。[!DNL Insight]
