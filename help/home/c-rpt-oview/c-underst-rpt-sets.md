---
description: レポートセットは、Report.cfg設定ファイルで指定された値に基づいてReport Serverが生成するワークスペースの集まりです。
title: レポートセットについて
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
exl-id: 95609a1a-e70c-41e2-ace3-0cb09f77705a
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 4%

---

# レポートセットについて{#understanding-report-sets}

レポートセットは、Report.cfg設定ファイルで指定された値に基づいてReport Serverが生成するワークスペースの集まりです。

[!DNL Insight]インストールフォルダー内の&lt;*working profile name*\Reportsフォルダー内の各サブフォルダーは、作成されたレポートセットを表します。 各レポートセットには、そのサブフォルダー内に独自の[!DNL Report.cfg]設定ファイルがあります。

>[!NOTE]
>
>Data Workbenchーの[!DNL Profile Manager]には、レポートセットが[!DNL Reports]フォルダー内のサブフォルダーとして表示されます。 [!DNL Profile Manager]について詳しくは、『[Data Workbenchユーザーガイド](https://experienceleague.adobe.com/docs/data-workbench/using/home.html#Data_Workbench_Help)』を参照してください。

[!DNL Report.cfg]ファイルでレポートセットの特定の設定を定義することで、どのレポートを受け取るユーザーや形式でレポートを作成し、配信するかなど、レポートのスケジュールを設定できます。
