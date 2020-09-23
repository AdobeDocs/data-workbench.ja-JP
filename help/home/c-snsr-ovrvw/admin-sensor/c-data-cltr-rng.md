---
description: コレクタが異なる方法で実行されているかどうかを確認します。
solution: Analytics
title: データコレクターの実行状態の確認
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---


# データコレクターの実行状態の確認{#confirming-that-the-data-collector-is-running}

コレクタが異なる方法で実行されているかどうかを確認します。

**推奨頻度：** 5 ～ 10分ごと

* [送信機のサイトテスト機能を使用します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Cookieが設定され [!DNL Sensor] ているかどうかを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## サイトテストの使用 {#section-a5a697c3252e40f184c0b662926170f2}

コレクタが実行されていることを確認する1つの方法は、トランスミッタでサイトテスト機能を有効にすることです。 サイトテストを有効にすると、トランスミッタは定期的に（60秒ごとに）コレクタが実行されているWebサーバにGETリクエストを送信します。 Site Testは、Webサーバーから応答を受け取らない場合、エラーメッセージをsyslogに書き込み、エラーメッセージを [!DNL data workbench server] （センサーログファイルに書き込まれる）に送信します。

Site Testは、Webサーバーから応答を受け取ると、キューファイル内でWebサーバーからのパケットを探します。 パケットが表示されない場合(イベントの取り込みにコレクタが実行されていないことを示す)、Site Testはエラーメッセージをsyslogに書き込み、Adobeにエラーメッセージを送信します（これもsensor-logファイルに書き込まれます）。

Site TestがWebサーバーに送信する要求で、Site TestはUser-Agentの値を「 [!DNL Sensor] Test」に設定します。 これらのリクエストをデータセットに表示しない場合は、「 [!DNL Sensor] Test」 User-Agentをファイルまたはの [!DNL Baseline Robots List.txt] フォルダーに [!DNL Extended Robots List.txt] ファイルに追加し [!DNL Lookups][!DNL data workbench server]ます。

**送信機でサイトテストを有効にするには**

1. を実行しているマシン上で [!DNL txlogd.conf] ファイルを探し、テキストエディタ [!DNL Sensor] ーで開きます。

1. ファイル内で、「SiteTest」行を探し、次のように設定します。 [!DNL txlogd.conf] ファイルに「SiteTest」行が含まれていない場合は、設定ファイルの末尾に行を追加します。 [!DNL txlogd.conf]

   SiteTest http, *serverAddress*, *port**, resource*

   serverAddress *はWebサーバーの名前またはIPアドレス、* port *はサーバーのHTTPリスニングポート、* resource ** はサーバーのテスト時にSite Testが要求する特定のリソースです。 リ *ソースにはクエリ文字列を含めることができます* 。

   例：SiteTest http,localhost,80,/index.jsp

   複数のWebサーバーをテストするには、単に複数のSiteTest行を指定します。

## Cookieのチェック {#section-365a0182474c4dc9a5372d3e984f53de}

Webサーバー上でコレクターが実行されていることを検証する別の方法は、Webサーバーがクライアントに返す応答にcookieが設定されているかどうかを確認するこ [!DNL Sensor] とです。 コレクタが動作している場合、Webサーバーは「v1st」Cookieを返します。

cookieの名前は変更できます。 名前を付けた場合は、v1stではなく、指定した名前を探す必要があります。

このチェックは、自動化されたスクリプトまたは監視エージェントを使用して実行できます。 このタスクのサンプルスクリプトやその他のヘルプについては、Adobeのコンサルティングサービスにお問い合わせください。
