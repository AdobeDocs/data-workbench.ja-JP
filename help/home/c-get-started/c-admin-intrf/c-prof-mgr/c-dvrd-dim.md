---
description: Data Workbenchを使用して作成する新しいディメンション（派生ディメンション）は、クライアント側のディメンションです。
title: 派生ディメンションの使用
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 37%

---

# 派生ディメンションの使用{#work-with-derived-dimensions}

{{eol}}

Data Workbenchを使用して作成する新しいディメンション（派生ディメンション）は、クライアント側のディメンションです。

( [!DNL Transformation.cfg] ファイル ) をData Workbenchサーバーコンピューター上に作成し、派生ディメンションを個別に [!DNL .dim] ファイルを含める必要があります。 その結果、データセットを再処理することなく、既存のディメンションを変更したり、新しい派生ディメンションを作成したりできます。

>[!NOTE]
>
>この節で説明するディメンションの詳細については、該当する「Data Workbench・アプリケーション・ガイド」を参照してください。

データセットの設定および更新プロセスについて詳しくは、『*データセット設定ガイド*』を参照してください。

## 派生ディメンションの作成 {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

派生ディメンションを作成するには、既存のディメンションをコピーして変更することも、ビジュアライゼーションからディメンションを保存することもできます。

## 既存のディメンションから派生ディメンションを作成する {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

ほとんどの場合、ユーザーは既存のディメンションから新しい時間ディメンションを作成します。例えば、既存の「Last 7 Days」ディメンションから新しい「Last 5 Days」ディメンションを作成できます。

1. 内 [!DNL Profile Manager]、 *プロファイル名* 列を右クリックし、作成するディメンションに類似したディメンションのチェックマークを右クリックして、 **[!UICONTROL Copy]**.

   例えば、 [!DNL Last 7 Days.dim] を [!DNL Traffic] プロファイルを選択し、 [!DNL Traffic] 列とクリック **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. を右クリックします。 [!DNL User] コピーしたディメンションを保存するフォルダーの列を選択し、 **[!UICONTROL Paste]**.

   ディメンションが選択した Dimensions フォルダーに表示され、[!DNL User] 列にチェックマークが付きます。

1. 新しいディメンションの名前を変更するには、 [!DNL User] 列に新しい名前を入力し、 [!DNL File] フィールドに入力します。
1. 右クリックメニューから、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. ディメンションを定義するパラメーターが表示されます。
1. 新しいディメンションを定義する必要に応じてパラメーターを変更します。

   時間ディメンションでは、Count パラメーターと Range パラメーターのみを変更する必要がある場合がほとんどです。

1. ファイルを保存するには、右クリックします。 **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   作成したディメンションをプロファイルのすべてのユーザーが使用できるようにする場合は、 [!DNL Profile Manager]. 詳しくは、 [作業プロファイルへのファイルの公開](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

これで、組み込みディメンションと同様に選択して、現在のプロファイルで新しいディメンションを使用できます。

## ビジュアライゼーションからのディメンションの保存 {#section-84cfe5e9ccb640afa2ee4e2da2682757}

プロセスマップとセグメントから拡張ディメンションを保存できます。プロセスマップからディメンションを保存する手順については、「 [プロセスマップからのディメンションの保存](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). セグメントディメンションを保存する手順については、 [セグメントDimensionの作成](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) 82 ページに

## セグメントをディメンションとして保存 {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

定義したセグメントをディメンションとして保存することもできます。手順については、「[セグメントのビジュアライゼーションの再利用](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc)」を参照してください。

## 既存の派生ディメンションの編集 {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   n [!DNL Profile Manager]、 *プロファイル名* 列で、編集するディメンションファイルのチェックマークを右クリックし、 **[!UICONTROL Make Local]**.
1. 内の寸法ファイルのチェックマークを右クリックします。 [!DNL User] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. 必要に応じてパラメーターを入力します。詳しくは、Adobe Consulting Services にお問い合わせください。
1. ファイルを保存するには、右クリックします。 **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   変更したディメンションをプロファイルのすべてのユーザーが使用できるようにする場合は、 [!DNL Profile Manager]. 詳しくは、 [作業プロファイルへのファイルの公開](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
