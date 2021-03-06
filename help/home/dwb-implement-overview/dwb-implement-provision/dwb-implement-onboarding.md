---
description: Adobe Analytics Premium(AAP)のコンポーネントであるAdobeData Workbench(DWB)のオンボーディングプロセスを開始するには、次の手順に従います。
title: DWB Managed Services の基本的なオンボーディング手順
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
exl-id: 49fb6afe-b417-4554-9238-fd6381c00029
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# DWB Managed Services の基本的なオンボーディング手順{#basic-onboarding-instructions-for-dwb-managed-services}

Adobe Analytics Premium(AAP)のコンポーネントであるAdobeData Workbench(DWB)のオンボーディングプロセスを開始するには、次の手順に従います。

これらのオンボーディング手順は、コンサルティングサービスを使用せずに、Adobe管理サービスを使用してData Workbenchを単一のレポートスイートで実装するお客様向けです。 DWBを実装する新しいAAPユーザーの場合、Adobeオンボーディングチームが最初の連絡先になります。 Adobe Analytics Standardまたは以前のバージョンのDWBからアップグレードする場合は、Adobeカスタマーサクセスマネージャーがお手伝いします。

## オンボーディング情報：お客様から必要な情報 {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobeから次の情報が届きます。

* DWBのプライマリユーザーを特定して、そのユーザー専用の証明書をネットワークディレクトリに生成します。 プライマリユーザーは、Adobeカスタマーケアと対話するポイントパーソンとしても機能します。
* DWBに読み込むレポートスイートを特定します。

次に、AdobeのDigital Marketingチームが、情報を取得して、プロファイルの作成、アカウントの設定、DWB用の設定ファイルの配信をおこないます。

**Adobeのオンボーディングタスク**

* AdobeカスタマーケアがDWBライセンスのアカウントを作成します。 Adobeカスタマーケアが、プライマリユーザー用のDWB証明書を生成します。
* Adobeカスタマーケアは、プライマリユーザーを「サポート対象ユーザー」と定義します。このユーザーは、サポート対象の通話と問題解決について特定された個人を指します。
* Adobeカスタマーケアが、DWBライセンスとソフトウェアポータル（ソフトドキュメント/ソフトウェアおよびドキュメントプロファイル）にソフトウェアパッケージを読み込み、組織にダウンロードします。
* AdobeのTechOpsチームは、DWBの実稼動環境と開発環境、および（契約ごとの）プロファイルを準備します。
* AdobeTechOpsチームが、データフィードとプロファイル管理スクリプトを設定します。
* AdobeTechOpsチームがDWB設定ファイル(Insight.cfg)を作成し、組織に関連するオンボーディングタスクを担当するAdobeオンボーディングチームに送信します。

データフィードをカスタマイズし、資格情報、証明書、およびプロファイル設定を生成した後、Adobeカスタマーケアは設定ファイルと資格情報を送信して次の手順に進みます。

## カスタムインストールファイルへのアクセス {#section-26962bf57fef435dbd1c5486d4b6f688}

これらのセットアップファイルは、Adobeカスタマーケアから受け取り、DWBワークステーションをクライアントコンピューターにインストールします。

* カスタムDWB設定ファイル(Insight.cfg)

   クライアントコンピューター上のこの構成ファイルには、管理されたDWBサーバーへの接続が含まれます。

* DWBセットアップウィザードと、プライマリユーザーの名前を含む必要な証明書（.pemファイル）をダウンロードするためのライセンスポータルのログイン資格情報。

**追加のセットアップファイルのダウンロード**

1. 参照先：license.visualsciences.comを使用して、ライセンス証明書とDWBセットアップウィザードの実行可能ファイルをダウンロードします。
1. 組織（アカウント名）、プライマリユーザーの名前、Adobeカスタマーケアから受け取ったパスワードを入力し、「ログイン」をクリックします。

   >[!NOTE]
   >
   >この時点で、ブラウザーから電子証明書を提示するように求められる場合があります。その場合は、「キャンセル」をクリックしてダイアログボックスを閉じます。

1. ダウンロードセクションで、AdobeData Workbench(`<PrimaryUser>`.pem)のインスタンス用に発行された証明書を探し、ダウンロードします。
1. ダウンロードセクションで標準クライアントインストーラーを探し、DWBセットアップウィザード(InsightSetup-x.xx.exeファイル)をダウンロードします。
1. Adobeカスタマーケアからファイルを受け取り、ダウンロードした後、DWBセットアップウィザードを実行して、ワークステーションソフトウェアをクライアントコンピューターにインストールします。

>[!NOTE]
DWBセットアップウィザードでは、DWBクライアントワークステーションのインストール手順を説明し、必要なフォルダーに配置するInsight.cfgファイルと`<PrimaryUser>`.pemファイルを探します。 Insight.cfgファイルは、インストールされたクライアントワークステーションのInsight.exeファイルと共に存在します。 `<PrimaryUser>`.pemファイルは、 trust_ca_cert.pemファイルと共にCertificatesフォルダーに存在します。 DWBが機能するには、すべての証明書ファイルと設定ファイルが存在する必要があります。

詳しくは、[DWBセットアップウィザード](https://experienceleague.adobe.com/docs/data-workbench/using/install/workstation-setup/install-setup.html)を参照してください。

## DWBサーバーへの接続 {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

管理対象サーバーは、Adobeカスタマーケアから受け取り、クライアントワークステーションに存在するInsight.cfgファイルで識別されます。 AdobeTechOpsはサーバーを設定し、Adobeカスタマーケアは、これらの管理対象サーバーおよびプロファイルへの参照をInsight.cfgファイルに追加してから送信します。 （DWBセットアップウィザードのドキュメントの手順12の「サーバーへの接続を設定」が完了します）。

>[!NOTE]
DWBクライアントワークステーションのワークステーション設定ワークスペースで、接続されたサーバーとプロファイルを確認できます。

**Adobe Managed Services**

・AdobeのTechOpsは、ネットワーク、データ・センター、サーバ、ストレージなどのインフラストラクチャを管理します。 インフラストラクチャの監視とアラートへの対応は、TechOpsアクションが必要なアラートに対して24時間365日実施されます。 その他のアラートの場合、TechOpsはAdobeカスタマーケアに連絡して調整を依頼します。

・AdobeTechOpsは、管理対象サーバのメンテナンスとファームウェアの更新を行います。 ダウンタイムを引き起こすメンテナンスの場合、少なくとも2週間前にカスタマーケアからメンテナンスウィンドウの通知を受け取ります。 AdobeのTechOpsは、可能な限り迅速に即時のニーズに対応します。 通知は緊急度に応じて異なり、スケジュールがわかれば解決されます。

・AdobeのTechOpsは、データを自動的に管理するためのスケジュールされたタスクを設定します。 分析フィードデータは、毎晩21:00レポートスイート時間に開始され、処理および変換のためにDWBに移動されます。

・AdobeのTechOpsは、必要に応じて、データのバックアップ、FTPアカウント、データのアーカイブ、データ転送など、他のAdobe Managed Servicesを処理します。

・AdobeのTechOpsは、リセットされ、毎月再処理される3か月のローリングデータを含むように主な実稼動クラスタを設定します。 検索（Geography、DeviceAtlas、標準分類）の更新も、再処理タスクの一環としておこなわれます。 デフォルトでは、タスクは毎月最初の金曜日に実行されます。 必要に応じて、カスタマーケアがスケジュールを変更できます。

詳しくは、[Adobeカスタマーケア](https://helpx.adobe.com/support/programs/enterprise-support-terms.html)にお問い合わせください。
