---
description: サーバーモニターインターフェイスは、トラブルシューティングや、Data WorkbenchサーバーコンピューターのクライアントであるData Workbenchサーバーコンピューターとレポートコンピューターのパフォーマンスパラメーターの追跡に役立ちます。
title: サーバーモニターインターフェイス
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 63%

---

# サーバーモニターインターフェイス{#server-monitor-interface}

サーバーモニターインターフェイスは、トラブルシューティングや、Data WorkbenchサーバーコンピューターのクライアントであるData Workbenchサーバーコンピューターとレポートコンピューターのパフォーマンスパラメーターの追跡に役立ちます。

サーバーモニターインターフェイスでは、上部のコンピューター名の左に、緑の丸か赤の丸が表示されます。緑の丸は、コンピューターが問題なく機能していることを示します。赤の丸は、コンピューター上で 1 つ以上のエラーが発生したことを示します。

サーバーモニターインターフェイスの下部には、利用できる各プロファイルの処理ステータスと、コンピューターに関するパフォーマンスの詳細が一覧表示されます。

[!DNL Data Workbench servers]の詳細については、『*サーバー製品のインストールと管理に関するガイド*』を参照してください。 [!DNL Report]について詳しくは、*Data Workbenchレポートガイド*&#x200B;を参照してください。

**サーバーモニターインターフェイスを開くには**

* サーバーマネージャーで、Data Workbenchサーバーまたは[!DNL Report]コンピューターのノードを右クリックします。 t

**[!UICONTROL Server Monitor]**&#x200B;をクリックして1台のサーバーに関する詳細を表示するか、**[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]**&#x200B;をクリックして関連サーバーのクラスターに関する詳細を表示します。

![](assets/vis_ServerMonitor.png)

[!DNL Server Monitor]インターフェイスは、10秒ごとに自動的に更新されます。

次の表に、[!DNL Server Monitor]インターフェイスを使用して実行できるタスクを示します。

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
