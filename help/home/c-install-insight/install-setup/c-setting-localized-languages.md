---
description: insight.zbin ファイルを設定して、クライアントアプリケーションの言語を設定します。
solution: Analytics
title: ローカライズされた言語の設定
topic: Data workbench
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ローカライズされた言語の設定{#setting-up-localized-languages}

insight.zbin ファイルを設定して、クライアントアプリケーションの言語を設定します。

## Data Workbench サーバーコンポーネントを更新します。{#section-5d07a081befc4eaa8fdf7fea904e0d48}

これらのサーバーコンポーネントを更新するには、管理者が最初に以下のタスクを完了する必要があります。

1. **Data Workbench サーバー 6.x への更新**[!DNL base\localization\*.zbin] ファイルを更新することにより、Data Workbench サーバーをローカリゼーション用に更新する必要があります。次に、この [!DNL insight.zbin] ファイルはクライアントにコピーされます。

   [!DNL insight.zbin] ファイルは、[!DNL insight.exe] ファイルと共にインストールフォルダーに含まれています。If you connect to a server that doesn&#39;t provide you with language-specific [!DNL .zbin] files, then data workbench will proceed to use this file.

   バックアップファイルの [!DNL insight.zbin] は、どの言語でも提供できます。As a result, if you use data workbench in Chinese and connect to a server that doesn&#39;t support this language, then your data workbench client will still be in Chinese, even if the server changes your base profile and removes your [!DNL .zbin] files from the [!DNL Base/Localization] folder.

1. **Data Workbench レポートサーバーの更新** Data Workbench レポートサーバーのルートフォルダーにある [!DNL insight.zbin] は、デフォルトでは英語です。As the administrator, you will be required to select and copy the [!DNL .zbin] file from the updated report server package and place it in the root directory of the data workbench report server. クライアント同様、レポートサーバーでも、選択した言語に適した引数（[!DNL Insight.exe -zh-cn] など）を指定する必要があります。

   1. レポートサーバーサービスを停止します。
   1. 新しいレポートサーバーパッケージから [!DNL Localization] フォルダーをコピーします。
   1. [!DNL Localization] フォルダーから、[!DNL Insight.zbin] ファイルをコピーして、[!DNL Insight.exe] が存在するレポートサーバーのルートディレクトリに配置します。

   1. Add any required arguments, such as [!DNL insight.exe -zh-cn]
   1. レポートサーバーを再起動します。

## Data Workbench クライアントの更新 {#section-9653d3fcaf2a4337a97b685857e7aeac}

サーバーを更新した後で、以下の手順を実行して各クライアントを更新します。

1. この更新中にクライアントがサーバーから更新されないように、[!DNL Insight.cfg] 引数を False に設定します。

   ```
   Update Software = bool: false
   ```

1. クライアントを再開します。
1. Navigate to the Software and Docs profile (SoftDocs profile) and download the required **[!UICONTROL insight.zbin]** file from the client package: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Move the [!DNL insight.zbin] file to the folder where [!DNL insight.exe] is located.

1. クライアントファイルがサーバーから更新されるように、[!DNL Insight.cfg] ファイル引数を True に設定します。

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >クライアントがサーバーと同期し、更新中であることを示すメッセージが表示されます。 ダウンロードが終了すると、クライアントを再起動するかどうかを尋ねるメッセージが表示されます。

1. 「**OK**」をクリックして、クライアントを再起動します。

以下のメッセージが表示された場合は、[!DNL zbin] ファイルが [!DNL Insight.exe] と同じ場所に配置されていなかったことを意味します。

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**ローカライズされたスプラッシュスクリーン**

data workbench は、以下のスプラッシュスクリーンファイルを探します。

* 英語（デフォルト）: [!DNL Base/Images/<version_product> Splash.png]
* 中国語（ —zh-cnで始まる場合）: [!DNL Base/Images/<version_product> Splash zh-cn.png].

要求されたスプラッシュスクリーンが見つからない場合、Data Workbench はデフォルトで英語のスプラッシュスクリーンを表示します。

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

