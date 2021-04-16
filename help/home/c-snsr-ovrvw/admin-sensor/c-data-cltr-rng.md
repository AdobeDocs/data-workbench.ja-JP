---
description: コレクタが異なる方法で実行されているかどうかを確認します。
title: データコレクターの実行状態の確認
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# データコレクターの実行状態の確認{#confirming-that-the-data-collector-is-running}

コレクタが異なる方法で実行されているかどうかを確認します。

**推奨頻度：5 ～ 10分** ごと

* [送信機のサイトテスト機能を使用します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Cookieが設定され [!DNL Sensor] ているかどうかを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## サイトテストの使用{#section-a5a697c3252e40f184c0b662926170f2}

コレクタが実行されていることを確認する1つの方法は、トランスミッタでサイトテスト機能を有効にすることです。 サイトテストを有効にすると、トランスミッタは定期的に（60秒ごとに）コレクタが実行されているWebサーバにGETリクエストを送信します。 Site TestがWebサーバーから応答を受け取らない場合、Syslogにエラーメッセージを書き込み、[!DNL data workbench server]にエラーメッセージを送信します（これはsensor-logファイルに書き込まれます）。

Site Testは、Webサーバーから応答を受け取ると、キューファイル内でWebサーバーからのパケットを探します。 パケットが表示されない場合(イベントの取り込みにコレクタが実行されていないことを示す)、Site Testはエラーメッセージをsyslogに書き込み、Adobeにエラーメッセージを送信します（これもsensor-logファイルに書き込まれます）。

Site TestがWebサーバーに送信する要求で、Site TestはUser-Agentの値を「[!DNL Sensor] Test」に設定します。 これらのリクエストをデータセットに含めない場合は、[!DNL data workbench server]の[!DNL Lookups]フォルダーの[!DNL Baseline Robots List.txt]ファイルまたは[!DNL Extended Robots List.txt]ファイルに「[!DNL Sensor] Test」 User-Agentを追加します。

**送信機でサイトテストを有効にするには**

1. [!DNL Sensor]を実行しているマシン上で[!DNL txlogd.conf]ファイルを探し、テキストエディターで開きます。

1. [!DNL txlogd.conf]ファイルで、「SiteTest」行を探し、次のように設定します。 [!DNL txlogd.conf]ファイルに「SiteTest」行が含まれていない場合は、設定ファイルの末尾に行を追加します。

   SiteTest http, *serverAddress*, *port*, *resource*

   *serverAddress*&#x200B;はWebサーバーの名前またはIPアドレス、*port*&#x200B;はサーバーのHTTPリスニングポート、*resource*&#x200B;はサーバーのテスト時にSite Testに要求させる特定のリソースです。 *resource*&#x200B;にはクエリ文字列を含めることができます。

   例：SiteTest http,localhost,80,/index.jsp

   複数のWebサーバーをテストするには、単に複数のSiteTest行を指定します。

## Cookieのチェック{#section-365a0182474c4dc9a5372d3e984f53de}

コレクタがWebサーバー上で実行されていることを検証する別の方法は、[!DNL Sensor]がクライアントに返すWebサーバーの応答にcookieが設定されているかどうかを確認することです。 コレクタが動作している場合、Webサーバーは「v1st」Cookieを返します。

cookieの名前は変更できます。 名前を付けた場合は、v1stではなく、指定した名前を探す必要があります。

このチェックは、自動化されたスクリプトまたは監視エージェントを使用して実行できます。 このタスクのサンプルスクリプトやその他のヘルプについては、Adobeのコンサルティングサービスにお問い合わせください。
