---
description: 以下の手順は、ワークスペースウィンドウメニューのサブメニューとメニュー項目の作成にのみ適用されます。
title: ワークスペースメニューとメニュー項目の作成
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 50%

---

# ワークスペースメニューとメニュー項目の作成{#create-a-workspace-menu-and-menu-item}

{{eol}}

以下の手順は、ワークスペースウィンドウメニューのサブメニューとメニュー項目の作成にのみ適用されます。

新しいフォルダーおよび新しい派生指標や派生ディメンションを作成することによって、指標やディメンションのメニューをカスタマイズできます。詳しくは、「 [派生指標の作成と編集](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) および [派生Dimensionの作成と編集](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**新しいワークスペースウィンドウメニューを作成するには**

1. 内 [!DNL Profile Manager]、 **[!UICONTROL Menu]** ディレクトリの内容を表示します。
1. 内 [!DNL User] 列をクリックします。 **[!UICONTROL Create]** > **[!UICONTROL Folder]**. New Folder という名前のフォルダーが、[!DNL File] の [!DNL Menu] 列に表示されます。

   >[!NOTE]
   >
   >また、Menu ディレクトリ内の任意のサブディレクトリに対して新しいフォルダを作成することもできます。

1. 新しいフォルダーの名前を変更します。そのフォルダーの [!DNL User] 列で右クリックして、Dir パラメーターに新しい名前を入力します。
1. 新しいフォルダーに必要なファイルを追加します。
1. （オプション） [!DNL User] 列をクリックし、 **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   [!DNL order.txt] ファイルが、新しいフォルダーの [!DNL File] 列に表示され、新しいファイルに対するチェックマークが [!DNL User] 列に表示されます。

1. （オプション）必要に応じて [!DNL order.txt] ファイルを編集します。詳しくは、 [Order.txt ファイルを使用したメニューのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. （オプション）作業プロファイルのすべてのユーザーが変更を利用できるようにするには、 [!DNL User] 列とクリック **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**既存のメニューに新しいメニュー項目を追加するには**

1. 次のいずれかの手順を実行します。

   * メニューに追加する新しいアイテム（ビジュアライゼーション、注釈など）を作成します。

      1. ワークスペースをData Workbenchで開き、目的の項目を作成します。
      1. アイテムを次のディレクトリに保存します。

         *Data Workbench のインストールディレクトリ*\User\*working profile name*\Work

      1. 内 [!DNL Profile Manager]、 **[!UICONTROL Work]** ディレクトリの内容を表示します。
      1. 内 [!DNL User] 」列で、目的のファイルのチェックマークを右クリックし、 **[!UICONTROL Copy]**.
      1. 内 [!DNL User] 」列で、 **[!UICONTROL Paste]**.

         ファイルのコピーが新しいフォルダーの [!DNL File] 列に表示され、新しいファイルに対するチェックマークが [!DNL User] 列に表示されます。
   * メニュー（フォルダー）から別のメニューに既存のアイテムをコピーして貼り付けます。

      1. 内 [!DNL Profile Manager]、 **[!UICONTROL Menu]** ディレクトリの内容を表示します。
      1. 内 *作業プロファイル名* 」列で、目的のファイルのチェックマークを右クリックし、 **[!UICONTROL Make Local]**.
      1. ファイルのチェックマークを右クリックし、 [!DNL User] 列とクリック **[!UICONTROL Copy]**.
      1. 内 [!DNL User] 」列で、 **[!UICONTROL Paste]**. ファイルのコピーが新しいフォルダーの [!DNL File] 列に表示され、新しいファイルに対するチェックマークが [!DNL User] 列に表示されます。


1. （オプション）必要に応じて [!DNL order.txt] ファイルを編集します。詳しくは、 [Order.txt ファイルを使用したメニューのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. （オプション）作業プロファイルのすべてのユーザーが変更を利用できるようにするには、 [!DNL User] 列とクリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. （オプション）複数のメニューに表示されるメニュー項目を避けるには、 *作業プロファイル名* 列とクリック **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   [!DNL User] 列のファイルのチェックマークに対して、この手順を繰り返します。
