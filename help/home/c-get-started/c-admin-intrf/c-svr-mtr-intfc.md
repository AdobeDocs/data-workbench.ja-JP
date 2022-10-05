---
description: Server Monitor インターフェイスは、トラブルシューティングや、Data WorkbenchサーバーコンピュータのクライアントであるData Workbenchサーバーコンピュータとレポートコンピュータのパフォーマンスパラメータの追跡に役立ちます。
title: サーバーモニターインターフェイス
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 59%

---

# サーバーモニターインターフェイス{#server-monitor-interface}

{{eol}}

Server Monitor インターフェイスは、トラブルシューティングや、Data WorkbenchサーバーコンピュータのクライアントであるData Workbenchサーバーコンピュータとレポートコンピュータのパフォーマンスパラメータの追跡に役立ちます。

サーバーモニターインターフェイスでは、上部のコンピューター名の左に、緑の丸か赤の丸が表示されます。緑の丸は、コンピューターが問題なく機能していることを示します。赤の丸は、コンピューター上で 1 つ以上のエラーが発生したことを示します。

サーバーモニターインターフェイスの下部には、利用できる各プロファイルの処理ステータスと、コンピューターに関するパフォーマンスの詳細が一覧表示されます。

詳しくは、 [!DNL Data Workbench servers]を参照し、 *サーバー製品のインストールおよび管理ガイド*. 詳しくは、 [!DNL Report]を参照し、 *Data Workbenchレポートガイド*.

**サーバーモニターインターフェイスを開くには**

* サーバーマネージャで、Data Workbenchサーバーのノードを右クリックします。 [!DNL Report] コンピュータ。 t

クリック **[!UICONTROL Server Monitor]** 1 つのサーバーの詳細を表示するには、以下をクリックします。 **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** をクリックして、関連するサーバーのクラスターに関する詳細を表示します。

![](assets/vis_ServerMonitor.png)

この [!DNL Server Monitor]インターフェイスは、10 秒ごとに自動的に更新されます。

次の表に、 [!DNL Server Monitor] インターフェイス。

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
   <td colname="col2"> <p>スイープ時間を表示します (hh:mm:ss) フィールド。変換中またはクエリ中にのみ存在します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンピューターへの現在のネットワーク接続数を確認するには </p> </td> 
   <td colname="col2"> <p>コンピューターの<span class="wintitle">サーバーモニター</span>情報の最後の行を確認します。上記の例では、現在 1 台のコンピューターから 2 つのネットワーク接続があることがわかります。 </p> </td> 
  </tr> 
 </tbody> 
</table>
