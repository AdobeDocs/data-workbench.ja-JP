---
description: クエリ API の設定に関するクイックガイドです。
title: クエリ API のセットアップ
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
exl-id: 8b9dace8-4dad-434c-aec3-2f6ca872a5f6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%

---

# クエリ API のセットアップ{#query-api-setup}

{{eol}}

クエリ API の設定に関するクイックガイドです。

クエリ API を設定するには、次の手順に従います。

1. クエリ API 証明書の取得

   Tech Ops チームにメールを送信するAdobeメール — `Dataworkbench@adobe.com`.

   クエリ API で使用する CN 名を指定してください（のような汎用名を指定してください）。 `<Client>` クエリ API) を参照してください。

   >[!NOTE]
   >
   >Tech Ops が証明書を生成し、URL にアップロードします。 チケットの生成に成功した場合、Adobeコンサルタントにテクニカルオペレーションから通知を受け取った後、チケットを返送するように、テクニカルコンサルタントにお知らせください。

1. API Stunnel のダウンロードと抽出。 コンサルタントから api-stunnel ファイルを受け取ります。

   お使いのマシンに Perl がインストールされていることを確認します。

   抽出したフォルダー（ファイルをコピーするフォルダーパス）で、クエリ API 証明書を *スタンネル* フォルダー。

1. Stunnel.conf の設定

   という名前のファイルが必要です。 *stunnel.conf* 内側 *Stunnel* フォルダー（証明書をコピーした場所）。

   ファイルをメモ帳で編集します。

   ![](assets/dwb_impl_API1.png)

   次のようにパラメーターを変更します。 ![](assets/dwb_impl_API2.png)

   このファイルでは、2 つのパラメーターを変更する必要があります。

   * *証明書* =証明書の名前。 この例では、Aadhithya Ramani QAPI Client.pem です。
   * *接続* =メイン DPU のサーバ名。

1. のコピー *クエリ.pm*.

   この *クエリ.pm* ファイルが Insight API フォルダーで使用可能になります。

   を *クエリ.pm* ファイルを作成し、Perl ライブラリフォルダに貼り付けます ( 通常は*C:\Perl64\lib *ですが、Perl がマシンにインストールされている場所を確認してください )。

1. を変更します。 *api-http.pl* ファイル

   api-http.pl ファイルは api-stunnel フォルダーで入手できます。

   変更するパラメーターは 1 つだけです

   *$profile* =クエリ API を設定するプロファイル名

1. クエリ API をインストールします。

   システムのコマンドプロンプトを「Administrator」として開き、 *スタンネル* 例： ![](assets/dwb_impl_API3.png)

   次のコマンドを実行します。 *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   コマンドを実行すると、ウィンドウがポップアップ表示され、 *スタンネル* がインストールされている。

   >[!NOTE]
   >
   >コマンドを実行すると、ウィンドウがポップアップ表示され、 *スタンネル* がインストールされている。

1. クエリ API スタンネル設定のテスト

   このプロセスの最後の手順は、クエリ API の設定をテストすることです。 api-stunnel ディレクトリのインストールに使用したコマンドプロンプトで、 ![](assets/dwb_impl_API5.png)

   次のコマンドを使用して、そのフォルダで使用可能な Perl スクリプトを実行します。* perl api-http.pl* ![](assets/dwb_impl_API6.png)

   スクリプトを実行した後の結果は、以下のスクリーンショットのようになります ( 結果の日時と値は、クエリ API を設定したプロファイルの時刻と他のパラメーターに応じて変わります（手順 6）。 ![](assets/dwb_impl_API7.png)
