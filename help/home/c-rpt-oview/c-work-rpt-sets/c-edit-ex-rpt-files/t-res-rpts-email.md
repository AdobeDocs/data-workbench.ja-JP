---
description: 電子メールでレポートを再送信する手順です。
title: 電子メールによるレポートの再送信
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# 電子メールによるレポートの再送信{#resending-reports-by-email}

{{eol}}

電子メールでレポートを再送信する手順です。

この **[!UICONTROL Allow Report Regeneration]** パラメーター [!DNL Report.cfg] ファイルが [!DNL True]に変更を加えた場合、 [!DNL Report.cfg] ファイルを作成し、そのファイルをサーバに保存すると、レポートサーバはそのセット内のレポートを自動的に再生成します。 電子メールでレポートを再送信するわけではありません。

1. の [!DNL Reports] 」タブで、再送信するレポートセットのサブフォルダ（タブまたはドロップダウンサブディレクトリ）を選択します。
1. 「**[!UICONTROL Report.cfg]**」をクリックします。のパラメーター [!DNL Report.cfg] このレポートセットが表示されます。
1. を **[!UICONTROL Start Date]** パラメーターを設定します。
1. 右クリックしてファイルを保存 **[!UICONTROL Report.cfg (modified)]** をクリックし、 **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
このセットのレポートは再生成され、指定された受信者に電子メールで再送信されます。
