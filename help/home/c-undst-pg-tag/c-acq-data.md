---
description: センサーを使用すると、Webリクエストデータ（イベントデータまたはログデータ）と拡張測定データを取得できます。
title: 取得できるデータの種類
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# 取得できるデータの種類{#what-kind-of-data-can-i-acquire}

センサーを使用すると、Webリクエストデータ（イベントデータまたはログデータ）と拡張測定データを取得できます。

拡張測定データは、通常の操作の一環としてWebサーバーで使用できません。

以下のトピックについて説明します。

## Webリクエストデータ{#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] webリクエストデータ（イベントまたはログデータ）を取得し、自動的に中央の場所に転送して、分析を行うことができます。特定のタイプのリクエストを除外し、それらのリクエストタイプに関するGETを収集しない場合を除き、 [!DNL Sensor]は、インストール先のWebサーバーでおこなわれたすべてのデータリクエストに関するデータを取り込みます。

[!DNL Sensor] は、お使いのサーバー上でおこなわれるすべてのGETリクエストに対して、このデータ取得プロセスを自動化します。webサイトリクエストデータを取得する他の方法と比べて、ビジネス上および技術上の大きなメリットがあります。次のような利点があります。

* 分析やレポートに不要なリクエストは、獲得、輸送、保管、処理に関するコストが発生する前に除外できます。
* サイト管理者は、手動またはスクリプトを使用して、ログファイルをバッチで回転する必要はありません。
* [!DNL Sensor] は、ログファイルを1か所に集約して、処理を容易におこなえるようにします。
* [!DNL Sensor] は、ログファイルを共通のデータ保持形式で整理して保存するので、分析やレポート作成の目的で使用する前に、ログファイルを前処理する必要がなくなります。
* 特定のコンテンツタイプに対するほとんどのリクエストが自動的に除外されても、特定のコンテンツタイプのインスタンスをログファイルに含めることができます。
* [!DNL Sensor] はログファイルエントリを圧縮し、必要なストレージ容量を大幅に削減し、コストを削減し、長い期間分析にデータを使用できるようにします。
* [!DNL Sensor’s] フォールトトレラント機能を使用すると、ログデータを中央リポジトリに確実に配信しながら、システムおよびネットワークの障害を発生させることができます。
* [!DNL Sensor] webコンテンツ、プロセス、マーケティングキャンペーンを使用して、対照実験を実装できます。
* [!DNL Sensor] タイムスタンプログエントリを100 ns単位で記録し、新しいタイプの分析機能を使用できます。
* [!DNL Sensor] を使用すると、分析とレポート作成で考慮するために、最初の実装後にサイトの所有者がデータ（測定値）をログエントリに追加できます。

拡張測定データの取得について詳しくは、[ベースライン測定の取得](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe)を参照してください。

## 拡張測定データ{#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] また、は、ページタグ（または埋め込みオブジェクトリクエスト）を使用して、Webサーバーが通常の操作の一環として使用できない測定データを取得することもできます。ページタグは、次の測定に一般に使用されます。

* 動的Webサイトでの論理ページの表示。
* サードパーティが管理するWebサイトでのコンテンツや広告の表示。
* ブラウザーキャッシュまたはCDNから提供されるコンテンツの表示。
* ページ読み込み時間、画面解像度、訪問者が入力したフォームフィールドなどの測定値を含む、訪問者のブラウザーに関する詳細情報。
* ブラウザーからWebサーバーに送信されないその他のデータ。

[!DNL Sensor] は、実行中のwebサーバーに対しておこなわれたGETリクエストに含まれる情報を収集しま [!DNL Sensor]す。このようなリクエストは、あらゆる種類の埋め込みオブジェクトリクエストから発生する場合があります。リクエストは、特定のブラウザーで特定の時間にリクエストされたことを測定するか、分析やレポート用に処理されるように他の測定データをデータ収集ストリームに渡します。

[!DNL Sensor] は、クライアント側とサーバー側の両方のデータ取得の世界で最も優れた機能を提供します。サーバー側のWebログデータを取得し、埋め込みオブジェクトリクエストによるクライアント側、サードパーティサイト、キャッシュバスティングの測定値を収集します。つまり、[!DNL Sensor]は、Webサーバーで通常知られている要求データ（サーバー側の測定）と、[!DNL Sensor]を実行する任意のWebサーバーにデータを送信するページタグ（クライアント側の測定）を使用して収集する追加の測定データの両方を取得します。 このようなWebサーバーは、クライアント側の測定値の収集専用ですが、必須ではありません。

拡張測定データの取得について詳しくは、「[拡張測定の取得](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944)」を参照してください。
