---
description: ワークトップまたはテキストエディターを使用して既存の Report.cfg ファイルを編集する手順です。
title: 既存の Report.cfg ファイルの編集
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# 既存の Report.cfg ファイルの編集{#editing-existing-report-cfg-files}

{{eol}}

ワークトップまたはテキストエディターを使用して既存の Report.cfg ファイルを編集する手順です。

>[!NOTE]
>
>* 編集するには、オンラインで作業する必要があります [!DNL Report.cfg] ファイル。 オンラインで作業するには、 [!DNL Worktop]をクリックし、タイトルバーを右クリックして、 **[!UICONTROL Work Online]**.
>
>* この **[!UICONTROL Allow Report Regeneration]** パラメーター [!DNL Report.cfg] ファイルが [!DNL True]をクリックし、そのファイルに変更を加えて、そのファイルをサーバに保存し直す場合、 [!DNL Report] は、そのセット内のレポートを自動的に再生成します。 レポートが再生成されますが、電子メールでレポートを再送信することはありません。 その手順については、 [メールによるレポートの再送信](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).
>


既存の [!DNL Report.cfg] から [!DNL Worktop] またはテキストエディターを使用して読み込むこともできます。

の編集 [!DNL Report.cfg] ファイルを [!DNL Reports] タブ [!DNL Worktop] では、ファイルに既に存在するパラメータ、ベクトル、およびベクトル項目のみを編集できます。 ファイルにパラメーターまたはベクトルを追加する必要がある場合は、メモ帳などのテキストエディターを使用して編集する必要があります。

* [ワークトップを使用して既存の Report.cfg を編集するには](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [テキストエディターを使用して既存の Report.cfg を編集するには](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## ワークトップを使用して既存の Report.cfg を編集するには {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>を編集するには、オンラインで作業する必要があります [!DNL Report.cfg] から [!DNL Worktop].

1. Data Workbench で、 [!DNL Reports] 」タブで、設定するレポートセットのサブフォルダ（タブまたはドロップダウンサブディレクトリ）を選択します。
1. 「**[!UICONTROL Report.cfg]**」をクリックします。のパラメーター [!DNL Report.cfg] このレポートセットが表示されます。

1. 必要に応じて設定パラメーターを編集します。 これらのパラメーターについて詳しくは、 [Report.cfg のパラメーター](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. 右クリックしてファイルを保存 **[!UICONTROL Report.cfg (modified)]** をクリックし、 **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## テキストエディターを使用して既存の Report.cfg を編集するには {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. を開きます。 [!DNL Reports Manager] ワークスペース内で右クリックし、 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. レポートセットのフォルダーをクリックします。
1. の横のチェックマークを右クリックします。 [!DNL Report.cfg] をクリックします。 **[!UICONTROL Make Local]**.

1. 内 [!DNL User] 列で、横のチェックマークを右クリックします。 [!DNL Report.cfg] をクリックします。 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. この [!DNL Report.cfg] ファイルが開きます。

   サンプル [!DNL Report.cfg] 次に示す [レポートセットの設定](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) には、 [!DNL Report.cfg] ファイルに書き込まれます。 次の例では、 [!DNL Report.cfg] パラメータエントリのモデルとして使用できるファイル：

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

1. 必要に応じて設定パラメーターを編集します。 これらのパラメーターについて詳しくは、 [Report.cfg のパラメーター](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. ファイルを保存して閉じます。
1. 内 [!DNL Reports Manager]を選択し、 [!DNL User] 列 [!DNL Report.cfg] ファイルと選択 **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
