---
description: insight.zbin ファイルを設定して、クライアントアプリケーションの言語を設定します。
title: ローカライズされた言語の設定
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 66%

---

# ローカライズされた言語の設定{#setting-up-localized-languages}

insight.zbin ファイルを設定して、クライアントアプリケーションの言語を設定します。

## Data Workbench サーバーコンポーネントを更新します。{#section-5d07a081befc4eaa8fdf7fea904e0d48}

これらのサーバーコンポーネントを更新するには、管理者が最初に以下のタスクを完了する必要があります。

1. **Data Workbench サーバー 6.x への更新**[!DNL base\localization\*.zbin] ファイルを更新することにより、Data Workbench サーバーをローカリゼーション用に更新する必要があります。次に、この [!DNL insight.zbin] ファイルはクライアントにコピーされます。

   [!DNL insight.zbin] ファイルは、[!DNL insight.exe] ファイルと共にインストールフォルダーに含まれています。言語固有の[!DNL .zbin]ファイルが提供されないサーバーに接続すると、data workbenchはこのファイルの使用に進みます。

   バックアップファイルの [!DNL insight.zbin] は、どの言語でも提供できます。その結果、Data Workbenchを中国語で使用し、この言語をサポートしないサーバーに接続した場合、サーバーが基本プロファイルーを変更して[!DNL Base/Localization]フォルダーから[!DNL .zbin]ファイルを削除しても、Data Workbenchクライアントは中国語のままです。

1. **Data Workbench レポートサーバーの更新** Data Workbench レポートサーバーのルートフォルダーにある [!DNL insight.zbin] は、デフォルトでは英語です。管理者は、更新されたレポートサーバーパッケージから[!DNL .zbin]ファイルを選択してコピーし、Data Workbenchレポートサーバーのルートディレクトリに配置する必要があります。 クライアント同様、レポートサーバーでも、選択した言語に適した引数（[!DNL Insight.exe -zh-cn] など）を指定する必要があります。

   1. レポートサーバーサービスを停止します。
   1. 新しいレポートサーバーパッケージから [!DNL Localization] フォルダーをコピーします。
   1. [!DNL Localization] フォルダーから、[!DNL Insight.zbin] ファイルをコピーして、[!DNL Insight.exe] が存在するレポートサーバーのルートディレクトリに配置します。

   1. 追加[!DNL insight.exe -zh-cn]などの必須の引数
   1. レポートサーバーを再起動します。

## Data Workbench クライアントの更新  {#section-9653d3fcaf2a4337a97b685857e7aeac}

サーバーを更新した後で、以下の手順を実行して各クライアントを更新します。

1. この更新中にクライアントがサーバーから更新されないように、[!DNL Insight.cfg] 引数を False に設定します。

   ```
   Update Software = bool: false
   ```

1. クライアントを再開します。
1. ソフトウェアおよびドキュメントプロファイル(SoftDocsプロファイル)に移動し、必要な&#x200B;**[!UICONTROL insight.zbin]**&#x200B;ファイルをクライアントパッケージからダウンロードします。[!DNL Software\Insight Client\Insight_6.1.zip]

1. [!DNL insight.zbin]ファイルを[!DNL insight.exe]のあるフォルダーに移動します。

1. クライアントファイルがサーバーから更新されるように、[!DNL Insight.cfg] ファイル引数を True に設定します。

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >クライアントがサーバーと同期され、更新中であることを示すメッセージが表示されます。 ダウンロードが終了すると、クライアントを再起動するかどうかを尋ねるメッセージが表示されます。

1. 「**OK**」をクリックして、クライアントを再起動します。

以下のメッセージが表示された場合は、[!DNL zbin] ファイルが [!DNL Insight.exe] と同じ場所に配置されていなかったことを意味します。

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**ローカライズされたスプラッシュスクリーン**

data workbench は、以下のスプラッシュスクリーンファイルを探します。

* 英語（デフォルト）:[!DNL Base/Images/<version_product> Splash.png]
* 中国語（ —zh-cnで始まる場合）:[!DNL Base/Images/<version_product> Splash zh-cn.png].

要求されたスプラッシュスクリーンが見つからない場合、Data Workbench はデフォルトで英語のスプラッシュスクリーンを表示します。

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
