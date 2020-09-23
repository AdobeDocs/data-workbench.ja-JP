---
description: Insightを使用してリピーターをアップグレードする手順、またはファイルをコピーしてアップグレードする手順です。
solution: Analytics
title: リピーターのアップグレード
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# リピーターのアップグレード{#upgrading-repeater}

Insightを使用してリピーターをアップグレードする手順、またはファイルをコピーしてアップグレードする手順です。

次のいずれかの方法を使用して、Platform 4.x以降 [!DNL Repeater] からアップグレードできます。

* InsightとRepeater間の接続の [!DNL Insight] 作成で説明したとの間に接続を作成した場合 [!DNL Repeater] 、を使用してアップグレード [でき](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)[!DNL Insight][!DNL Repeater]ます。 『Insightを使用したリピーターの [アップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764)』を参照してください。

   -or-

* との間に接続を作成できなかった場合、または接続を作成できなかった場合 [!DNL Insight] は、アップグレードファイルを直接 [!DNL Repeater][!DNL Repeater] マシンにコピーする必要があります。 ファイルのコピーによるリピータの [アップグレードを参照してください](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1)。

## Insightを使用したリピーターのアップグレード {#section-59c24448fd0f45c08abd0245ad746764}

1. コンピューター上で、アップグレードパッケージの [!DNL Insight] フォルダーを、がインストールされているディレクトリの [!DNL bin] フォルダーにコピー [!DNL Insight Server][!DNL Temp][!DNL Insight] します。
1. Start [!DNL Insight].
1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。
1. アップグレードするアイコンを右クリック [!DNL Repeater] し、をクリックし **[!UICONTROL Server Files]**&#x200B;ます。
1. で、次の手順を実行 [!DNL Server Files Manager]して、アップグレードファイルをサーバーにアップロードします。

   1. フォルダーを探し [!DNL bin] ます。
   1. Tempディレクトリ内の [!DNL bin] フォルダーのチェックマークを右クリックし、 **[!UICONTROL Save Directory to]** / *&lt;**[!UICONTROL server name]**>を選択します*。

>[!NOTE]
>
>この手順によって、サーバー上に存在する同じ名前のファイルが上書きされたことを示すメッセージが表示されます。 Click **[!UICONTROL Yes]** to continue.

>[!NOTE]
>
>アップグレードを完了するために追加のファイルをアップロードする必要がある場合は、 [!DNL Repeater] Adobeから指示を受けます。

アップグレードファイルをコンピュータにアップロードすると、が [!DNL Repeater] 自動的に再起動し、新しいバージョンが読み込まれ [!DNL Repeater] ます。

## ファイルをコピーしてリピータをアップグレードする {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Adobeが提供するアップグレードファイルを開きます。 おそらく、このファイルはアップグレード用の [!DNL .zip] ファイルで [!DNL Insight Server]す。
1. インストールしたディレクトリ [!DNL Repeater] (例： [!DNL D:\Adobe\Repeater])に移動します。
1. ファイル内の [!DNL bin] フォルダーをコピーし、インストー [!DNL .zip] ルディレクトリに貼り付けて、既存の [!DNL Repeater][!DNL bin] フォルダーを上書きします。

>[!NOTE]
>
>アップグレードを完了するために追加のファイルをアップロードする必要がある場合は、 [!DNL Insight Server] Adobeから指示を受けます。

アップグレードファイルをコピーした後、が [!DNL Repeater] 自動的に再起動し、新しいバージョンが読み込まれ [!DNL Repeater] ます。
