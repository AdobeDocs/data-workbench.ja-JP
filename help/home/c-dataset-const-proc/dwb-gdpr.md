---
description: AdobeData Workbenchは、一般データ保護規則 (GDPR) に準拠するためのデータ準備を行うためのツールとプロセスを提供します。
title: GDPR の Data Workbench サポート
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 4%

---

# GDPR の Data Workbench サポート

{{eol}}

AdobeData Workbenchは、 [!DNL General Data Protection Regulations] (GDPR)。

すべてのAdobe Analyticsソリューションと同様に、Data Workbenchは、Adobe Analyticsのデータフィードの処理時に分析変数のクレンジング、削除、ラベル付けを提供することで、GDPR をサポートします。 GDPR 実装をサポートするために、Adobeを使用すると、Adobeとの間で締結された会社の権限に従って、GDPR のプロセスを設定できます。 詳しくは、 [Adobe Analyticsと GDPR を参照してください](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=ja).

GDPR 規制により、GDPR の実施に責任を負う様々な関係者の役割と義務を特定します ( [GDPR とビジネス](https://www.adobe.com/jp/privacy/general-data-protection-regulation.html)) をクリックします。

* 組織が **データ管理者** のニーズや制約に基づいて個人データのコンテキストと保持を判断する。 Adobeは、その後、お客様に代わってこのデータを処理および保存します。
* Adobeは **データ処理装置** お客様との合意に基づいて GDPR 要件を実装するためのソフトウェアおよびサービスをAdobeに提供する。
* Data Workbenchを GDPR サービスと統合し、GDPR 標準に従って、サイト ( **データ主体**) は、Adobe（データ処理者）によって「忘れられる権利」を行使できます。 忘れられる権利を達成するには、データ管理者が、問題が発生した訪問者 ID を UI または API からAdobeにアップロードできるので、 詳しくは、 [Adobe Analytics GDPR Workflow](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-workflow.html?lang=en) 詳しくは、 [アクセス要求と削除要求の送信](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html) 」セクションに入力します。

>[!NOTE]
>
>その他のデータソースについては、CRM、POS、IVR、その他の生データソースなど、他のログソースからの問題のある訪問者 ID のクリーンアップを組織が担当します。 カスタムスコープのサービスパッケージを利用して、 _各データソースに対してファイルの完全な置き換えセットを提供する_ 継続中のサービス保持者は、サポートまたは維持する必要があります。

## DWB の GDPR 実装へのアップグレード

コンサルティングは、既存の実装をコンプライアンスに移行するための適切なサービスパッケージについてアドバイスします。 詳しくは、カスタマーサクセスマネージャー (CSM) にお問い合わせください。

必要に応じて以下を実行します。

* [最新バージョンにアップグレード](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) Data Workbench 最高レベルのセキュリティを確保するために、GDPR 統合に必要な DWB 6.7 リリースに新しい証明書とセキュリティ機能が追加されました。
* 従来の TSV Analytics イベントログを使用している場合は、 [AVRO データフィード](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* 既存のログを更新するために Transform でレガシー UCP(Unified Customer Process) を使用している場合は、現在のプロセスにアップグレードします。 更新されたプロセスは、ソースをまたいで訪問者 ID をマッピングするためのマスター参照ファイルを直接生成します。
* GDPR サービスに対応するようにデータフローを標準化します。
* CRM、POS、IVR、その他の生データソースなどの他のログソースを管理するために、カスタムスコープのサービスパッケージを確立します。
* Analytics 契約で、25 ヶ月以上のデフォルトのデータ保持期間を確認します。
