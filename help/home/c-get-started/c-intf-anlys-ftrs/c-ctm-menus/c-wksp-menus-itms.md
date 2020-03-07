---
description: 以下の手順は、ワークスペースウィンドウメニューのサブメニューとメニュー項目の作成にのみ適用されます。
solution: Analytics
title: ワークスペースメニューとメニュー項目の作成
topic: Data workbench
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ワークスペースメニューとメニュー項目の作成{#create-a-workspace-menu-and-menu-item}

以下の手順は、ワークスペースウィンドウメニューのサブメニューとメニュー項目の作成にのみ適用されます。

新しいフォルダーおよび新しい派生指標や派生ディメンションを作成することによって、指標やディメンションのメニューをカスタマイズできます。詳しくは、「 派生指 [標の作成と編集](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) 、派 [生ディメンションの作成と編集](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)。

**新しいワークスペースウィンドウメニューを作成するには**

1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents.
1. In the [!DNL User] column for the Menu directory, click **[!UICONTROL Create]** > **[!UICONTROL Folder]**. New Folder という名前のフォルダーが、[!DNL File] の [!DNL Menu] 列に表示されます。

   >[!NOTE]
   >
   >また、Menuディレクトリ内の任意のサブディレクトリに対して新しいフォルダを作成することもできます。

1. 新しいフォルダーの名前を変更します。そのフォルダーの [!DNL User] 列で右クリックして、Dir パラメーターに新しい名前を入力します。
1. 新しいフォルダーに必要なファイルを追加します。
1. (Optional) In the [!DNL User] column for the new folder, click **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   [!DNL order.txt] ファイルが、新しいフォルダーの [!DNL File] 列に表示され、新しいファイルに対するチェックマークが [!DNL User] 列に表示されます。

1. （オプション）必要に応じて [!DNL order.txt] ファイルを編集します。See [Customizing Menus Using Order.txt Files](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for the folder in the [!DNL User] column and click **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**既存のメニューに新しいメニュー項目を追加するには**

1. 次のいずれかの手順を実行します。

   * メニューに追加する新しいアイテム（ビジュアライゼーション、注釈など）を作成します。

      1. Data Workbenchでワークスペースを開き、目的の項目を作成します。
      1. アイテムを次のディレクトリに保存します。

         *Data Workbenchのインストールディレクトリ*\User\*working profile name*\Work

      1. In the [!DNL Profile Manager], click the **[!UICONTROL Work]** directory to view its contents.
      1. In the [!DNL User] column, right-click the check mark for the desired file and click **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**.

         ファイルのコピーが新しいフォルダーの [!DNL File] 列に表示され、新しいファイルに対するチェックマークが [!DNL User] 列に表示されます。
   * メニュー（フォルダー）から別のメニューに既存のアイテムをコピーして貼り付けます。

      1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents.
      1. In the *working profile name* column, right-click the check mark for the desired file and click **[!UICONTROL Make Local]**.
      1. Right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**. ファイルのコピーが新しいフォルダーの [!DNL File] 列に表示され、新しいファイルに対するチェックマークが [!DNL User] 列に表示されます。


1. （オプション）必要に応じて [!DNL order.txt] ファイルを編集します。See [Customizing Menus Using Order.txt Files](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for each file in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Optional) To avoid having a menu item appear in multiple menus, you should delete the corresponding file from its original folder by right-clicking the check mark for the file in the *working profile name* column and clicking **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   [!DNL User] 列のファイルのチェックマークに対して、この手順を繰り返します。

