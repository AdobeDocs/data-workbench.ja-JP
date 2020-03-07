---
description: Data Workbenchを使用して作成する新しいディメンション（派生ディメンション）は、クライアント側のディメンションです。
solution: Analytics
title: 派生ディメンションの操作
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 派生ディメンションの操作{#work-with-derived-dimensions}

Data Workbenchを使用して作成する新しいディメンション（派生ディメンション）は、クライアント側のディメンションです。

Instead of defining these dimensions during the dataset construction and update process (in the [!DNL Transformation.cfg] file) on your Data Workbench server computers, derived dimensions are created and stored individually as [!DNL .dim] files in a profile. その結果、データセットを再処理することなく、既存のディメンションを変更したり、新しい派生ディメンションを作成したりできます。

>[!NOTE]
>
>この節で説明するディメンションについて詳しくは、該当するData Workbenchアプリケーションガイドを参照してください。

データセットの設定および更新プロセスについて詳しくは、『*データセット設定ガイド*』を参照してください。

## Create a derived dimensions {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

派生ディメンションを作成するには、既存のディメンションをコピーして変更することも、ビジュアライゼーションからディメンションを保存することもできます。

## 既存のディメンションから派生ディメンションを作成する {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

ほとんどの場合、ユーザーは既存のディメンションから新しい時間ディメンションを作成します。例えば、既存の「Last 7 Days」ディメンションから新しい「Last 5 Days」ディメンションを作成できます。

1. In the [!DNL Profile Manager], in the *profile name* column, right-click the check mark for a dimension that is similar to the dimension that you want to create and click **[!UICONTROL Copy]**.

   For example, to copy the [!DNL Last 7 Days.dim] from the Reporting folder of the [!DNL Traffic] profile, you right-click the check mark for the file name in the [!DNL Traffic] column and click **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Right-click in the [!DNL User] column for the folder in which you want to store the copied dimension and click **[!UICONTROL Paste]**.

   ディメンションが選択した Dimensions フォルダーに表示され、[!DNL User] 列にチェックマークが付きます。

1. To rename the new dimension, right-click its check mark in the [!DNL User] column and type the new name in the [!DNL File] field.
1. 右クリックメニューで、/をクリッ **[!UICONTROL Open]** クしま **[!UICONTROL from the workbench]**&#x200B;す。 ディメンションを定義するパラメーターが表示されます。
1. 新しいディメンションを定義する必要に応じてパラメーターを変更します。

   時間ディメンションでは、Count パラメーターと Range パラメーターのみを変更する必要がある場合がほとんどです。

1. To save the file, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

   If you would like all users of a profile to use the dimension that you created, you must upload it to the profile using the [!DNL Profile Manager]. 詳しくは、作業プロファイルへ [のファイルの公開を参照してください](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。

これで、組み込みディメンションと同様に選択して、現在のプロファイルで新しいディメンションを使用できます。

## ビジュアライゼーションからのディメンションの保存 {#section-84cfe5e9ccb640afa2ee4e2da2682757}

プロセスマップとセグメントから拡張ディメンションを保存できます。プロセスマップからディメンションを保存する手順については、「 [プロセスマップからのディメンションの保存](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). セグメントディメンションを保存する手順については、「 [Creating Segment Dimensions](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) on page 82」を参照してください。

## セグメントをディメンションとして保存する {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

定義したセグメントをディメンションとして保存することもできます。手順については、「[セグメントのビジュアライゼーションの再利用](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc)」を参照してください。

## Edit an existing derived dimension {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   n the [!DNL Profile Manager], in the *profile name* column, right-click the check mark for the dimension file that you want to edit and click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the dimension file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. 必要に応じてパラメーターを入力します。詳しくは、Adobe Consulting Services にお問い合わせください。
1. To save the file, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

   If you would like all users of a profile to use the modified dimension, you must upload it to the profile using the [!DNL Profile Manager]. 詳しくは、作業プロファイルへ [のファイルの公開を参照してください](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。

