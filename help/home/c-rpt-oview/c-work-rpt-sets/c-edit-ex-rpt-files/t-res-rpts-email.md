---
description: レポートを電子メールで再送信する手順です。
solution: Analytics
title: 電子メールによるレポートの再送信
topic: Data workbench
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 電子メールによるレポートの再送信{#resending-reports-by-email}

レポートを電子メールで再送信する手順です。

ファイル内 **[!UICONTROL Allow Report Regeneration]** のパラメー [!DNL Report.cfg] タがに設定され [!DNL True][!DNL Report.cfg] ている場合、ファイルに変更を加え、そのファイルをサーバーに保存すると、Report Serverはそのセット内のレポートを自動的に再生成します。 電子メールでのレポートの再送信は行われません。

1. タブで、 [!DNL Reports] 再送信するレポートセットのサブフォルダ（タブまたはドロップダウンサブディレクトリ）を選択します。
1. クリック **[!UICONTROL Report.cfg]**. このレポートセットの [!DNL Report.cfg] のパラメータが表示されます。
1. このパラメ **[!UICONTROL Start Date]** ーターを、レポートを再送する未来の時刻に変更します。
1. Save the file by right-clicking **[!UICONTROL Report.cfg (modified)]** at the top of the parameters and clicking **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
このセット内のレポートは再生成され、指定した受信者に電子メールで送信されます。
