---
description: Data Workbenchは、特定のユーザーのみが特定のワークスペースを変更できるように設定できます。
title: ロックされているワークスペースの設定
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 75%

---

# ロックされているワークスペースの設定{#configure-a-locked-workspace}

{{eol}}

Data Workbenchは、特定のユーザーのみが特定のワークスペースを変更できるように設定できます。

ワークスペースがロックされていても、ユーザーは大部分のビジュアライゼーション内に選択範囲を作成したり、テーブルのデータを並べ替えたりできますが、それ以外のワークスペースの変更はできません。この機能は、ユーザーがワークスペースに意図しない変更を行うことを防ぎます。

次の 3 つの要素が連携してワークスペースのロックを制御します。

* **または *workspace name*.lock ファイル：**[!DNL folder.lock]folder.lock ファイルは、特定のフォルダー内のワークスペースをロックするかどうかを指定します。[!DNL name.lock]workspace   ファイルは、特定のワークスペースをロックするかどうかを指定します。

* **ユーザーの [!DNL Insight.cfg] ファイル内の Unlock パラメーター：**&#x200B;このパラメーターは、ロックされているワークスペースをユーザーが一時的にロック解除できるかどうかを指定します。
* **一時的にロック解除メニューオプション：**&#x200B;ユーザーの [!DNL Insight.cfg] 内の Unlock パラメーターが true に設定されている場合、ロックされている各ワークスペースのタイトルバーメニューにこのオプションが自動的に表示されて、ユーザーにロック解除手段を提示します。

[!DNL folder.lock] ファイルと [!DNL name.lock]workspace   ファイルについては、以下の節を参照してください。Unlock パラメータの設定については、 [Unlock パラメータの設定](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). 詳しくは、 [!DNL Temporarily Unlock menu] オプション： [ワークスペースのロック解除](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
