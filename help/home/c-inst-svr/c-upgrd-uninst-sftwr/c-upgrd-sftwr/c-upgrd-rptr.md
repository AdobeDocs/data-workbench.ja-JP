---
description: Insightを使用してリピーターをアップグレードする手順、またはファイルをコピーしてアップグレードする手順です。
title: リピーターのアップグレード
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# リピーターのアップグレード{#upgrading-repeater}

Insightを使用してリピーターをアップグレードする手順、またはファイルをコピーしてアップグレードする手順です。

[!DNL Repeater]をプラットフォーム4.x以降からアップグレードするには、次の方法のいずれかを使用できます。

* [Insightとリピーターの間の接続の作成](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)の説明に従って[!DNL Insight]と[!DNL Repeater]の間に接続を作成した場合は、[!DNL Insight]を使用して[!DNL Repeater]をアップグレードできます。 「Insight[を使用したリピーターのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764)」を参照してください。

   -or-

* [!DNL Insight]と[!DNL Repeater]の間の接続を作成できなかった、または作成できなかった場合は、アップグレードファイルを[!DNL Repeater]マシンに直接コピーする必要があります。 「[ファイルをコピーしてリピータをアップグレードする](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1)」を参照してください。

## Insightを使用したリピーターのアップグレード{#section-59c24448fd0f45c08abd0245ad746764}

1. [!DNL Insight]コンピューター上で、[!DNL Insight Server]アップグレードパッケージの[!DNL bin]フォルダーを、[!DNL Insight]がインストールされているディレクトリの[!DNL Temp]フォルダーにコピーします。
1. 開始[!DNL Insight]。
1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。
1. アップグレードする[!DNL Repeater]のアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。
1. [!DNL Server Files Manager]で、次の手順を実行してアップグレードファイルをサーバーにアップロードします。

   1. [!DNL bin]フォルダーを探します。
   1. Tempディレクトリ内の[!DNL bin]フォルダーのチェックマークを右クリックし、**[!UICONTROL Save Directory to]**/***[!UICONTROL server name]***&#x200B;を選択します。

>[!NOTE]
>
>この手順によって、サーバー上に存在する同じ名前のファイルが上書きされたことを示すメッセージが表示されます。 **[!UICONTROL Yes]**&#x200B;をクリックして続行します。

>[!NOTE]
>
>[!DNL Repeater]のアップグレードを完了するために追加のファイルをアップロードする必要がある場合は、Adobeから指示があります。

[!DNL Repeater]コンピューターにアップロードしたアップグレードファイルは、[!DNL Repeater]によって自動的に再起動され、新しいバージョンが読み込まれます。

## ファイルをコピーしてリピータをアップグレードする{#section-202f2209f6604f19a15d96b517ea1bc1}

1. Adobeが提供するアップグレードファイルを開きます。 おそらく、このファイルは[!DNL Insight Server]をアップグレードするための[!DNL .zip]ファイルです。
1. [!DNL Repeater]をインストールしたディレクトリ（例：[!DNL D:\Adobe\Repeater]）に移動します。
1. [!DNL .zip]ファイル内の[!DNL bin]フォルダーをコピーし、[!DNL Repeater]インストールディレクトリに貼り付けて、既存の[!DNL bin]フォルダーを上書きします。

>[!NOTE]
>
>[!DNL Insight Server]のアップグレードを完了するために追加のファイルをアップロードする必要がある場合は、Adobeから指示があります。

アップグレードファイルを[!DNL Repeater]マシンにコピーすると、[!DNL Repeater]が自動的に再起動し、新しいバージョンが読み込まれます。
