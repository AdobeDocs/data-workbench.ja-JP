---
description: サーバーモニターインターフェイスは、Data WorkbenchサーバーコンピューターおよびData Workbenchサーバーコンピューターのクライアントであるレポートコンピューターのパフォーマンスパラメーターのトラブルシューティングや追跡に役立ちます。
solution: Analytics
title: サーバーモニターインターフェイス
topic: Data workbench
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server Monitor interface{#server-monitor-interface}

サーバーモニターインターフェイスは、Data WorkbenchサーバーコンピューターおよびData Workbenchサーバーコンピューターのクライアントであるレポートコンピューターのパフォーマンスパラメーターのトラブルシューティングや追跡に役立ちます。

サーバーモニターインターフェイスでは、上部のコンピューター名の左に、緑の丸か赤の丸が表示されます。緑の丸は、コンピューターが問題なく機能していることを示します。赤の丸は、コンピューター上で 1 つ以上のエラーが発生したことを示します。

サーバーモニターインターフェイスの下部には、利用できる各プロファイルの処理ステータスと、コンピューターに関するパフォーマンスの詳細が一覧表示されます。

For more information about [!DNL Data Workbench servers], see the *Server Products Installation and Administration Guide*. For more information about [!DNL Report], see the *Data Workbench Report Guide*.

**サーバーモニターインターフェイスを開くには**

* サーバーマネージャーで、Data Workbenchサーバーまたはコンピューターのノードを右クリック [!DNL Report] します。 t

1つのサ **[!UICONTROL Server Monitor]** ーバーの詳細を表示するにはをクリックし、 **[!UICONTROL Related Servers]** >をク **[!UICONTROL Server Monitor List]** リックして関連サーバーのクラスターの詳細を表示します。

![](assets/vis_ServerMonitor.png)

The [!DNL Server Monitor]interface updates automatically every 10 seconds.

The following table lists the tasks that can be completed using the [!DNL Server Monitor] interface.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 実行する作業... </th> 
   <th colname="col2" class="entry"> 手順... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>プロファイルのログ処理ステータスを確認するには </p> </td> 
   <td colname="col2"> <p>Profile <i>Profile Name</i> ベクトルを確認します。上記の例では、Profile ExampleProfile ベクトルを確認すると、ExampleProfile プロファイルは 1 つのサーバー上で処理され、そのログ処理が 100 ％終了していることがわかります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リクエストに対するコンピューターの応答時間を確認するには </p> </td> 
   <td colname="col2"> <p>ポール待ち時間フィールドを確認します。この値が 1000 ms より大きい場合は、Adobe Support Services にお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>変換やクエリーの完了にかかる時間の推定値を確認するには </p> </td> 
   <td colname="col2"> <p>スイープ時間（hh:mm:ss）フィールドを確認します。このフィールドは変換中またはクエリー中のみ存在します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンピューターへの現在のネットワーク接続数を確認するには </p> </td> 
   <td colname="col2"> <p>コンピューターの<span class="wintitle">サーバーモニター</span>情報の最後の行を確認します。上記の例では、現在 1 台のコンピューターから 2 つのネットワーク接続があることがわかります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

