---
description: ユーザーの Insight.cfg ファイル内の Unlock パラメーターは、ロックされているワークスペースを一時的にロック解除して編集する権限をユーザーが持っているかどうかを指定します。
title: Unlock パラメーターの設定
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 73%

---

# Unlock パラメーターの設定{#set-the-unlock-parameter}

ユーザーの Insight.cfg ファイル内の Unlock パラメーターは、ロックされているワークスペースを一時的にロック解除して編集する権限をユーザーが持っているかどうかを指定します。

Unlockパラメーターが既にユーザーの[!DNL Insight.cfg]ファイルに存在する場合は、Data Workbenchを使用してパラメーターを編集できます。 Unlock パラメーターがユーザーの [!DNL Insight.cfg] ファイルにまだ存在していない場合、メモ帳などのテキストエディターを使用してファイルに追加する必要があります。

**Insight.cfg ファイルに存在している [!DNL Unlock] パラメーターを設定するには**

1. ワークスペースで、**[!UICONTROL Admin]**/**[!UICONTROL Client Configuration]**&#x200B;を右クリックします。 [!DNL Insight.cfg]ファイルが開きます。
1. Unlock パラメーターに対して、true または false を入力します。true に設定すると、ユーザーはロックされた任意のワークスペースのロックを一時的に解除できますが、false に設定すると、ユーザーはロックを解除できません。
1. 設定の変更を保存するには、ウィンドウ上部の&#x200B;**[!UICONTROL Insight.cfg (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save as Insight.cfg]**&#x200B;をクリックします。

**Unlock パラメーターを Insight.cfg ファイルに追加するには**

1. Data Workbenchのインストールディレクトリに移動し、メモ帳などのテキストエディターを使用して[!DNL Insight.cfg]ファイルを開きます。
1. ファイルの最後に、次の例のように Unlock パラメーターを追加します。

[!DNL Unlock = bool: false]

1. 値を true か false に設定します。true に設定すると、ユーザーはロックされた任意のワークスペースのロックを一時的に解除できますが、false に設定すると、ユーザーはロックを解除できません。
1. ファイルを保存して閉じます。
