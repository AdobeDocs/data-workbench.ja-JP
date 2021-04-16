---
description: Insightサーバー、変換、リピーターのアンインストール手順を説明します。
title: ソフトウェアのアンインストール
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 9%

---

# ソフトウェアのアンインストール{#uninstalling-your-software}

Insightサーバー、変換、リピーターのアンインストール手順を説明します。

## InsightサーバーAdobeのアンインストール{#section-7d7befe672854df79bb6c28ec02f6670}

1. [!DNL Insight Server] Windowsサービスの登録を解除します。

   1. コマンドプロンプトを開き、[!DNL Insight Server]をインストールしたフォルダー内のbinサブディレクトリに移動します。

      例：[!DNL C:\Adobe\Server\bin]

   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windowsのサービスとして停止および登録解除します。

      ```
      InsightServer64.exe /unregserver
      ```

1. [!DNL Insight Server]インストールディレクトリを削除します。

## 変換{#section-5e6a604dadb5477ba4dc9f93c9be0897}をアンインストールしています

1. [!DNL Transform]を使用した各プロファイルの[!DNL profile.cfg]ファイルを更新するには、次の手順を実行します。

   1.  [!DNL Profile Manager].
   1. [!DNL profile.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。 [!DNL profile.cfg]ウィンドウが表示されます。

   1. [!DNL profile.cfg]ウィンドウで、Directoriesベクトルから[!DNL Transform]プロファイルエントリを削除します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Profile Manager]で、[!DNL User]列の[!DNL profile.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL profile name]**>*&#x200B;をクリックします。

1. [!DNL Insight Server]インストールディレクトリの[!DNL Profiles]フォルダーから[!DNL Transform]フォルダーを削除します。

## リピーターのアンインストール{#section-2f94141d956749d88f549dbea26e5272}

1. [!DNL Repeater] Windowsサービスの登録を解除します。

   1. コマンドプロンプトを開き、[!DNL Repeater]をインストールしたフォルダー内のbinサブディレクトリに移動します。

      例：[!DNL D:\Adobe\Repeater\bin]

   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windowsのサービスとして停止および登録解除します。

      ```
      InsightServer64.exe /unregserver
      ```

1. [!DNL Repeater]インストールディレクトリを削除します。
