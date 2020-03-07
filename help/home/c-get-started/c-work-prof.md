---
description: Data Workbenchは、プロファイルをコンピューターにダウンロードします。
title: プロファイル
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# プロファイル{#profiles}

Data Workbenchは、プロファイルをコンピューターにダウンロードします。

If you are loading a profile for the first time, you must have a network connection to the [!DNL Data Workbench server] and be working online so that Data Workbench can download the necessary files from the [!DNL Data Workbench server].

プロファイルのダウンロードには数分かかる場合があります。データキャッシュの充てんが開始されるまでプロファイルの操作を開始することはできませんが、充てんが完了するまで待つ必要はありません。プロファイルの読み込み中にステータスバーを参照すると、データキャッシュの進行状況、プロファイルの同期の進行状況、最近処理したデータの日時を確認できます。

>[!NOTE]
>
>追加したビジュアライゼーションのデータは、データキャッシュの埋め込みが開始されるまで表示されません。

The next time that you load the profile, updates to the profile and its data are downloaded only if you have a network connection to the [!DNL Data Workbench server] and are working online. オフラインで作業している場合、プロファイルとそのデータはご使用のコンピューターのキャッシュから読み込まれます。この場合、表示されるプロファイルとデータは、最後にそのプロファイルをオンラインで操作したときにダウンロードされたバージョンです。オンライン対オフラインの操作について詳しくは、「[オフラインおよびオンラインでの動作](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54)」で概説されている利点と影響を比較検討してください。

When you need to change your profile (using the [!DNL Profile Manager] or the [!DNL Server Files Manager]), you should work online to ensure that you have the most up-to-date version of the profile. との詳細については、 [!DNL Profile Manager] Administrative Interfaces [!DNL Server Files Manager]を参照し [てください](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)。

プロファイルにアクセスできない場合やプロファイルを読み込めない場合は、次の点を確認する必要があります。

* You have a network connection to the [!DNL Data Workbench server] machine on which the profile resides.
* プロファイルにアクセスする適切な権限があること

ご不明な点は、システム管理者にお問い合わせください。

## Loading or switching profiles {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Data Workbenchを起動します。
1. In the side bar, click the profile name and click **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, where *profile name* is the profile with which you want to work.

   ![](assets/sidebar_profile.png)

選択したプロファイルを読み込むのはこれが初めての場合、ビジュアライゼーションの表示に十分なデータをダウンロードするのに数分かかる場合があります。

## Accessing a profile on a cluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbenchユーザーが、

data workbenchサーバークラスターは、Data Workbench設定ファイル( [!DNL Insight.cfg])内のマスターData Workbenchサーバーのみを識別します。 Data Workbenchユーザーの観点から見ると、1つのData Workbenchサーバー（マスターData Workbenchサーバー）上でのみプロファイルにアクセスできます。 ただし、アナリストからのクエリ要求は、クラスター内の任意のData Workbenchサーバーに送信されます。

For more information about profiles running on a Data Workbench Server cluster, see the *Server Products Installation and Administration Guide*.
