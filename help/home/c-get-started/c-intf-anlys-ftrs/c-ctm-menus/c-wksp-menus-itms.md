---
description: 以下の手順は、ワークスペースウィンドウメニューのサブメニューとメニュー項目の作成にのみ適用されます。
title: ワークスペースメニューとメニュー項目の作成
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 50%

---

# ワークスペースメニューとメニュー項目の作成{#create-a-workspace-menu-and-menu-item}

以下の手順は、ワークスペースウィンドウメニューのサブメニューとメニュー項目の作成にのみ適用されます。

新しいフォルダーおよび新しい派生指標や派生ディメンションを作成することによって、指標やディメンションのメニューをカスタマイズできます。詳しくは、「  [派生](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) 指標の作成と編集および派生Dimensionの [作成と編集](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)。

**新しいワークスペースウィンドウメニューを作成するには**

1. [!DNL Profile Manager]の&#x200B;**[!UICONTROL Menu]**&#x200B;ディレクトリをクリックして、その内容を表示します。
1. Menuディレクトリの[!DNL User]列で、**[!UICONTROL Create]** > **[!UICONTROL Folder]**&#x200B;をクリックします。 New Folder という名前のフォルダーが、[!DNL File] の [!DNL Menu] 列に表示されます。

   >[!NOTE]
   >
   >また、Menuディレクトリ内の任意のサブディレクトリに対して新しいフォルダーを作成することもできます。

1. 新しいフォルダーの名前を変更します。そのフォルダーの [!DNL User] 列で右クリックして、Dir パラメーターに新しい名前を入力します。
1. 新しいフォルダーに必要なファイルを追加します。
1. （オプション）新しいフォルダーの[!DNL User]列で、**[!UICONTROL Create]** > **[!UICONTROL order.txt]**&#x200B;をクリックします。

   [!DNL order.txt] ファイルが、新しいフォルダーの [!DNL File] 列に表示され、新しいファイルに対するチェックマークが [!DNL User] 列に表示されます。

1. （オプション）必要に応じて [!DNL order.txt] ファイルを編集します。[Order.txtファイルを使用したメニューのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)を参照してください。
1. （オプション）作業プロファイルのすべてのユーザーが変更を利用できるようにするには、[!DNL User]列のフォルダーの白いチェックマークを右クリックし、**[!UICONTROL Save Directory to]**/***[!UICONTROL working profile name]**>*&#x200B;をクリックします。

**既存のメニューに新しいメニュー項目を追加するには**

1. 次のいずれかの手順を実行します。

   * メニューに追加する新しいアイテム（ビジュアライゼーション、注釈など）を作成します。

      1. Data Workbenchでワークスペースを開き、必要なアイテムを作成します。
      1. アイテムを次のディレクトリに保存します。

         *Data Workbenchのインストールディレクトリ*\User\*作業プロファイル名*\Work

      1. [!DNL Profile Manager]の&#x200B;**[!UICONTROL Work]**&#x200B;ディレクトリをクリックして、その内容を表示します。
      1. [!DNL User]列で、目的のファイルのチェックマークを右クリックし、**[!UICONTROL Copy]**&#x200B;をクリックします。
      1. 目的のフォルダーの[!DNL User]列で、**[!UICONTROL Paste]**&#x200B;をクリックします。

         ファイルのコピーが新しいフォルダーの [!DNL File] 列に表示され、新しいファイルに対するチェックマークが [!DNL User] 列に表示されます。
   * メニュー（フォルダー）から別のメニューに既存のアイテムをコピーして貼り付けます。

      1. [!DNL Profile Manager]の&#x200B;**[!UICONTROL Menu]**&#x200B;ディレクトリをクリックして、その内容を表示します。
      1. *作業プロファイル名*&#x200B;列で、目的のファイルのチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。
      1. [!DNL User]列のファイルのチェックマークを右クリックし、**[!UICONTROL Copy]**&#x200B;をクリックします。
      1. 目的のフォルダーの[!DNL User]列で、**[!UICONTROL Paste]**&#x200B;をクリックします。 ファイルのコピーが新しいフォルダーの [!DNL File] 列に表示され、新しいファイルに対するチェックマークが [!DNL User] 列に表示されます。


1. （オプション）必要に応じて [!DNL order.txt] ファイルを編集します。[Order.txtファイルを使用したメニューのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)を参照してください。
1. （オプション）作業プロファイルのすべてのユーザーが変更を反映するには、[!DNL User]列の各ファイルの白いチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL working profile name]**>*&#x200B;をクリックします。
1. （オプション）複数のプロファイルにメニュー項目が表示されないようにするには、*working menu name*&#x200B;列でファイルのチェックマークを右クリックし、**[!UICONTROL Remove]**/**[!UICONTROL Yes]**&#x200B;をクリックして、対応するファイルを元のフォルダーから削除します。

   [!DNL User] 列のファイルのチェックマークに対して、この手順を繰り返します。
