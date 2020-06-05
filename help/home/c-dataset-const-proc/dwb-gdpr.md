---
description: Adobe Data Workbenchは、General Data Protection Regulations(GDPR)に準拠するようにデータを準備するためのツールとプロセスを提供します。
solution: Analytics
title: GDPRに対するData Workbenchのサポート
topic: Data workbench
translation-type: tm+mt
source-git-commit: 279e71f3da3f0ebc29091e88b87666a22a36a8d6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# GDPRに対するData Workbenchのサポート

Adobe Data Workbenchは、 [!DNL General Data Protection Regulations] (GDPR)に準拠するようにデータを準備するためのツールとプロセスを提供します。

Data Workbenchは、すべてのAdobe Analyticsソリューションと同様、Adobe Analyticsのデータフィードを処理する際に、分析変数のクレンジング、削除、およびラベル付けを提供することで、GDPRをサポートします。 GDPRの導入をサポートするため、Adobeでは、Adobeとの契約に基づいて設定された会社の権限に従って、GDPRのプロセスを設定できます。 詳しくは、 [Adobe AnalyticsとGDPRを参照してください](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)。

GDPR規制は、GDPRの実施を担当する様々なパーティの役割と義務を特定します( [GDPRとお客様のビジネス](https://www.adobe.com/jp/privacy/general-data-protection-regulation.html))。

* 組織は、 **データコントローラーとして機能し** 、ニーズと制約に基づいて個人データのコンテキストと保存を決定します。 その後、アドビがこのデータを処理し、お客様に代わって保存します。
* アドビは、アドビとの契約に基づき、GDPR要件を実装するためのソフトウェアとサービスを提供する **データプロセッサーとしての役割を果たします** 。
* Data WorkbenchとGDPRサービスが統合され、GDPRの基準に従って、サイト( **データサブジェクト**)への訪問者は、データプロセッサーであるアドビが「忘れられる権利」を行使できます。 忘れ去られる権利を実現するために、データコントローラーは、問題のある訪問者IDをUIまたはAPIからアドビにアップロードできます。 詳しくは、 [Adobe Analytics GDPR Workflow](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) (リクエストの [送信および削除)の節を参照してください](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) 。

>[!NOTE]
>
>他のデータソースの場合、CRM、POS、IVRなどの生の訪問者ソースなど、他のログソースから、問題のあるデータIDをクリーンアップする必要があります。 カスタムスコープのサービスパッケージは、継続的なサービスの保持がサポートまたは保守を必要とする各データソースに対して完全な置き換えファイルのセットを _提供することで_ 、組織のサポートを提供するために利用できます。

## GDPR向けのDWBのアップグレード

コンサルティングから、既存の実装をコンプライアンスに組み込むための適切なサービスパッケージについてアドバイスを受けます。 詳細については、Customer Success Manager(CSM)にお問い合わせください。

必要に応じて：

* [Data Workbenchの最新バージョン](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/release-notes/release-notes.html) 。 最高のセキュリティを確保するために、DWB 6.7リリースにはGDPR統合に必要な新しい証明書とセキュリティ機能が追加されています。
* 従来のTSV Analyticsイベントログを使用している場合は、 [Avroデータフィードにアップグレードし](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)ます。
* 既存のログを更新するために、TransformとレガシーUCP(Unified Customer Process)を使用している場合は、現在のプロセスにアップグレードします。 更新されたプロセスは、ソース間で訪問者IDをマッピングするためのマスター参照ファイルを直接生成します。
* GDPRサービスに対応するためにデータ・フローを標準化。
* カスタムスコープのサービスパッケージを作成して、CRM、POS、IVRなどの他のログソース、およびその他の生データソースを管理します。
* Analytics契約で、デフォルトの25か月以上のデータ保持期間を確認します。
