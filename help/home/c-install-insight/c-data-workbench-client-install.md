---
description: Data Workbench のワークステーション（クライアント）をインストールするための要件および推奨事項です。
title: ワークステーションの要件
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 46%

---

# ワークステーションの要件{#workstation-requirements}

Data Workbench のワークステーション（クライアント）をインストールするための要件および推奨事項です。

追加のData Workbenchシステム要件については、[サーバーシステムの要件](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html)を参照してください。

>[!IMPORTANT]
>
>アップグレード後のサーバー、レポートサーバー、クライアントコンポーネントは、64ビットWindowsオペレーティングシステム上で動作します。

**始める前に**

Data Workbench ワークステーション（クライアント）をインストールする前に、必ず以下の作業を完了してください。

* 以下の実行ファイルについて、Windows 2012 Server の **MS System Center Endpoint Protection** の&#x200B;***除外プロセス***&#x200B;を&#x200B;*追加*&#x200B;します。

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   これにより、これらのインターフェイスする実行可能ファイルの許可リスト権限が有効になります。

* **分析データをエクスポートするには、Microsoft Excel をインストールします。** ワークスペースからデータをMicrosoft Excel( [!DNL .xls] または [!DNL .xlsx])ファイルとしてエクスポートするには、Data WorkbenchをインストールしたコンピューターにExcelがインストールされ、登録されている必要があります。Excelが登録されていない状態で、Data Workbenchが初めてアクセスを試みた場合は、登録ダイアログボックスが表示されます。 登録されているかどうかが不明な場合は、Excel を手動で起動し、登録ダイアログボックスが表示されれば登録プロセスを完了します。

   >[!NOTE]
   >
   >Data Workbench 6.4 のリリースに伴って、Excel 2007 のサポートが終了しました。また、Data Workbench は 64 ビットアーキテクチャの Microsoft Windows 上でのみ動作するので、64 ビット版の Microsoft Excel もインストールすることをお勧めします。

* **拡大縮小したワークスペースを PDF に出力するには、Adobe [!DNL Acrobat] をインストールします。** 拡大縮小したワークスペースをAdobe PDF形式で印刷するには、Data WorkbenchをインストールしたコンピューターにAdobeが [!DNL Acrobat] インストールされている必要があります。

* **ワークスペースを印刷するには、プリンターにアクセスできるようにします。** Data Workbenchからワークスペースを印刷するには、Data Workbenchをインストールしたコンピューターがプリンターにアクセスできる必要があります。Data Workbenchは、ワークスペースをカラーまたはモノクロで印刷でき、ポストスクリプトやその他の高度なプリンター機能は必要ありません。 適切な結果を得るために、アドビではワークスペースをカラーで印刷することを推奨しています。
* **セキュリティ対策を実施します。** Data Workbenchコンピューターに対する会社の通常のエンタープライズセキュリティポリシーに従う必要があります。Data Workbenchが主な目的を果たすために必要とするのは、サーバへの接続（ポート80と443を介する）と、データを収集する任意のサーバへの接続のみです。 Data Workbenchハードウェアは、Data Workbenchソフトウェアを保守し、Data Workbenchに10 GB以上のストレージ領域を割り当てる限り、他の目的に使用できます。
* ビジュアライゼーションを正確にレンダリングするため、Data Workbench をインストールするコンピューターには適切な&#x200B;**グラフィックアダプター**&#x200B;がインストールされている必要があります（下記のグラフィックアダプターの要件を参照してください）。

**Data Workbench クライアントの要件** 

**オペレーティングシステム**

* Microsoft Windows 7 64-bit
* Microsoft Windows 8.1 64-bit
* Microsoft Windows 10 64ビット

>[!NOTE]
>
>Windows XPは、Data Workbench6.1以降のバージョンではサポートされていません。

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
