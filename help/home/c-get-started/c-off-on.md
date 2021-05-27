---
description: オフラインまたはオンラインでのData Workbench・サーバの操作に関する情報。
title: オフラインおよびオンラインでの操作
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 32%

---

# オフラインおよびオンラインでの操作{#working-offline-and-online}

オフラインまたはオンラインでのData Workbench・サーバの操作に関する情報。

Data Workbenchが[!DNL server]にネットワーク接続し、オンラインで動作している場合は、Data Workbenchサーバーからプロファイルとそのデータの更新が自動的にダウンロードされます。 オンラインで動作するように指定していない場合、Data Workbenchは、プロファイルとそのデータをコンピューターのキャッシュから読み込みます。 この場合、プロファイルを使用して最後にオンラインで動作した時にダウンロードされたプロファイルとそのデータが表示されます。

オフラインでの動作は、ローカルキャッシュを使用して作業し、コンピューター上のデータをクエリーするので、処理速度の面でメリットがあります。オンラインで作業する場合は、すべてのクエリをData Workbenchサーバーに戻す必要があります。この処理には時間がかかり、他のオンラインユーザーとサーバーリソースを競い合わせる必要があります。 Data WorkbenchサーバーにData Workbench接続している限り、オフラインで作業すると、Data Workbench上のプロファイルやデータの更新はサーバーで停止されますが、Data Workbenchサーバーへの項目の保存は停止されません。

オフラインで動作する機能により、Data Workbenchサーバーは、Data Workbenchユーザー数と共に、データセット内のリアルタイムトラフィック入力やデータ量を処理するようにサイズ設定されますが、同時ユーザー数を最大に抑える必要はありません（実際には頻繁にはありません）。 ユーザーは通常、傾向や比率を探し求め、データを調べているので、ほとんどの場合、正確な数を必要としません。現在のデータを使用して正確な数をクエリーし、解決する必要がある場合は、オンラインで動作して正確な数を取得できますが、クエリーを 100 ％解決するまでにかかる時間は長くなります。

**オンラインまたはオフラインで作業するには**

サイドバーで&#x200B;**[!UICONTROL Connection]**&#x200B;設定をクリックし、**[!UICONTROL Work Online]**&#x200B;をクリックします。

![](assets/sidebar_work_online.png)

オンラインで作業する場合、Data WorkbenchはData Workbenchサーバーに接続し、コンピューター上の情報とData Workbenchサーバー上のデータセット情報を同期します。

Data Workbenchのデフォルトの設定はオフラインで動作しますが、次の節で説明するように、各ユーザーは[!DNL Insight.cfg]ファイルを変更して、Data Workbenchのインスタンスをデフォルトでオンラインで動作させることができます。

**デフォルトでオンライン動作させるには**

1. Insight インストールディレクトリに移動します。
1. [!DNL Insight.cfg] ファイルをテキストエディターで開きます。
1. 以下の例に示すように、ハイライトされている行をファイルに追加します。

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

次回Data Workbenchを開くと、Data Workbenchサーバーに接続し、デフォルトでオンラインで動作します。
