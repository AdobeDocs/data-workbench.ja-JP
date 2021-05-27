---
description: コレクターが別の方法で実行されているかどうかを確認します。
title: データコレクターの実行状態の確認
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# データコレクターの実行状態の確認{#confirming-that-the-data-collector-is-running}

コレクターが別の方法で実行されているかどうかを確認します。

**推奨頻度：** 5 ～ 10分ごと

* [トランスミッターでサイトテスト機能を使用します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [ [!DNL Sensor] がcookieを設定しているかどうかを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## サイトテスト{#section-a5a697c3252e40f184c0b662926170f2}の使用

コレクターが実行されていることを確認する方法の1つは、トランスミッターでサイトテスト機能を有効にすることです。 サイトテストを有効にすると、トランスミッターは定期的に（60秒ごとに）、コレクターが実行されているWebサーバーにGETリクエストを送信します。 Site TestがWebサーバから応答を受け取らない場合は、エラーメッセージをsyslogに書き込み、[!DNL data workbench server]にエラーメッセージを送信します（このメッセージはsensor-logファイルに書き込まれます）。

Site Testは、Webサーバからの応答を受け取ると、Webサーバからのパケットをキューファイルで探します。 パケットが表示されない場合（コレクタがイベントをキャプチャするために実行されていなかったことを示す）、Site Testはエラーメッセージをsyslogに書き込み、Adobeにエラーメッセージを送信します（これもsensor-logファイルに書き込まれます）。

Site TestがWebサーバーに送信する要求で、Site TestはUser-Agentの値を「[!DNL Sensor] Test」に設定します。 これらのリクエストをデータセットに表示しない場合は、 [!DNL data workbench server]の[!DNL Lookups]フォルダーの[!DNL Baseline Robots List.txt]ファイルまたは[!DNL Extended Robots List.txt]ファイルに「 [!DNL Sensor] Test 」ユーザーエージェントを追加します。

**トランスミッターでサイトテストを有効にするには**

1. [!DNL Sensor]が実行されているマシン上で[!DNL txlogd.conf]ファイルを探し、テキストエディターで開きます。

1. [!DNL txlogd.conf]ファイル内で、「SiteTest」行を探し、次のように設定します。 [!DNL txlogd.conf]ファイルに「SiteTest」行が含まれていない場合は、設定ファイルの末尾に行を追加します。

   SiteTest http、*serverAddress*、*port*、*resource*

   ここで、 *serverAddress*&#x200B;はWebサーバーの名前またはIPアドレス、 *port*&#x200B;はサーバーのHTTPリスニングポート、 *resource*&#x200B;はサーバーのテスト時にSite Testが要求する特定のリソースです。 *resource*&#x200B;にはクエリ文字列を含めることができます。

   例：SiteTest http,localhost,80,/index.jsp

   複数のWebサーバーをテストするには、複数のSiteTest行を指定するだけです。

## Cookie {#section-365a0182474c4dc9a5372d3e984f53de}の確認

Webサーバー上でコレクターが実行されていることを確認するもう1つの方法は、[!DNL Sensor]がクライアントに返されるWebサーバーの応答にCookieを設定しているかどうかを確認することです。 コレクターが動作している場合、Webサーバーは「v1st」Cookieを返します。

cookieの名前は変更できます。 既に名前を付けている場合は、v1stではなく、指定した名前を探す必要があります。

このチェックは、自動スクリプトまたは監視エージェントを使用して実行できます。 このタスクに関するサンプルスクリプトやその他のヘルプについては、Adobeコンサルティングサービスにお問い合わせください。
