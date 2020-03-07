---
description: Data Workbench のワークステーション（クライアント）をインストールするための要件および推奨事項です。
solution: Analytics
title: ワークステーションの要件
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Workstation requirements{#workstation-requirements}

Data Workbench のワークステーション（クライアント）をインストールするための要件および推奨事項です。

See [Server System Requirements](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) for additional Data Workbench system requirements.

>[!IMPORTANT]
>
>サーバ、レポートサーバ、クライアントの各コンポーネントは、64ビットWindowsオペレーティングシステムで実行するようにアップグレードされます。

**始める前に**

Data Workbench ワークステーション（クライアント）をインストールする前に、必ず以下の作業を完了してください。

* 以下の実行ファイルについて、Windows 2012 Server の **MS System Center Endpoint Protection** の&#x200B;***除外プロセス***&#x200B;を&#x200B;*追加*&#x200B;します。

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   これにより、連動するこれらの実行ファイルに「ホワイトリスト」権限を許可します。

* **分析データをエクスポートするには、Microsoft Excel をインストールします。** ワークスペースからデータをMicrosoft Excel(または [!DNL .xls][!DNL .xlsx])ファイルとしてエクスポートするには、Data WorkbenchをインストールしたコンピューターにExcelがインストールされ、登録されている必要があります。 Excelが登録されておらず、Data Workbenchが初めてアクセスを試みた場合は、登録ダイアログボックスが表示されます。 登録されているかどうかが不明な場合は、Excel を手動で起動し、登録ダイアログボックスが表示されれば登録プロセスを完了します。

   >[!NOTE]
   >
   >Data Workbench 6.4 のリリースに伴って、Excel 2007 のサポートが終了しました。また、Data Workbench は 64 ビットアーキテクチャの Microsoft Windows 上でのみ動作するので、64 ビット版の Microsoft Excel もインストールすることをお勧めします。

* **拡大縮小したワークスペースを PDF に出力するには、Adobe[!DNL Acrobat]をインストールします。** 縮小されたワークスペースをAdobe PDF形式で印刷するには、Data WorkbenchをインストールしたコンピューターにAdobeがインストールされている必要が [!DNL Acrobat] あります。

* **ワークスペースを印刷するには、プリンターにアクセスできるようにします。** Data Workbenchからワークスペースを印刷するには、Data Workbenchをインストールしたコンピューターがプリンターにアクセスできる必要があります。 Data Workbenchは、ワークスペースをカラーまたはモノクロのプリンターで印刷でき、ポストスクリプトやその他の高度なプリンター機能は不要です。 適切な結果を得るために、アドビではワークスペースをカラーで印刷することを推奨しています。
* **セキュリティ対策を実施します。** Data Workbenchコンピューターに関する会社の通常のエンタープライズセキュリティポリシーに従う必要があります。 Data Workbenchが主な目的を果たすために必要なのは、サーバー（ポート80と443を経由）と、データを収集する任意のサーバーに接続する機能のみです。 Data Workbenchハードウェアは、Data Workbenchソフトウェアを保守し、Data Workbench用に10 GB以上の記憶領域を割り当てる限り、その他の目的に使用できます。
* ビジュアライゼーションを正確にレンダリングするため、Data Workbench をインストールするコンピューターには適切な&#x200B;**グラフィックアダプター**&#x200B;がインストールされている必要があります（下記のグラフィックアダプターの要件を参照してください）。

**Data Workbench クライアントの要件** 

**オペレーティングシステム**

* Microsoft Windows 7 64-bit
* Microsoft Windows 8.1 64-bit
* Microsoft Windows 10 64ビット

>[!NOTE]
>
>Windows XPは、Data Workbench 6.1以降のバージョンではサポートされていません。

**解像度**

* 必須：1024 x 768(XGA)
* 推奨：1920 x 1200(WUXGA)

**グラフィックアダプター**

* 必須：OpenGL 3.2をサポートするOpenGLハードウェアアクセラレーション
* 推奨：専用のビデオアダプタ（NVIDIAやATIアダプタなど）

**プロセッサー**

* 必須：1.2 GHz以上のIntelまたはAMD
* 推奨：Core 2 Duoクラス

**RAM**

* 必須：2 GB
* 推奨：4 GB

**接続**

* 必須：DPUへの512 Kbpsリンク
* 推奨：DPUへの2 Mbps以上のリンク

**ファイルシステム**

NTFS

**ディスクストレージ**

ハードディスクドライブの 10 GB 以上の空きスペース

**印刷**

ワークスペースとレポートを印刷するためのプリンター（カラーまたはグレースケールのプリンター）

**その他**

* 専用マウス
* 低グレアの作業環境
* つや消し面のモニター
