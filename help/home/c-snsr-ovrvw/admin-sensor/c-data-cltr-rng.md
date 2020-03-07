---
description: コレクタが異なる方法を使用して実行されているかどうかを確認します。
solution: Insight
title: データコレクタの実行の確認
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データコレクタの実行の確認{#confirming-that-the-data-collector-is-running}

コレクタが異なる方法を使用して実行されているかどうかを確認します。

**推奨頻度：** 5 ～ 10分ごと

* [送信機のサイトテスト機能を使用します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [[!DNL Sensor]がcookieを設定しているかどうかを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## サイトテストの使用 {#section-a5a697c3252e40f184c0b662926170f2}

コレクターが実行されていることを確認する1つの方法は、トランスミッターでサイトテスト機能を有効にすることです。 サイトテストを有効にすると、送信機は定期的に（60秒ごとに）コレクタが実行されているWebサーバにGETリクエストを送信します。 Site Testは、Webサーバーから応答を受け取らない場合、syslogにエラーメッセージを書き込み、 [!DNL data workbench server] （センサーログファイルに書き込まれる）にエラーメッセージを送信します。

Site Testは、Webサーバーから応答を受け取ると、キューファイル内でWebサーバーからのパケットを探します。 パケットが表示されない場合（イベントを取り込むためにコレクタが実行されていないことを示す）、Site Testはエラーメッセージをsyslogに書き込み、アドビにエラーメッセージを送信します（これもセンサーログファイルに書き込まれます）。

Site TestがWebサーバーに送信するリクエストで、Site TestはUser-Agentの値を「 [!DNL Sensor] Test」に設定します。これらのリクエストをデータセットに表示しない場合は、「 [!DNL Sensor] Test」 User-Agentをファイルまたは上のフォルダー内の [!DNL Baseline Robots List.txt] フ [!DNL Extended Robots List.txt] ァイルに [!DNL Lookups] 追加します [!DNL data workbench server]。

**送信機でサイトテストを有効にするには**

1. を実行して [!DNL txlogd.conf] いるコンピュータ上でフ [!DNL Sensor] ァイルを探し、テキストエディタで開きます。

1. ファイル [!DNL txlogd.conf] 内で「SiteTest」行を探し、次のように設定します。 ファイル [!DNL txlogd.conf] に「SiteTest」行が含まれていない場合は、設定ファイルの末尾に行を追加します。

   SiteTest http、 *serverAddress*、 *port*、 *resource*

   *serverAddress* はWebサーバーの名前またはIPアドレス、 *portはサーバーのHTTPリスニングポート、*** resourceはサーバーのテスト時にSite Testで要求する特定のリソースです。 リソースには *クエリ文字列* を含めることができます。

   例：SiteTest http,localhost,80,/index.jsp

   複数のWebサーバーをテストするには、複数のSiteTest行を指定します。

## Cookieの確認 {#section-365a0182474c4dc9a5372d3e984f53de}

Webサーバーでコレクターが実行されていることを確認する別の方法は、Webサーバーがクライアントに返す応答にcookieが設定されてい [!DNL Sensor] るかどうかを確認することです。 コレクタが動作している場合、Webサーバーは「v1st」Cookieを返します。

cookieの名前を変更できます。 名前を指定した場合は、v1stではなく、指定した名前を探す必要があります。

このチェックは、自動化されたスクリプトまたは監視エージェントを使用して実行できます。 このタスクに関するサンプルスクリプトやその他のヘルプについては、アドビのコンサルティングサービスにお問い合わせください。
