---
description: AdobeData Workbenchは、一般データ保護規則(GDPR)に準拠するためのデータ準備のためのツールとプロセスを提供します。
title: GDPR の Data Workbench サポート
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

---

# GDPR の Data Workbench サポート

AdobeData Workbenchは、[!DNL General Data Protection Regulations](GDPR)に準拠するためにデータを準備するためのツールとプロセスを提供します。

すべてのAdobe Analyticsソリューションと同様に、Data Workbenchは、Adobe Analyticsのデータフィードを処理する際の分析変数のクレンジング、削除、ラベル付けを提供することで、GDPRをサポートします。 GDPR実装をサポートするために、Adobeを使用すると、Adobeとの契約に基づいて、会社の権限に従ってGDPRのプロセスを設定できます。 [Adobe AnalyticsとGDPRで追加情報を参照してください。](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)

GDPR規制は、GDPRの実施を担当する様々な関係者の役割と義務を特定します（[GDPRとお客様のビジネス](https://www.adobe.com/jp/privacy/general-data-protection-regulation.html)を参照）。

* 組織は&#x200B;**データ管理者**&#x200B;として機能し、ニーズと制約に基づいて個人データのコンテキストと保持を決定します。 Adobeは、その後、お客様に代わってこのデータを処理および保存します。
* Adobeは、**データ処理者**&#x200B;として機能し、Adobeとの契約に基づいてGDPR要件を実装するためのソフトウェアとサービスを提供します。
* GDPRサービスとのData Workbenchの統合後、GDPR標準に従って、サイト（**データ主体**）への訪問者は、Adobe（データ処理者）によって「忘れられる権利」を行使できます。 忘れられる権利を実現するには、データ管理者が、問題のある訪問者IDをUIまたはAPIからAdobeにアップロードできます。 詳しくは、[送信アクセス要求および削除要求](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html)の節を含む、[Adobe Analytics GDPRワークフロー](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html)のドキュメントを参照してください。

>[!NOTE]
>
>その他のデータソースについては、CRM、POS、IVR、その他の生データソースなど、他のログソースからの問題のある訪問者IDをクリーンアップする必要があります。 カスタムスコープのサービスパッケージは、各データソース&#x200B;_に対して継続的なサービス保持がサポートまたは保守に必要なファイルの完全な置き換えセットを提供する_&#x200B;によって、組織のサポートを提供します。

## GDPR実装用のDWBのアップグレード

コンサルティングは、既存の実装をコンプライアンスに移行するための適切なサービスパッケージについてアドバイスします。 詳しくは、カスタマーサクセスマネージャー(CSM)にお問い合わせください。

必要に応じて、

* [最新バージョンの](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/release-notes/release-notes.html) Data Workbench最高のセキュリティを実現するために、GDPR統合に必要なDWB 6.7リリースに新しい証明書とセキュリティ機能が追加されました。
* 従来のTSV Analyticsイベントログを使用している場合は、[Avroデータフィード](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)にアップグレードします。
* 既存のログを更新するために、TransformでレガシーUCP(Unified Customer Process)を使用している場合は、現在のプロセスにアップグレードします。 更新されたプロセスは、ソース間で訪問者IDをマッピングするためのマスター参照ファイルを直接生成します。
* GDPRサービスに対応するようにデータフローを標準化します。
* CRM、POS、IVR、その他の生データソースなどの他のログソースを管理するために、カスタムスコープのサービスパッケージを確立します。
* Analytics契約で、デフォルトの25ヶ月以上のデータ保持期間を確認します。
