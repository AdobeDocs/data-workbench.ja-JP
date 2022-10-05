---
description: Insight サーバー、変換、リピーターのアンインストール手順です。
title: ソフトウェアのアンインストール
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 9%

---

# ソフトウェアのアンインストール{#uninstalling-your-software}

{{eol}}

Insight サーバー、変換、リピーターのアンインストール手順です。

## Insight サーバーAdobeのアンインストール {#section-7d7befe672854df79bb6c28ec02f6670}

1. 登録解除 [!DNL Insight Server] Windows サービス。

   1. コマンドプロンプトを開き、をインストールしたフォルダー内の bin サブディレクトリに移動します。 [!DNL Insight Server].

      例：[!DNL C:\Adobe\Server\bin]

   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windows でサービスとして停止および登録解除します。

      ```
      InsightServer64.exe /unregserver
      ```

1. を削除します。 [!DNL Insight Server] インストールディレクトリ。

## 変換のアンインストール {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. 次の手順を使用して、 [!DNL profile.cfg] 使用している各プロファイルのファイル [!DNL Transform].

   1.  [!DNL Profile Manager].
   1. の横のチェックマークを右クリックします。 [!DNL profile.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. この [!DNL profile.cfg] ウィンドウが表示されます。

   1. 内 [!DNL profile.cfg] ウィンドウで、 [!DNL Transform] Directories ベクトルからのプロファイルエントリ。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Profile Manager]、次のチェックマークを右クリック： [!DNL profile.cfg] 内 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. を削除します。 [!DNL Transform] フォルダーを [!DNL Profiles] の [!DNL Insight Server] インストールディレクトリ。

## リピーターのアンインストール {#section-2f94141d956749d88f549dbea26e5272}

1. 登録解除 [!DNL Repeater] Windows サービス。

   1. コマンドプロンプトを開き、をインストールしたフォルダー内の bin サブディレクトリに移動します。 [!DNL Repeater].

      例：[!DNL D:\Adobe\Repeater\bin]

   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windows でサービスとして停止および登録解除します。

      ```
      InsightServer64.exe /unregserver
      ```

1. を削除します。 [!DNL Repeater] インストールディレクトリ。
