---
description: Data Workbench v6.4 にアップグレードするには、この手順に従います。
title: 6.3 から 6.4 へのアップグレード
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 2930bd3ae06e700e75144221fc993efdd6bd1e85
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 74%

---


# 6.3 から 6.4 へのアップグレード{#upgrading-to}

Data Workbench v6.4 にアップグレードするには、この手順に従います。

## アップグレード要件と推奨事項 {#section-8704a9ac358246cd81233dd0982d534f}

Data Workbench 6.4 にアップグレードする際は、以下の要件および推奨事項に従ってください。

>[!IMPORTANT]
>
>以前のインストールからファイルを移動するのではなく、新たにインストールしたデフォルトの設定ファイルを使用してカスタマイズすることをお勧めします。ただし、次の例外があります。

* 以下の実行ファイルについて、Windows 2012 Server の **MS System Center Endpoint Protection** の&#x200B;***除外プロセス***&#x200B;を&#x200B;*追加*&#x200B;します。

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   これにより、これらのインターフェイスする実行可能ファイルに対して許可リスト権限が有効になります。

* **サーバー上の&#x200B;*Trust_ca_cert.pem*証明書を更新します**。
* **アトリビューションプロファイルの再編成**。

   * *Attribution* フォルダーの名前が ***Attribution - Premiumに変更されました*** ( *プロファイル*\*Attribution - Premium*にあるデフォルトのインストールにあります)。

   * *Premium* プロファイルは削除され、ワークスペースは新しい ***Attribution - Premium*** フォルダーに移動されました。

* ***Attribution-Premium*設定を更新します**。 デフォルトの *Adobe SC* プロファイルをオーバーライドするパラメーター設定でプロファイルをカスタマイズした場合は、以下の設定ファイルのカスタムフィールドを更新する必要があります。

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* この再編成によって、古い *Attribution* フォルダーと *Premium* フォルダーをサーバーのインストール場所から削除する必要があります。

   **以下の設定を**

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 6 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
   
       4 = string: Attribution\\ 
       5 = string: Premium\\
   ```

   次のように変更します。

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\
       4 = string: Attribution - Premium\\
   ```

* **カスタム Meta.cfg ファイルを更新します**（必要な場合）。

   The **[!DNL Meta.cfg]** files in **[!DNL Base\Context and AdobeSC\Context]** folders have been updated in this release.

   インストール時に **meta.cfg** ファイルをオーバーライドする場合は、これらのパラメーターと、適切に入力された&#x200B;**メタデータのベクター**&#x200B;でプロファイルのコピーを更新する必要があります。

   ```
   94 = meta: 
     path = string: SegmentExport:CRS Configuration/CRS Attributes 
     acceptable children = vector: 1 items 
       0 = Template: 
         name = string: CRS Attributes 
         value = CRSAttributeConfiguration: 
           Attribute Name = string: 
           Attribute Type(int,string) = string: 
           Field Name = string: 
   
   95 = meta: 
     path = string: SegmentExportQuery:CRS Configuration/Report Suite 
     acceptable children = vector: 1 items 
       0 = Template 
         name = string: Add Report Suite 
         value = string:
   ```

* Windows 2012 Server 上で Microsoft Excel レポートを生成できるように **Report Server の権限**&#x200B;を設定します。

   1. Set permission of the root folder (**[!DNL E:\ReportServer\]**) to *Everyone = full control*.

   1. 適切な権限で以下のフォルダーを作成します。

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Windows Server 2012でReport Serverを実行する場合は、Windows Server 2012 R2をインストールする必要があります。

   1. これらのフォルダーの所有者として「SYSTEM」を割り当てます。

* **フォントを Report Server に追加します。** **[!DNL ReportServer.cfg]**ファイルに、（すべての言語で）次のフォントを追加します。

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Microsoft Excelのバージョンを更新します**（必要な場合）。

   Data Workbench 6.4 のリリースに伴って、Excel 2007 のサポートが終了しました。また、Data Workbench は 64 ビットアーキテクチャの Microsoft Windows 上でのみ動作するので、64 ビット版の Microsoft Excel もインストールすることをお勧めします。

* ワークステーション（クライアント）のインストールに必要な **64 ビットアーキテクチャ**。
* **ワークステーションセットアップウィザードを実行します**。

   ***InsightSetup.exe*** をダウンロードして起動し、セットアップ手順に従って、新しいバージョンのワークステーション（クライアント）をインストールします。デフォルトでは、ファイルは以下の新しい場所にインストールされます。

   プログラムファイルはデフォルトで次の場所に保存されるようになりました。

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   データファイル（プロファイル、証明書、トレースログ、ユーザーファイルなど）はデフォルトで次の場所に保存されるようになりました。

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **フォントをワークステーションに追加します**。

   **[!DNL Insight.cfg]** ファイル内で、以下のフォントを（すべての言語に対して）追加します。

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

