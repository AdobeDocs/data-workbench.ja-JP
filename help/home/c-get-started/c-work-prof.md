---
description: Data Workbenchは、お使いのコンピューターにプロファイルをダウンロードします。
title: プロファイル
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 40%

---

# プロファイル{#profiles}

{{eol}}

Data Workbenchは、お使いのコンピューターにプロファイルをダウンロードします。

初めてプロファイルを読み込む場合は、 [!DNL Data Workbench server] Data Workbenchが必要なファイルを [!DNL Data Workbench server].

プロファイルのダウンロードには数分かかる場合があります。データキャッシュの充てんが開始されるまでプロファイルの操作を開始することはできませんが、充てんが完了するまで待つ必要はありません。プロファイルの読み込み中にステータスバーを参照すると、データキャッシュの進行状況、プロファイルの同期の進行状況、最近処理したデータの日時を確認できます。

>[!NOTE]
>
>追加するビジュアライゼーションには、データキャッシュの充てんが開始されるまでデータが表示されません。

次回プロファイルを読み込む際には、 [!DNL Data Workbench server] オンラインで作業しています。 オフラインで作業している場合、プロファイルとそのデータはご使用のコンピューターのキャッシュから読み込まれます。この場合、表示されるプロファイルとデータは、最後にそのプロファイルをオンラインで操作したときにダウンロードされたバージョンです。オンライン対オフラインの操作について詳しくは、「[オフラインおよびオンラインでの動作](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54)」で概説されている利点と影響を比較検討してください。

( [!DNL Profile Manager] または [!DNL Server Files Manager]) を使用する場合は、オンラインで作業して、プロファイルの最新バージョンを入手する必要があります。 詳しくは、 [!DNL Profile Manager] そして [!DNL Server Files Manager]を参照してください。 [管理インターフェイス](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

プロファイルにアクセスできない場合やプロファイルを読み込めない場合は、次の点を確認する必要があります。

* 次に対するネットワーク接続があります： [!DNL Data Workbench server] プロファイルが存在するマシン。
* プロファイルにアクセスする適切な権限があること

ご不明な点は、システム管理者にお問い合わせください。

## プロファイルの読み込みまたは切り替え {#section-c50499d7d8084d7cadfada52df33f5f4}

1. 起動Data Workbench。
1. サイドバーで、プロファイル名をクリックし、 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*&#x200B;で、 *プロファイル名* は、作業するプロファイルです。

   ![](assets/sidebar_profile.png)

選択したプロファイルを読み込むのはこれが初めての場合、ビジュアライゼーションの表示に十分なデータをダウンロードするのに数分かかる場合があります。

## クラスター上のプロファイルへのアクセス {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench上で実行されているプロファイルにアクセスするユーザー

data workbench サーバークラスターは、Data Workbench設定ファイル ( [!DNL Insight.cfg]) をクリックします。 Data Workbench・ユーザーの観点からは、1 台のData Workbench・サーバ ( マスター・Data Workbench・サーバ ) 上でのみプロファイルにアクセスできます。 ただし、アナリストからのクエリ要求は、クラスター内の任意のData Workbenchサーバーに送信できます。

Data Workbench・サーバー・クラスタ上で実行するプロファイルの詳細は、 *サーバー製品のインストールおよび管理ガイド*.
