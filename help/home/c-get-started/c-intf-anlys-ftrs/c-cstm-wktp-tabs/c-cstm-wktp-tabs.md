---
description: ワークトップのタブまたはサブタブはそれぞれ、ダッシュボード、アクティビティ、獲得など特定のタイプの情報に対応しています。
title: ワークトップタブのカスタマイズ
uuid: f1f557c8-f4cb-4789-8162-39cc7c52c943
exl-id: 529c6d8d-fc42-4c2b-a111-b8eea4665d8b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 42%

---

# ワークトップタブのカスタマイズ{#customize-a-worktop-tab}

ワークトップのタブまたはサブタブはそれぞれ、ダッシュボード、アクティビティ、獲得など特定のタイプの情報に対応しています。

例えば、「[!DNL Acquisition]（獲得）」タブには、参照ドメイン、検索エンジン、キャンペーンに関するデータを提供するワークスペースを含めることができます。

[!DNL Worktop]に表示される各タブは、Data Workbenchインストールディレクトリ内の&#x200B;*working profile name*\Workspacesフォルダー内のフォルダーに対応します。 [!DNL Worktop]内のタブの順序は、同じフォルダー内の[!DNL order.txt]ファイルで制御します。 例えば、WorkspacesフォルダーにAcquisitionサブフォルダーがあり、[!DNL order.txt]ファイルの最初のエントリとしてAcquisitionを追加した場合、[!DNL Acquisition]は[!DNL Worktop]の最初のタブになり、そのサブフォルダー内のすべてが[!DNL Acquisition]タブに表示されます。

>[!NOTE]
>
>[!DNL order.txt]ファイルを使用してワークスペースウィンドウメニューをカスタマイズする方法については、[メニューのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/c-ctm-menus.md#concept-93d4c09cb7f34cd293b7b64fba1cf894)を参照してください。
