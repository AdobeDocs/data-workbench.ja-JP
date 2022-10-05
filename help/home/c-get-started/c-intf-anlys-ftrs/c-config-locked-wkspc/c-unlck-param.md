---
description: ユーザーの Insight.cfg ファイル内の Unlock パラメーターは、ロックされているワークスペースを一時的にロック解除して編集する権限をユーザーが持っているかどうかを指定します。
title: Unlock パラメーターの設定
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 73%

---

# Unlock パラメーターの設定{#set-the-unlock-parameter}

{{eol}}

ユーザーの Insight.cfg ファイル内の Unlock パラメーターは、ロックされているワークスペースを一時的にロック解除して編集する権限をユーザーが持っているかどうかを指定します。

Unlock パラメーターが既にユーザーの [!DNL Insight.cfg] ファイル内のパラメータを編集する場合は、Data Workbenchを使用します。 Unlock パラメーターがユーザーの [!DNL Insight.cfg] ファイルにまだ存在していない場合、メモ帳などのテキストエディターを使用してファイルに追加する必要があります。

**Insight.cfg ファイルに存在している [!DNL Unlock] パラメーターを設定するには**

1. ワークスペースで、右クリック **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. この [!DNL Insight.cfg] ファイルが開きます。
1. Unlock パラメーターに対して、true または false を入力します。true に設定すると、ユーザーはロックされた任意のワークスペースのロックを一時的に解除できますが、false に設定すると、ユーザーはロックを解除できません。
1. 設定の変更を保存するには、右クリックします。 **[!UICONTROL Insight.cfg (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save as Insight.cfg]**.

**Unlock パラメーターを Insight.cfg ファイルに追加するには**

1. Data Workbenchインストールディレクトリに移動し、 [!DNL Insight.cfg] ファイルを作成します（メモ帳など）。
1. ファイルの最後に、次の例のように Unlock パラメーターを追加します。

[!DNL Unlock = bool: false]

1. 値を true か false に設定します。true に設定すると、ユーザーはロックされた任意のワークスペースのロックを一時的に解除できますが、false に設定すると、ユーザーはロックを解除できません。
1. ファイルを保存して閉じます。
