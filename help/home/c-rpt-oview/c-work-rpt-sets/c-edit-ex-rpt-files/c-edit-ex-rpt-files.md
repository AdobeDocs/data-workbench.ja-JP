---
description: ワークトップまたはテキストエディターを使用して既存のReport.cfgファイルを編集する手順です。
solution: Analytics
title: 既存のReport.cfgファイルの編集
topic: Data workbench
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 既存のReport.cfgファイルの編集{#editing-existing-report-cfg-files}

ワークトップまたはテキストエディターを使用して既存のReport.cfgファイルを編集する手順です。

>[!NOTE]
>
>* ファイルを編集するには、オンラインで作業する必要が [!DNL Report.cfg] あります。 オンラインで作業するには、から、 [!DNL Worktop]タイトルバーを右クリックし、をクリックしま **[!UICONTROL Work Online]**&#x200B;す。
   >
   >
* ファイル内 **[!UICONTROL Allow Report Regeneration]** のパラメー [!DNL Report.cfg] タがに設定され [!DNL True]ている場合、そのファイルに変更を加え、そのファイルをサーバーに保存すると、そのセット内のレポートが自 [!DNL Report] 動的に再生成されます。 レポートは再生成されますが、電子メールでのレポートの再送信は行われません。 その手順については、「電子メールでのレポ [ートの再送信」を参照してください](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607)。
>



既存のを編集するには、を使用す [!DNL Report.cfg] るか、テキ [!DNL Worktop] ストエディターを使用します。

のタブを使 [!DNL Report.cfg] 用してファ [!DNL Reports] イルを編集す [!DNL Worktop] ると、ファイル内に既に存在するパラメータ、ベクトル、ベクトル項目のみを編集できます。 ファイルにパラメータまたはベクトルを追加する必要がある場合は、メモ帳などのテキストエディターを使用して編集する必要があります。

* [ワークトップを使用して既存のReport.cfgを編集するには](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [テキストエディターを使用して既存のReport.cfgを編集するには](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## ワークトップを使用して既存のReport.cfgを編集するには {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>からを編集するには、オンラインで作業して [!DNL Report.cfg] いる必要がありま [!DNL Worktop]す。

1. data workbenchのタブで、設 [!DNL Reports] 定するレポートセットのサブフォルダー（タブまたはドロップダウンサブディレクトリ）を選択します。
1. クリック **[!UICONTROL Report.cfg]**. このレポートセットの [!DNL Report.cfg] のパラメータが表示されます。

1. 必要に応じて、設定パラメータを編集します。 これらのパラメーターについて詳しくは、 [Report.cfgのパラメーターを参照してください](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. Save the file by right-clicking **[!UICONTROL Report.cfg (modified)]** at the top of the parameters and clicking **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## テキストエディターを使用して既存のReport.cfgを編集するには {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. ワークスペ [!DNL Reports Manager] ース内で右クリックし、//をクリ **[!UICONTROL Admin]** ックして、を **[!UICONTROL Profile]** 開きま **[!UICONTROL Reports Manager]**&#x200B;す。

1. レポートセットのフォルダをクリックします。
1. このレポートセットの横のチェックマークを右ク [!DNL Report.cfg] リックし、をクリックしま **[!UICONTROL Make Local]**&#x200B;す。

1. 列で、こ [!DNL User] のレポートセットの横のチェックマークを右ク [!DNL Report.cfg] リックし、/をクリック **[!UICONTROL Open]** します **[!UICONTROL in Notepad]**。 The [!DNL Report.cfg] file opens.

   「レポートセ [!DNL Report.cfg] ットの設 [定」に示すサンプルには](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) 、デフォルトでファイルに含まれるパラメ [!DNL Report.cfg] ータのみが含まれます。 次の例には、パラメータエントリのモデルとして使用でき [!DNL Report.cfg] る、ファイルで使用可能なすべてのパラメータが含まれています。

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

1. 必要に応じて、設定パラメータを編集します。 これらのパラメーターについて詳しくは、 [Report.cfgのパラメーターを参照してください](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. ファイルを保存して閉じます。
1. で、フ [!DNL Reports Manager]ァイルの列のチェックマークを右ク [!DNL User] リックし [!DNL Report.cfg] て、 **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>を選択します&#x200B;*。

