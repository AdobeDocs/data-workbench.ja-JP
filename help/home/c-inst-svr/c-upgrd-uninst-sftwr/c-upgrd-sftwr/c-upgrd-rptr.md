---
description: Insightを使用してリピーターをアップグレードする手順、またはファイルをコピーしてアップグレードする手順。
solution: Insight
title: リピータのアップグレード
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# リピータのアップグレード{#upgrading-repeater}

Insightを使用してリピーターをアップグレードする手順、またはファイルをコピーしてアップグレードする手順。

次のいずれかの方法を使用して、Platform 4.x以降 [!DNL Repeater] からアップグレードできます。

* InsightとRepeater間の接続の作成で説明し [!DNL Insight] てい [!DNL Repeater] るとお [よび間の接続を作成した場合](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)、を使用してアップグ [!DNL Insight] レードできます [!DNL Repeater]。 Insightを使用し [たリピーターのアップグレードを参照してくださ](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764)い。

   - または -

* との間に接続を作成できなかった場合、または作成しなか [!DNL Insight] った場合 [!DNL Repeater]は、アップグレードファイルを直接コンピュータにコピーする必要があ [!DNL Repeater] ります。 詳しくは、ファ [イルのコピーによるリピータのアップグレードを参照してくださ](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1)い。

## Insightを使用したリピーターのアップグレード {#section-59c24448fd0f45c08abd0245ad746764}

1. コンピュータ [!DNL Insight] ー上で、アップグレード [!DNL bin] パッケージのフ [!DNL Insight Server] ォルダーを、がインストー [!DNL Temp] ルされているディレクトリのフォルダー [!DNL Insight] にコピーします。
1. Start [!DNL Insight].
1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。
1. アップグレードするアイコンを右ク [!DNL Repeater] リックし、をクリックしま **[!UICONTROL Server Files]**&#x200B;す。
1. で、次の手順 [!DNL Server Files Manager]を実行して、アップグレードファイルをサーバーにアップロードします。

   1. フォルダを見つ [!DNL bin] けます。
   1. Tempディレクトリ内のフォルダーのチェ [!DNL bin] ックマークを右クリックし、/ **[!UICONTROL Save Directory to]** &lt; *>を選&#x200B;**[!UICONTROL server name]**択します*。

>[!NOTE]
>
>この手順で、サーバー上に存在する同じ名前のファイルが上書きされたことを示すメッセージが表示されます。 Click **[!UICONTROL Yes]** to continue.

>[!NOTE]
>
>アップグレードを完了するために追加のファイルをアップロードする [!DNL Repeater] 必要がある場合は、アドビから指示があります。

アップグレードファイルをコンピュータにアップロードした後、 [!DNL Repeater] が自動的に [!DNL Repeater] 再起動し、新しいバージョンが読み込まれます。

## ファイルのコピーによるリピータのアップグレード {#section-202f2209f6604f19a15d96b517ea1bc1}

1. アドビから提供されたアップグレードファイルを開きます。 おそらく、このファイルはアップグレード用のフ [!DNL .zip] ァイルであると思われま [!DNL Insight Server]す。
1. をインストールしたディレクトリ( [!DNL Repeater] 例： [!DNL D:\Adobe\Repeater])に移動します。
1. ファイル内のフ [!DNL bin] ォルダーをコ [!DNL .zip] ピーし、インストールディレクトリに貼り付け [!DNL Repeater] て、既存のフォルダーを上書き [!DNL bin] します。

>[!NOTE]
>
>アップグレードを完了するために追加のファイルをアップロードする [!DNL Insight Server] 必要がある場合は、アドビから指示があります。

アップグレードファイルをコピーした後、は自 [!DNL Repeater] 動的に再起 [!DNL Repeater] 動し、新しいバージョンを読み込みます。
