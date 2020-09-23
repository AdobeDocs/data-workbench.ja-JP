---
description: Insightサーバー、変換、リピーターのアンインストール手順を説明します。
solution: Analytics
title: ソフトウェアのアンインストール
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 9%

---


# ソフトウェアのアンインストール{#uninstalling-your-software}

Insightサーバー、変換、リピーターのアンインストール手順を説明します。

## InsightサーバーAdobeのアンインストール {#section-7d7befe672854df79bb6c28ec02f6670}

1. Windowsサー [!DNL Insight Server] ビスの登録を解除します。

   1. コマンドプロンプトを開き、インストール先のフォルダー内のbinサブディレクトリに移動し [!DNL Insight Server]ます。

      例：[!DNL C:\Adobe\Server\bin]

   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windowsのサービスとして停止および登録解除します。

      ```
      InsightServer64.exe /unregserver
      ```

1. インストー [!DNL Insight Server] ルディレクトリを削除します。

## 変換のアンインストール {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. 次の手順を実行して、使用している各プロファイルの [!DNL profile.cfg] ファイルを更新し [!DNL Transform]ます。

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックし、 [!DNL profile.cfg] をクリックし **[!UICONTROL Make Local]**&#x200B;ます。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** /をクリックし **[!UICONTROL in Insight]**&#x200B;ます。 The [!DNL profile.cfg] window appears.

   1. ウィン [!DNL profile.cfg] ドウで、Directoriesベクトルから [!DNL Transform] プロファイルエントリを削除します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. で、 [!DNL Profile Manager]列ののチェックマーク [!DNL profile.cfg] を右クリックし、 [!DNL User] / **[!UICONTROL Save to]** &lt; *>をクリックします&#x200B;**[!UICONTROL profile name]***。

1. インストールディレクトリ内の [!DNL Transform] フォルダーから [!DNL Profiles][!DNL Insight Server] フォルダーを削除します。

## リピーターのアンインストール {#section-2f94141d956749d88f549dbea26e5272}

1. Windowsサー [!DNL Repeater] ビスの登録を解除します。

   1. コマンドプロンプトを開き、インストール先のフォルダー内のbinサブディレクトリに移動し [!DNL Repeater]ます。

      例：[!DNL D:\Adobe\Repeater\bin]

   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windowsのサービスとして停止および登録解除します。

      ```
      InsightServer64.exe /unregserver
      ```

1. インストー [!DNL Repeater] ルディレクトリを削除します。

