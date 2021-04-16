---
description: レポートポータルを開き、プロファイルのレポートを正しく表示できるようにする手順です。
title: Report Portal のテスト
uuid: eee0df5e-78e0-49b2-853c-40f1b332328b
exl-id: 197ff815-9234-4dce-b30f-b9cacf259634
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 6%

---

# Report Portal のテスト{#test-the-report-portal}

レポートポータルを開き、プロファイルのレポートを正しく表示できるようにする手順です。

>[!NOTE]
>
>[!DNL Report Portal]にログインするには、レポートがOutputフォルダーに表示される必要があります。

1. Webブラウザーで、次のURI形式を使用して[!DNL Report Portal]を開きます。

   http://*ServerAddress*/*PortalName*

   例：[!DNL http://localhost/VisualReportPortal]

1. [!DNL Report Portal]からログイン資格情報の入力を求められた場合は、アカウント名とパスワードを入力します（例えば、デフォルトのアカウントは「account &quot;test&quot;」、パスワードは「user&quot;」）。
1. [!DNL Report Portal]が表示されたら、次のことを確認します。

   * ポータルには、出力フォルダー内の各レポートセット用のタブが含まれます。
   * 各タブには、レポートセットのサマリレポートが表示されます。
   * 各タブのメニューには、レポートセットの個々のサブリスト（存在する場合）が表示され、それらのフォルダの内容が表示されます。
