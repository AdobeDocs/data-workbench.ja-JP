---
description: Report Portal を開き、自分のプロファイルのレポートが正常に表示されるようにする手順です。
title: Report Portal のテスト
uuid: eee0df5e-78e0-49b2-853c-40f1b332328b
exl-id: 197ff815-9234-4dce-b30f-b9cacf259634
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 6%

---

# Report Portal のテスト{#test-the-report-portal}

{{eol}}

Report Portal を開き、自分のプロファイルのレポートが正常に表示されるようにする手順です。

>[!NOTE]
>
>次にログインすることはできません： [!DNL Report Portal] レポートが Output フォルダーに表示されるまで。

1. Web ブラウザーで、 [!DNL Report Portal] 次の URI 形式を使用します。

   https://*ServerAddress*/*PortalName*

   例：[!DNL https://localhost/VisualReportPortal]

1. If [!DNL Report Portal] ログイン資格情報の入力を求め、アカウント名とパスワードを入力します（例：アカウント名は「test」、パスワードは「user」、デフォルトアカウントは「user」）。
1. 次の場合に [!DNL Report Portal] が表示され、次の点を確認します。

   * ポータルには、output フォルダー内の各レポートセットのタブが含まれます。
   * 各タブには、レポートセットの概要レポートが表示されます。
   * 各タブのメニューには、レポートセットの個々のサブフォルダ（存在する場合）が表示され、それらのフォルダの内容が表示されます。
