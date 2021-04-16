---
description: AdobeData Workbenchは、GDPR(General Data Protection Regulations)に準拠するようにデータを準備するためのツールとプロセスを提供します。
title: GDPR の Data Workbench サポート
exl-id: fdc43567-0c57-4851-9073-e295258a8074
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

---

# GDPR の Data Workbench サポート

AdobeData Workbenchは、[!DNL General Data Protection Regulations] (GDPR)に準拠するようにデータを準備するためのツールとプロセスを提供します。

Data Workbenchは、すべてのAdobe Analytics・ソリューションと同様、Adobe Analyticsのデータ・フィードを処理する際に、解析変数のクレンジング、削除、ラベル付けを提供することで、GDPRをサポートします。 GDPRの導入をサポートするために、Adobeでは、Adobeとの契約に基づいて設定された会社の権限に従って、GDPRのプロセスを設定できます。 [Adobe AnalyticsとGDPRに関する追加情報](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)を参照。

GDPR規制は、GDPRの有効化を担当する様々なパーティの役割と義務を特定します（[GDPRとお客様のビジネス](https://www.adobe.com/jp/privacy/general-data-protection-regulation.html)を参照）。

* 組織は&#x200B;**データコントローラー**&#x200B;として機能し、ニーズと制約に基づいて個人データのコンテキストと保存を決定します。 次に、Adobeがこのデータを処理し、お客様に代わって保存します。
* Adobeは&#x200B;**データ・プロセッサ**&#x200B;として機能し、Adobeとの契約に基づいてGDPR要件を実装するためのソフトウェアとサービスを提供します。
* GDPRサービスとのData Workbenchの統合後、GDPR基準に従って、サイト（**データ・サブジェクト**）への訪問者は、Adobe、データ・プロセッサが「忘れられる権利」を行使する。 忘れられる権利を実現するために、データコントローラーは、障害の発生した訪問者IDをUIまたはAPIからAdobeにアップロードできます。 [送信アクセスと削除リクエスト](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html)の節など、詳細は[Adobe AnalyticsGDPRワークフロー](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html)のドキュメントを参照してください。

>[!NOTE]
>
>他のデータソースの場合、CRM、POS、IVRなどの生の訪問者ソースなど、他のログソースから、問題のあるデータIDをクリーンアップする必要があります。 カスタムスコープのサービスパッケージは、_継続的なサービスの保持がサポートまたは保守に必要となる各データソース_&#x200B;に対してファイルの完全な置き換えセットを提供することで、組織のサポートを提供します。

## GDPR向けのDWBのアップグレード

コンサルティングから、既存の実装をコンプライアンスに組み込むための適切なサービスパッケージについてアドバイスを受けます。 詳細については、Customer Success Manager(CSM)にお問い合わせください。

必要に応じて：

* [最新](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/release-notes/release-notes.html) バージョンのData Workbenchにアップグレードします。最高のセキュリティを確保するために、DWB 6.7リリースにはGDPR統合に必要な新しい証明書とセキュリティ機能が追加されています。
* 従来のTSV Analyticsイベントログを使用している場合は、[Avroデータフィード](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)にアップグレードします。
* 既存のログを更新するために、TransformとレガシーUCP(Unified Customer Process)を使用している場合は、現在のプロセスにアップグレードします。 更新されたプロセスは、ソース間で訪問者IDをマッピングするためのマスター参照ファイルを直接生成します。
* GDPRサービスに対応するためにデータ・フローを標準化。
* カスタムスコープのサービスパッケージを作成して、CRM、POS、IVRなどの他のログソース、およびその他の生データソースを管理します。
* Analytics契約で、デフォルトの25か月以上のデータ保持期間を確認します。
