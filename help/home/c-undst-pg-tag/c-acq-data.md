---
description: センサーを使用すると、Web リクエストデータ（イベントまたはログデータ）と拡張測定データを取得できます。
title: 取得できるデータの種類
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# 取得できるデータの種類{#what-kind-of-data-can-i-acquire}

{{eol}}

センサーを使用すると、Web リクエストデータ（イベントまたはログデータ）と拡張測定データを取得できます。

拡張された測定データは、通常の操作の一環として Web サーバーでは使用できません。

次のトピックについて説明します。

## Web リクエストデータ {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] web リクエストデータ（イベントまたはログデータ）を取得し、自動的に一元的な場所に転送して、分析を行うことができます。 特定のタイプのリクエストを除外し、それらのリクエストタイプに関するデータを収集しない場合を除き、 [!DNL Sensor] は、インストール先の Web サーバーでおこなわれたすべてのGETリクエストに関するデータをキャプチャします。

[!DNL Sensor] は、サーバー上でおこなわれたすべてのGETリクエストに対してこのデータ取得プロセスを自動化します。web サイトリクエストデータを取得する他の方法と比べて、ビジネス上および技術上の大きなメリットがあります。 次のような利点があります。

* 分析やレポートに不要なリクエストは、取得、輸送、保管、処理に関するコストを発生させる前に除外できます。
* サイト管理者は、手動またはスクリプトを使用して、ログファイルをバッチでローテーションする必要はありません。
* [!DNL Sensor] は、ログファイルを中央の場所に集計して、処理に容易にアクセスできるようにします。
* [!DNL Sensor] は、ログファイルを共通のデータ保持形式で整理および保存するので、分析やレポート作成の目的で使用する前に事前に処理する必要がなくなります。
* 特定のコンテンツタイプに対するほとんどのリクエストが自動的に除外されても、特定のコンテンツタイプのインスタンスをログファイルに含めることができます。
* [!DNL Sensor] はログファイルエントリを圧縮し、必要なストレージ容量を大幅に削減し、コストを削減し、長い期間分析にデータを使用できるようにします。
* [!DNL Sensor’s] フォールトトレラント機能を使用すると、中央リポジトリにログデータを配信し続けながら、システムおよびネットワークの障害を発生させることができます。
* [!DNL Sensor] web コンテンツ、プロセス、マーケティングキャンペーンを使用した対照実験を実装できます。
* [!DNL Sensor] タイムスタンプログのエントリを 100 ns 単位で記録し、新しいタイプの分析機能を使用できます。
* [!DNL Sensor] サイトの所有者は、分析とレポート作成で考慮するために、初回導入後にログエントリにデータ（測定値）を追加できます。

拡張測定データの取得について詳しくは、 [ベースライン測定の取得](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## 拡張測定データ {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] また、は、ページタグ（または埋め込みオブジェクトリクエスト）を使用して、通常の操作の一環として Web サーバーで使用できない測定データを取得することもできます。 ページタグは、次の測定に一般的に使用されます。

* 動的 Web サイト内の論理ページの表示。
* サードパーティが管理する Web サイト上でのコンテンツや広告の表示。
* ブラウザーキャッシュまたは CDN から提供されるコンテンツの表示。
* ページ読み込み時間、画面の解像度、訪問者が入力したフォームフィールドなどの測定値を含む、訪問者のブラウザーに関する詳細情報。
* ブラウザーで Web サーバーに送信されないその他のデータ。

[!DNL Sensor] は、実行中の web サーバーに対するGETリクエストに配置された情報を収集します [!DNL Sensor]. このようなリクエストは、ある種のブラウザーで特定の時間にリクエストがおこなわれたかどうかを測定する目的、または分析やレポート目的で処理できるように他の測定データをデータ収集ストリームに渡す目的など、あらゆる種類の埋め込みオブジェクトリクエストから生じます。

[!DNL Sensor] は、クライアント側とサーバー側の両方のデータ取得の世界で最も優れた機能を提供します。サーバー側の Web ログデータを取得し、埋め込みオブジェクトリクエストによるクライアント側、サードパーティサイト、キャッシュバスティング測定を収集します。 つまり、 [!DNL Sensor] は、Web サーバーで通常知られている要求データ（サーバー側の測定）と、実行中の任意の Web サーバーにデータを送信するページタグを使用して収集する追加の測定データ（クライアント側の測定）の両方を取得します [!DNL Sensor]. このような Web サーバーは、クライアント側の測定値の収集専用ですが、必須ではありません。

拡張測定データの取得について詳しくは、 [拡張測定の取得](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
