---
description: Data Workbench のワークステーション（クライアント）をインストールするための要件および推奨事項です。
title: ワークステーションの要件
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 46%

---

# ワークステーションの要件{#workstation-requirements}

{{eol}}

Data Workbench のワークステーション（クライアント）をインストールするための要件および推奨事項です。

詳しくは、 [サーバーの必要システム構成](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/c-msr-server.html?lang=en) を参照してください。

>[!IMPORTANT]
>
>サーバー、レポートサーバー、およびクライアントコンポーネントは、64 ビット Windows オペレーティングシステムで実行するようにアップグレードされます。

**始める前に**

Data Workbench ワークステーション（クライアント）をインストールする前に、必ず以下の作業を完了してください。

* 以下の実行ファイルについて、Windows 2012 Server の **MS System Center Endpoint Protection** の&#x200B;***除外プロセス***&#x200B;を&#x200B;*追加*&#x200B;します。

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   これにより、これら許可リストの相互に作用する実行可能ファイルに対する権限が有効になります。

* **分析データをエクスポートするには、Microsoft Excel をインストールします。** ワークスペースからデータをMicrosoft Excel ( [!DNL .xls] または [!DNL .xlsx]) ファイルを使用する場合は、Excel をインストールし、Data Workbenchを登録しておく必要があります。 Excel が登録されていない状態で、Data Workbenchが初めてアクセスを試みた場合は、登録ダイアログボックスが表示されます。 登録されているかどうかが不明な場合は、Excel を手動で起動し、登録ダイアログボックスが表示されれば登録プロセスを完了します。

   >[!NOTE]
   >
   >Data Workbench 6.4 のリリースに伴って、Excel 2007 のサポートが終了しました。また、Data Workbench は 64 ビットアーキテクチャの Microsoft Windows 上でのみ動作するので、64 ビット版の Microsoft Excel もインストールすることをお勧めします。

* **拡大縮小したワークスペースを PDF に出力するには、Adobe [!DNL Acrobat] をインストールします。** 拡大縮小されたワークスペースをAdobe PDF形式で印刷するには、Data WorkbenchをインストールしたコンピュータにAdobeが必要です [!DNL Acrobat] インストール済み

* **ワークスペースを印刷するには、プリンターにアクセスできるようにします。** ワークスペースをData Workbenchから印刷するには、Data Workbenchをインストールしたコンピュータがプリンタにアクセスできる必要があります。 Data Workbenchは、ワークスペースをカラーまたはモノクロのプリンタに印刷でき、ポストスクリプトやその他の高度なプリンタ機能は必要ありません。 適切な結果を得るために、アドビではワークスペースをカラーで印刷することを推奨しています。
* **セキュリティ対策を実施します。** 企業の通常のエンタープライズセキュリティポリシーに従って、Data Workbench・コンピュータを使用する必要があります。 Data Workbenchが主な目的を果たすには、サーバー（ポート 80 および 443 を介して）と、データを収集する任意のサーバーに接続する機能のみが必要です。 Data Workbench・ソフトウェアを保守し、Data Workbench用に少なくとも 10 GB のストレージ・スペースを割り当てる限り、Data Workbench・ハードウェアをその他の目的に使用できます。
* ビジュアライゼーションを正確にレンダリングするため、Data Workbench をインストールするコンピューターには適切な&#x200B;**グラフィックアダプター**&#x200B;がインストールされている必要があります（下記のグラフィックアダプターの要件を参照してください）。

**Data Workbench クライアントの要件** 

**オペレーティングシステム**

* Microsoft Windows 7 64-bit
* Microsoft Windows 8.1 64-bit
* Microsoft Windows 10 64 ビット

>[!NOTE]
>
>Windows XP は、Data Workbench6.1 以降のバージョンではサポートされていません。

**解像度**

* 必須：1024 x 768 (XGA)
* 推奨：1920 x 1200 (WUXGA)

**グラフィックアダプター**

* 必須：OpenGL 3.2 をサポートする OpenGL ハードウェアアクセラレーション
* 推奨：専用ビデオアダプタ（NVIDIA や ATI アダプタなど）

**プロセッサー**

* 必須：1.2 GHz 以上の Intel または AMD
* 推奨：ICore 2 Duo クラス

**RAM**

* 必須：2 GB
* 推奨：4 GB

**接続**

* 必須：DPU への 512 Kbps リンク
* 推奨：DPU への 2 Mbps 以上のリンク

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
