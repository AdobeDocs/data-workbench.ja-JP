---
description: ワークトップまたはテキストエディターを使用して既存のReport.cfgファイルを編集する手順です。
title: 既存の Report.cfg ファイルの編集
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# 既存の Report.cfg ファイルの編集{#editing-existing-report-cfg-files}

ワークトップまたはテキストエディターを使用して既存のReport.cfgファイルを編集する手順です。

>[!NOTE]
>
>* [!DNL Report.cfg]ファイルを編集するには、オンラインで作業する必要があります。 オンラインで作業するには、[!DNL Worktop]からタイトルバーを右クリックし、**[!UICONTROL Work Online]**&#x200B;をクリックします。
   >
   >
* [!DNL Report.cfg]ファイルの&#x200B;**[!UICONTROL Allow Report Regeneration]**&#x200B;パラメーターが[!DNL True]に設定されている場合、そのファイルに変更を加えてサーバーに保存すると、[!DNL Report]は自動的にそのセット内のレポートを再生成します。 レポートは再生成されますが、電子メールでは再送信されません。 その手順については、[電子メールでのレポートの再送信](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607)を参照してください。

>



既存の[!DNL Report.cfg]は、[!DNL Worktop]またはテキストエディターを使用して編集できます。

[!DNL Worktop]の[!DNL Reports]タブを使用して[!DNL Report.cfg]ファイルを編集すると、ファイル内に既に存在するパラメーター、ベクトル、ベクトル項目のみを編集できます。 ファイルにパラメーターまたはベクトルを追加する必要がある場合は、メモ帳などのテキストエディターを使用して編集する必要があります。

* [ワークトップを使用して既存のReport.cfgを編集するには](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [テキストエディターを使用して既存のReport.cfgを編集するには](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## ワークトップ{#section-7bce3bca006149c79be7678430f21945}を使用して既存のReport.cfgを編集するには

>[!NOTE]
>
>[!DNL Worktop]の[!DNL Report.cfg]を編集するには、オンラインで作業する必要があります。

1. Data Workbenchの「[!DNL Reports]」タブで、設定するレポートセットのサブフォルダー（タブまたはドロップダウンサブディレクトリ）を選択します。
1. 「**[!UICONTROL Report.cfg]**」をクリックします。このレポートセットの[!DNL Report.cfg]のパラメーターが表示されます。

1. 必要に応じて、設定パラメーターを編集します。 これらのパラメーターについて詳しくは、[Report.cfgパラメーター](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)を参照してください。
1. パラメーターの上部の&#x200B;**[!UICONTROL Report.cfg (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save to]***&lt;**[!UICONTROL server location]**>*をクリックして、ファイルを保存します。

## テキストエディター{#section-06f3d2a8d7f34bc2841180caf10a1eb7}を使用して既存のReport.cfgを編集するには

1. ワークスペース内で右クリックし、**[!UICONTROL Admin]**/**[!UICONTROL Profile]**/**[!UICONTROL Reports Manager]**&#x200B;をクリックして、[!DNL Reports Manager]を開きます。

1. レポートセットのフォルダをクリックします。
1. このレポートセットの[!DNL Report.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

1. [!DNL User]列で、このレポートセットの[!DNL Report.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Notepad]**&#x200B;をクリックします。 [!DNL Report.cfg]ファイルが開きます。

   [レポートセットの設定](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)に示すサンプル[!DNL Report.cfg]には、デフォルトで[!DNL Report.cfg]ファイルに含まれているパラメーターのみが含まれています。 次の例には、[!DNL Report.cfg]ファイルに使用できるすべてのパラメーターが含まれており、このパラメーターはパラメーターエントリのモデルとして使用できます。

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. 必要に応じて、設定パラメーターを編集します。 これらのパラメーターについて詳しくは、[Report.cfgパラメーター](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)を参照してください。
1. ファイルを保存して閉じます。
1. [!DNL Reports Manager]で、[!DNL Report.cfg]ファイルの[!DNL User]列のチェックマークを右クリックし、**[!UICONTROL Save to]***&lt;**[!UICONTROL profile name]**>*を選択します。
