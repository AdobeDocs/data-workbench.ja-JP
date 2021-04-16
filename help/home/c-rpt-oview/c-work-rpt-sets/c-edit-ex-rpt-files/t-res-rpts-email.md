---
description: 電子メールでレポートを再送信する手順です。
title: 電子メールによるレポートの再送信
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# 電子メールによるレポートの再送信{#resending-reports-by-email}

電子メールでレポートを再送信する手順です。

[!DNL Report.cfg]ファイルの&#x200B;**[!UICONTROL Allow Report Regeneration]**&#x200B;パラメーターが[!DNL True]に設定されている場合、[!DNL Report.cfg]ファイルに変更を加え、そのファイルをサーバーに保存すると、Report Serverはそのセット内のレポートを自動的に再生成します。 電子メールでのレポートの再送信は行いません。

1. [[!DNL Reports]]タブで、再送信するレポートセットのサブフォルダ（タブまたはドロップダウンサブディレクトリ）を選択します。
1. 「**[!UICONTROL Report.cfg]**」をクリックします。このレポートセットの[!DNL Report.cfg]のパラメーターが表示されます。
1. **[!UICONTROL Start Date]**&#x200B;パラメーターを、レポートを再送する将来の時刻に変更します。
1. パラメーターの上部の&#x200B;**[!UICONTROL Report.cfg (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save to]***&lt;**[!UICONTROL server location]**>*をクリックして、ファイルを保存します。
このセット内のレポートは再生成され、指定した受信者に電子メールで送信されます。
