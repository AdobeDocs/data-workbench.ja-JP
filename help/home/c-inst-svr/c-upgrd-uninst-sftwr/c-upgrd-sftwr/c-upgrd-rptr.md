---
description: Insight を使用してリピーターをアップグレードする手順、またはファイルをコピーしてアップグレードする手順です。
title: リピーターのアップグレード
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# リピーターのアップグレード{#upgrading-repeater}

{{eol}}

Insight を使用してリピーターをアップグレードする手順、またはファイルをコピーしてアップグレードする手順です。

次のいずれかの方法を使用して、アップグレードできます。 [!DNL Repeater] Platform 4.x 以降の場合：

* 次の間に [!DNL Insight] および [!DNL Repeater] の説明に従って、 [Insight とリピーターとの接続の作成](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)を使用する場合、 [!DNL Insight] アップグレード [!DNL Repeater]. 詳しくは、 [Insight を使用したリピーターのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -または-

* 次の間に接続を作成できなかったか、作成できなかった場合： [!DNL Insight] および [!DNL Repeater]を使用する場合は、アップグレードファイルを [!DNL Repeater] マシン。 詳しくは、 [ファイルのコピーによるリピーターのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Insight を使用したリピーターのアップグレード {#section-59c24448fd0f45c08abd0245ad746764}

1. の [!DNL Insight] コンピュータ、コピー [!DNL bin] フォルダーを [!DNL Insight Server] パッケージをにアップグレード [!DNL Temp] フォルダー内の [!DNL Insight] がインストールされている。
1. 開始 [!DNL Insight].
1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。
1. 次のアイコンを右クリック： [!DNL Repeater] アップグレードして、 **[!UICONTROL Server Files]**.
1. 内 [!DNL Server Files Manager]次の手順を実行して、アップグレードファイルをサーバーにアップロードします。

   1. を [!DNL bin] フォルダー。
   1. のチェックマークを右クリックします。 [!DNL bin] Temp ディレクトリ内のフォルダーを選択し、 **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>この手順により、サーバー上に存在する同じ名前のファイルが上書きされたことを示すメッセージが表示されます。 クリック **[!UICONTROL Yes]** をクリックして続行します。

>[!NOTE]
>
>追加のファイルをアップロードして [!DNL Repeater] アップグレード時に、Adobeが指示を出します。

アップグレードファイルを [!DNL Repeater] 機械 [!DNL Repeater] を自動的に再起動し、新しいバージョンを読み込みます。

## ファイルのコピーによるリピーターのアップグレード {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Adobe おそらく、このファイルは [!DNL .zip] アップグレード用ファイル [!DNL Insight Server].
1. をインストールしたディレクトリに移動します。 [!DNL Repeater] ( 例： [!DNL D:\Adobe\Repeater]) をクリックします。
1. を [!DNL bin] フォルダー内の [!DNL .zip] ファイルを [!DNL Repeater] 既存のディレクトリを上書きするインストールディレクトリ [!DNL bin] フォルダー。

>[!NOTE]
>
>追加のファイルをアップロードして [!DNL Insight Server] アップグレード時に、Adobeが指示を出します。

アップグレードファイルを [!DNL Repeater] 機械 [!DNL Repeater] を自動的に再起動し、新しいバージョンを読み込みます。
