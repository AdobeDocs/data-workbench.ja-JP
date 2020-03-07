---
description: Insightサーバー、変換またはリピーターのアンインストール手順を説明します。
solution: Insight
title: ソフトウェアのアンインストール
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ソフトウェアのアンインストール{#uninstalling-your-software}

Insightサーバー、変換またはリピーターのアンインストール手順を説明します。

## Insight Server Adobeのアンインストール {#section-7d7befe672854df79bb6c28ec02f6670}

1. Windowsサービスの登 [!DNL Insight Server] 録を解除します。

   1. コマンドプロンプトを開き、をインストールしたフォルダー内のbinサブディレクトリに移動しま [!DNL Insight Server]す。

      例：[!DNL C:\Adobe\Server\bin]

   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windowsのサービスを停止し、登録解除します。

      ```
      InsightServer64.exe /unregserver
      ```

1. インストールディレクトリ [!DNL Insight Server] を削除します。

## 変換のアンインストール {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. 次の手順を実行して、使用してい [!DNL profile.cfg] た各プロファイルのファイルを更新しま [!DNL Transform]す。

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックし、をク [!DNL profile.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL in Insight]**&#x200B;す。 The [!DNL profile.cfg] window appears.

   1. ウィンドウ [!DNL profile.cfg] で、Directoriesベクトルか [!DNL Transform] らprofileエントリを削除します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Profile Manager]のチェックマークを右クリ [!DNL profile.cfg] ックし [!DNL User] 、/ **[!UICONTROL Save to]** &lt; *>をクリック&#x200B;**[!UICONTROL profile name]**します*。

1. インストールデ [!DNL Transform] ィレクトリ内の [!DNL Profiles] フォルダからフォルダ [!DNL Insight Server] を削除します。

## Repeaterのアンインストール {#section-2f94141d956749d88f549dbea26e5272}

1. Windowsサービスの登 [!DNL Repeater] 録を解除します。

   1. コマンドプロンプトを開き、をインストールしたフォルダー内のbinサブディレクトリに移動しま [!DNL Repeater]す。

      例：[!DNL D:\Adobe\Repeater\bin]

   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windowsのサービスを停止し、登録解除します。

      ```
      InsightServer64.exe /unregserver
      ```

1. インストールディレクトリ [!DNL Repeater] を削除します。

