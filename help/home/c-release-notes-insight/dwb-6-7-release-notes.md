---
description: Data Workbench6.7の新機能、修正点および既知の問題です。
title: Data Workbench 6.7 のリリースノート
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
exl-id: e5ec3224-66d1-47a6-9bf3-8be9f6568b8d
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 36%

---

# Data Workbench 6.7 のリリースノート{#data-workbench-release-notes}

Data Workbench6.7の新機能、修正点および既知の問題です。

## Data Workbench 6.7 のリリースノート {#topic-7655534554ac4a4b816af1bd73b06aad}

Data Workbench6.7の新機能、修正点および既知の問題です。

## リリース6.7の新機能 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Data Workbench Workstation の新しい認証モデル（IMS 統合）**

Data Workbench Workstation は、ユーザー名とパスワードを使用したユーザー認証をサポートするようになりました。この新しい方法を使用すると、管理者は、カスタマーケアに問い合わせずに独自のユーザーアカウントを作成および管理できます。

詳しくは、[ユーザーの自己プロビジョニング](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html)を参照してください。

**フラットファイル参照**

Data Workbench Workstation は、ユーザー名とパスワードを使用したユーザー認証をサポートするようになりました。この新しい方法を使用すると、管理者は、カスタマーケアに問い合わせずに独自のユーザーアカウントを作成および管理できます。

フラットファイル参照では、以前は、ファイル全体がメモリ内バッファーに読み込まれていたので、メモリ使用量が膨れあがり、他のサブシステムに対するパフォーマンスの問題を生み出していました。** で Memory Mapped Lookup Files を [!DNL MemorySettings.cfg]true に設定することで、ファイルをメモリにマッピングして Windows でキャッシュできるようになるので、メモリ使用量が最適化されます。

詳しくは、[ユーザーの自己プロビジョニング](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html)を参照してください。

**メモリ使用量**

[!DNL MemorySettings.cfg]で「*大きいページを使用*」をfalseに設定することで、大きいページの使用を無効にできるようになりました。 詳しくは、[メモリ使用量の監視](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html)を参照してください。

**セキュリティ暗号**

ECDHE および DHE のサポートが追加されました。

[!DNL User List.cfg]での電子メールのサポート

[!DNL User List.cfg]にEメール属性のサポートを追加しました。 詳しくは、[グループメンバーのユーザー管理](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html?lang=en)を参照してください。

**ヘルプメニュー**

ヘルプメニューに証明書ディレクトリを開くためのショートカットが表示されるようになりました。

**`TargetBulkUpload`export**

停止したバッチを追跡するために、書き出しトレースファイルおよび `targetbulkuploadexportname.log.completed` ファイルの最後に URL が提供されます。

新しいファイルの [!DNL TargetBulkUpload.cfg] は、最大タイムアウト間隔（分単位）を設定するために提供されました。ファイルは [!DNL Server\Admin\Export\]にあります。

## 修正点 {#section-160baf6ea04c45a993777ee4260691ed}

* キャンペーンのクリックスルーディメンションで水増しされた値が表示されていた問題を修正しました。
* レポートサーバーからのExcelファイルの生成に関する問題を修正しました。
* RC4暗号はデフォルトで無効になりました。
* 値の凡例テーブルにData Workbench要素を追加すると、ディメンションワークステーションがクラッシュする問題を修正しました。
* タイムアウトを引き起こしていた、AAMへのData Workbenchの書き出しに関する問題を修正しました。
* 十分なアクセスレベルを持たないData Workbenchがワークスペースをサーバーに保存した場合にワークステーションがクラッシュする問題を修正しました。
* [!DNL report.cfg]の日付形式が正しくない、またはローカライズされていなかった問題を修正しました。
* AVROフィードのモバイル行と製品行に、わかりにくい情報が表示されていた問題を修正しました。
* [!DNL order.txt]内の`*.1cd`ファイルと`*.1ad`ファイルの順序が正しくない問題を修正しました。

* クラスタリングの実行中、期待値最大化アルゴリズムの「サーバーへ送信」オプションが無効になりました。
* `TargetBulkUpload`実行可能ファイルの停止と、完全に実行できない問題を修正しました。

## 既知の問題 {#section-d76322bdac5043f087ab303dc68b8fff}

* ログアウト時に、[!DNL user cache.db]ファイルが消去されます。
* 「+」文字または「%」文字を含むIMSユーザーEメールアドレスはサポートされていません。
* 接続状態のエラー中にログアウトできない。 回避策として、オフラインモードでログアウトします。
* 高解像度および高DPIの一部のハードウェアで、IMSログインウィンドウが正しくレンダリングされない。 回避策として、[!DNL Insight.exe]を右クリックし、**[!UICONTROL Properties]** > **[!UICONTROL Compatability]**&#x200B;に移動して、ボックス&#x200B;**[!UICONTROL Override high DPI scaling behavior]**&#x200B;をオンにします。

## アップグレード要件 {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. ビルドパッケージの一部であるInsightサーバーの[!DNL trust_ca_cert.pem]を更新します。
1. [https://aap.adobe.com](https://aap.adobe.com)から新しい証明書をダウンロードして、サーバーとレポートサーバーの証明書を更新します。
1. ワークステーションとレポートサーバを自動的に更新するには、ライセンスサーバから[!DNL trust_ca_cert.pem]をダウンロードして、両方のを手動で更新します。
1. Sensorの自動更新機能を使用するには、Insight Serverバージョン6.70と通信するためにバージョン5.0が必要です。また、Sensorの[!DNL trust_ca_cert.pem]をLicense Serverからダウンロードして手動で更新する必要があります。

## システムの更新 {#section-c1b4949ea734440aa62658ac313261db}

新しいファイルは次のとおりです。

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

更新されたファイルには、次が含まれます。

1. [!DNL trust_ca_cert.pem] （すべてのコンポーネント）
1. [!DNL Access Control.cfg] を使用して、IMS設定をサポートします。
1. [!DNL Base\Context\meta.cfg] で開始日と終了日の形式をサポートする場合  [!DNL Report.cfg]

1. IMS認証のプロキシをサポートするため、[!DNL Insight.cfg]に次の機能が追加されました。

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Data Workbench 5.3 から 5.52 までについては、[アーカイブされているリリースノート](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html)を参照してください。
