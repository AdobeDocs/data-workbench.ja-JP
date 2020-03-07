---
description: Data Workbenchサーバーのオフラインまたはオンラインでの操作に関する情報です。
solution: Analytics
title: オフラインおよびオンラインでの作業
topic: Data workbench
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Working offline and online{#working-offline-and-online}

Data Workbenchサーバーのオフラインまたはオンラインでの操作に関する情報です。

Data Workbench automatically downloads updates to the profile and its data from the Data Workbench server if you have a network connection to the [!DNL server] and are working online. オンラインで動作するように指定していない場合、Data Workbenchは、プロファイルとそのデータをコンピューターのキャッシュから読み込みます。 この場合、プロファイルを使用して最後にオンラインで動作した時にダウンロードされたプロファイルとそのデータが表示されます。

オフラインでの動作は、ローカルキャッシュを使用して作業し、コンピューター上のデータをクエリーするので、処理速度の面でメリットがあります。オンラインで作業する場合、すべてのクエリーをData Workbenchサーバーに戻す必要があります。これには時間がかかり、他のオンラインユーザーとサーバーリソースを競合させる必要があります。 Data Workbenchサーバーにネットワーク接続している限り、オフラインで作業すると、Data WorkbenchサーバーはData Workbench上のプロファイルやデータを更新できなくなりますが、Data Workbenchサーバーに項目を保存するのは停止しません。

オフラインでの作業が可能なので、Data Workbenchサーバーのサイズは、データセット内のリアルタイムトラフィック入力量やデータ量、Data Workbenchユーザー数などを処理するように設定されていますが、同時使用ユーザー数の上限（実際にはあまり多くは発生しません）に対応する必要はありません。 ユーザーは通常、傾向や比率を探し求め、データを調べているので、ほとんどの場合、正確な数を必要としません。現在のデータを使用して正確な数をクエリーし、解決する必要がある場合は、オンラインで動作して正確な数を取得できますが、クエリーを 100 ％解決するまでにかかる時間は長くなります。

**オンラインまたはオフラインで作業するには**

サイドバーで、設定をクリックし **[!UICONTROL Connection]** てをクリックしま **[!UICONTROL Work Online]**&#x200B;す。

![](assets/sidebar_work_online.png)

オンラインで作業する場合、Data WorkbenchはData Workbenchサーバーに接続し、コンピューター上の情報と、Data Workbenchサーバー上に存在するプロファイルとそのデータセット情報とを同期します。

The default configuration for Data Workbench is to work offline, but as described in the following section, each user can change their [!DNL Insight.cfg] file to make their instance of Data Workbench work online by default.

**デフォルトでオンライン動作させるには**

1. Insight インストールディレクトリに移動します。
1. [!DNL Insight.cfg] ファイルをテキストエディターで開きます。
1. 以下の例に示すように、ハイライトされている行をファイルに追加します。

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

次回Data Workbenchを開くと、Data Workbenchサーバーに接続され、デフォルトでオンラインで動作します。
