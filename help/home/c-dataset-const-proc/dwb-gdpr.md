---
description: Adobe Data Workbenchは、一般的なデータ保護規制(GDPR)に準拠するためのツールとプロセスを提供します。
solution: Analytics
title: GDPRに対するData Workbenchのサポート
topic: Data workbench
translation-type: tm+mt
source-git-commit: 4002d01c4c9aaa7d8833415aba3fa5105cb7ac1f

---


# GDPRに対するData Workbenchのサポート

Adobe Data Workbenchは、GDPR (GDPR)に準拠するためのデータ準備を行うためのツールとプロ [!DNL General Data Protection Regulations] セスを提供します。

Data Workbenchは、すべてのAdobe Analyticsソリューションと同様、Adobe Analyticsのデータフィードを処理する際に、分析変数のクレンジング、削除、ラベル付けを提供することで、GDPRをサポートします。 GDPRの導入をサポートするため、アドビでは、お客様の会社の権限に従って、アドビとの契約に基づいてGDPRのプロセスを設定できます。 詳しく [は、Adobe AnalyticsとGDPRを参照してください](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)。

GDPR規制は、GDPRの実施を担当する様々な関係者の役割と義務を特定します( [GDPRとお客様のビジネスを参照](https://www.adobe.com/jp/privacy/general-data-protection-regulation.html))。

* 組織はデータコントローラーとし **て機能し** 、ニーズと制約に基づいて個人データのコンテキストと保存を決定します。 その後、アドビがこのデータを処理し、お客様に代わって保存します。
* アドビは、お客様との契約に **基づいて** 、GDPR要件を実装するためのソフトウェアとサービスを提供するデータプロセッサーの役割を果たします。
* Data WorkbenchをGDPRサービスと統合し、GDPRの基準に従うと、サイト(データの対象 ****)への訪問者は、データ・プロセッサであるアドビが「忘れ去られる権利」を行使できます。 忘れられる権利を達成するために、データコントローラーは、問題のある訪問者IDをUIまたはAPIからアドビにアップロードできます。 送信アクセ [スおよび削除リクエストを含む詳細については、](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) Adobe Analytics GDPRワークフローのドキュ [メントを参照してください](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) 。

>[!NOTE]
>
>他のデータソースの場合、組織は、CRM、POS、IVR、その他の生のデータソースなど、問題のある訪問者IDを他のログソースからクリーンアップする必要があります。 カスタムスコープのサービスパッケージは、各データソースまたは他のカスタムオプションに対し _て完全な置き換えファイルのセットを提供することで_ 、組織のサポートを提供するために利用できます。

## GDPR実装用のDWBのアップグレード

コンサルティングは、既存の実装をコンプライアンスに適合させるための適切なサービスパッケージについてアドバイスします。 詳しくは、お客様サクセスマネージャー(CSM)にお問い合わせください。

必要な場合：

* [Data Workbenchの最新バージョンにアップグレードします](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) 。 最高のセキュリティを確保するために、GDPR統合に必要なDWB 6.7リリースに新しい証明書とセキュリティ機能が追加されました。
* 従来のTSV Analyticsのイベントログを使用する場合は、 [Avroデータフィードにアップグレードします](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)。
* 既存のログを更新するためにTransformとレガシーUCP(Unified Customer Process)を使用する場合は、現在のプロセスにアップグレードします。 更新されたプロセスは、ソース間で訪問者IDをマッピングするためのマスター参照ファイルを直接生成します。
* GDPRサービスに対応するため、データ・フローを標準化。
* CRM、POS、IVR、その他の生データソースなど、他のログソースを管理するカスタムスコープのサービスパッケージを作成します。
* Analytics契約で25か月以上のデフォルトのデータ保持期間を確認します。
