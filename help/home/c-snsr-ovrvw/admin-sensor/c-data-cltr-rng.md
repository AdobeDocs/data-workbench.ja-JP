---
description: コレクターが別の方法で実行されているかどうかを確認します。
title: データコレクターの実行状態の確認
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# データコレクターの実行状態の確認{#confirming-that-the-data-collector-is-running}

{{eol}}

コレクターが別の方法で実行されているかどうかを確認します。

**推奨頻度：** 5 ～ 10 分ごと

* [トランスミッターのサイトテスト機能を使用します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [チェック [!DNL Sensor] は cookie を設定しています。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## サイトテストの使用 {#section-a5a697c3252e40f184c0b662926170f2}

コレクターが実行中であることを確認する方法の 1 つは、トランスミッターでサイトテスト機能を有効にすることです。 サイトテストを有効にすると、トランスミッターは定期的に（60 秒ごとに）GETリクエストを、コレクターが実行されている Web サーバーに送信します。 Site Test が Web サーバから応答を受け取らない場合、Syslog にエラーメッセージを書き込み、エラーメッセージを [!DNL data workbench server] （sensor-log ファイルに書き込まれます）。

Site Test は、Web サーバからの応答を受け取ると、Web サーバからのパケットをキューファイルで探します。 パケットが表示されない場合（コレクタがイベントをキャプチャするために実行していなかったことを示す）、Site Test はエラーメッセージを syslog に書き込み、Adobeにエラーメッセージを送信します（sensor-log ファイルにも書き込まれます）。

サイトテストが Web サーバーに送信する要求で、Site Test は User-Agent 値を「 [!DNL Sensor] テスト」 これらのリクエストをデータセットに表示したくない場合は、 [!DNL Sensor] Test」を実行し、 [!DNL Baseline Robots List.txt] ファイルまたは [!DNL Extended Robots List.txt] ファイルを [!DNL Lookups] フォルダーを [!DNL data workbench server].

**トランスミッターでサイトテストを有効にするには**

1. を [!DNL txlogd.conf] ～があるマシン上のファイル [!DNL Sensor] を実行し、テキストエディターで開きます。

1. 内 [!DNL txlogd.conf] ファイルで、「SiteTest」行を探し、次に示すように設定します。 次に、 [!DNL txlogd.conf] ファイルには「SiteTest」行は含まれていません。設定ファイルの最後に行を追加するだけです。

   SiteTest http, *serverAddress*, *ポート*, *リソース*

   場所 *serverAddress* は、Web サーバーの名前または IP アドレスです。 *ポート* はサーバーの HTTP リスニングポート、 *リソース* は、サーバーのテスト時にサイトテストから要求する特定のリソースです。 注意： *リソース* には、クエリー文字列を含めることができます。

   例：SiteTest http,localhost,80,/index.jsp

   複数の Web サーバーをテストするには、複数の SiteTest 行を指定するだけです。

## Cookie の確認 {#section-365a0182474c4dc9a5372d3e984f53de}

Web サーバー上でコレクタが実行されていることを確認するもう 1 つの方法は、 [!DNL Sensor] は、Web サーバーがクライアントに返す応答に cookie を設定しています。 コレクターが動作している場合、Web サーバーは「v1st」Cookie を返します。

cookie の名前は変更できます。 既に名前を付けた場合は、v1st ではなく、指定した名前を検索する必要があります。

このチェックは、自動化されたスクリプトまたは監視エージェントを使用して実行できます。 サンプルスクリプトやこのタスクに関する追加のヘルプについては、Adobeコンサルティングサービスにお問い合わせください。
