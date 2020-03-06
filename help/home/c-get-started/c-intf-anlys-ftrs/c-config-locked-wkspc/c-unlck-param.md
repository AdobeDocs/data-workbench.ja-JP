---
description: ユーザーの Insight.cfg ファイル内の Unlock パラメーターは、ロックされているワークスペースを一時的にロック解除して編集する権限をユーザーが持っているかどうかを指定します。
solution: Analytics
title: unlockパラメーターの設定
topic: Data workbench
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Set the unlock parameter{#set-the-unlock-parameter}

ユーザーの Insight.cfg ファイル内の Unlock パラメーターは、ロックされているワークスペースを一時的にロック解除して編集する権限をユーザーが持っているかどうかを指定します。

If the Unlock parameter is already present in the user’s [!DNL Insight.cfg] file, you can edit the parameter using Data Workbench. Unlock パラメーターがユーザーの [!DNL Insight.cfg] ファイルにまだ存在していない場合、メモ帳などのテキストエディターを使用してファイルに追加する必要があります。

**Insight.cfg ファイルに存在している[!DNL Unlock]パラメーターを設定するには**

1. ワークスペース内で右クリックし、/を **[!UICONTROL Admin]** 選択しま **[!UICONTROL Client Configuration]**&#x200B;す。 The [!DNL Insight.cfg] file opens.
1. Unlock パラメーターに対して、true または false を入力します。true に設定すると、ユーザーはロックされた任意のワークスペースのロックを一時的に解除できますが、false に設定すると、ユーザーはロックを解除できません。
1. To save your configuration changes, right-click **[!UICONTROL Insight.cfg (modified)]** at the top of the window and click **[!UICONTROL Save as Insight.cfg]**.

**Unlock パラメーターを Insight.cfg ファイルに追加するには**

1. Navigate to your Data Workbench installation directory and open the [!DNL Insight.cfg] file using a text editor, such as Notepad.
1. ファイルの最後に、次の例のように Unlock パラメーターを追加します。

[!DNL Unlock = bool: false]

1. 値を true か false に設定します。true に設定すると、ユーザーはロックされた任意のワークスペースのロックを一時的に解除できますが、false に設定すると、ユーザーはロックを解除できません。
1. ファイルを保存して閉じます。

