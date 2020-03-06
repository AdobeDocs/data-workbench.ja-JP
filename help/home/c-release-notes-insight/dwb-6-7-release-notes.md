---
description: Data Workbench 6.7の新機能、修正点および既知の問題です。
title: Data Workbench 6.7 のリリースノート
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.7 のリリースノート{#data-workbench-release-notes}

Data Workbench 6.7の新機能、修正点および既知の問題です。

## Data Workbench 6.7 のリリースノート {#topic-7655534554ac4a4b816af1bd73b06aad}

Data Workbench 6.7の新機能、修正点および既知の問題です。

## リリース6.7の新機能 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Data Workbench Workstation の新しい認証モデル（IMS 統合）**

Data Workbench Workstation は、ユーザー名とパスワードを使用したユーザー認証をサポートするようになりました。この新しい方法を使用すると、管理者は、カスタマーケアに問い合わせずに独自のユーザーアカウントを作成および管理できます。

詳しくは、[ユーザーの自己プロビジョニング](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html)を参照してください。

**フラットファイル参照**

Data Workbench Workstation は、ユーザー名とパスワードを使用したユーザー認証をサポートするようになりました。この新しい方法を使用すると、管理者は、カスタマーケアに問い合わせずに独自のユーザーアカウントを作成および管理できます。

フラットファイル参照では、以前は、ファイル全体がメモリ内バッファーに読み込まれていたので、メモリ使用量が膨れあがり、他のサブシステムに対するパフォーマンスの問題を生み出していました。*で* Memory Mapped Lookup Files[!DNL MemorySettings.cfg] を true に設定することで、ファイルをメモリにマッピングして Windows でキャッシュできるようになるので、メモリ使用量が最適化されます。

詳しくは、[ユーザーの自己プロビジョニング](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html)を参照してください。

**メモリ使用量**

Large Page usage can now be disabled by setting *Use Large Pages* to false in [!DNL MemorySettings.cfg]. 詳しくは、[メモリ使用量の監視](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html)を参照してください。

**セキュリティ暗号**

ECDHE および DHE のサポートが追加されました。

Email support in [!DNL User List.cfg]

Added support for Email attribute in [!DNL User List.cfg]. 詳しくは、[グループメンバーのユーザー管理](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html)を参照してください。

**ヘルプメニュー**

ヘルプメニューに証明書ディレクトリを開くためのショートカットが表示されるようになりました。

**`TargetBulkUpload`エクスポート&#x200B;**

停止したバッチを追跡するために、書き出しトレースファイルおよび `targetbulkuploadexportname.log.completed` ファイルの最後に URL が提供されます。

新しいファイルの [!DNL TargetBulkUpload.cfg] は、最大タイムアウト間隔（分単位）を設定するために提供されました。ファイルは[!DNL Server\Admin\Export\]にあります。

## 修正点 {#section-160baf6ea04c45a993777ee4260691ed}

* キャンペーンクリックスルーディメンションに水増し値が表示されていた問題を修正しました。
* レポートサーバーからのExcelファイルの生成に関する問題を修正しました。
* RC4暗号は、デフォルトで無効になりました。
* 値の凡例テーブルにディメンション要素を追加すると、Data Workbenchワークステーションがクラッシュする問題を修正しました。
* Data WorkbenchでAAMへの書き出しでタイムアウトが発生する問題を修正しました。
* 十分なアクセスレベルを持たないユーザーがワークスペースをサーバーに保存した場合に、Data Workbenchワークステーションがクラッシュする問題を修正しました。
* 日付形式が正しくない、またはローカライズされな [!DNL report.cfg] い問題を修正しました。
* AVROフィードのモバイル行と製品行にわかりにくい情報が表示される問題を修正しました。
* とファイルの順序を変更できない問題 `*.1cd` を修 `*.1ad` 正しまし [!DNL order.txt]た。

* クラスタリングの実行中に、期待値最大化アルゴリズムの「サーバーに送信」オプションが無効になりました。
* 実行可能ファイルの停止と完 `TargetBulkUpload` 全に実行できなかった問題を修正しました。

## 既知の問題 {#section-d76322bdac5043f087ab303dc68b8fff}

* ログアウト時に、ファイル [!DNL user cache.db] は消去されます。
* 「+」または「%」文字を含むIMSユーザーの電子メールアドレスはサポートされていません。
* 接続状態のエラー時に、ユーザーがログアウトできない。 回避策として、オフラインモードでログアウトします。
* 高解像度で高DPIのハードウェアで、IMSログインウィンドウが正しくレンダリングされない。 回避策として、右クリックして/に移動し、 [!DNL Insight.exe] ボックスにチ **[!UICONTROL Properties]** ェッ **[!UICONTROL Compatability]**&#x200B;クマークを付けてくださ **[!UICONTROL Override high DPI scaling behavior]**&#x200B;い。

## アップグレード要件 {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. ビルド [!DNL trust_ca_cert.pem] パッケージの一部であるInsightサーバーを更新します。
1. https://aap.adobe.comから新しい証明書をダウンロードして、サーバーとレポートサーバーの証明書を更新 [します](https://aap.adobe.com)。
1. WorkstationとReport Serverを自動的に更新するには、License Serverからダウンロー [!DNL trust_ca_cert.pem] ドして、両方のWorkstationとReport Serverを手動で更新します。
1. Sensorの自動更新機能は、Insight Serverバージョン6.70と通信するためにバージョン5.0が必要です。また、Sensorは、License Serverからダ [!DNL trust_ca_cert.pem] ウンロードして手動で更新する必要があります。

## システムの更新 {#section-c1b4949ea734440aa62658ac313261db}

新しいファイルには次のものが含まれます。

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

更新されたファイルには、次が含まれます。

1. [!DNL trust_ca_cert.pem] を設定します。
1. [!DNL Access Control.cfg] を追加します。
1. [!DNL Base\Context\meta.cfg] サポートする開始日および終了日の形式 [!DNL Report.cfg]

1. IMS認証のプロ [!DNL Insight.cfg] キシをサポートするための追加機能：

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Data Workbench 5.3 から 5.52 までについては、[アーカイブされているリリースノート](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html)を参照してください。
