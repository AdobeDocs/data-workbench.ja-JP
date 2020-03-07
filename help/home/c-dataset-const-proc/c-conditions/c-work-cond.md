---
description: 条件の追加、削除またはコピーについて取り上げます。
solution: Analytics
title: 条件の操作
topic: Data workbench
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 条件の操作{#working-with-conditions}

条件の追加、削除またはコピーについて取り上げます。

* [データセット設定ファイルに条件を追加するには](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [データセット設定ファイルから条件を削除するには](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [条件をコピーするには](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## データセット設定ファイルに条件を追加するには {#section-3e2a34db047b462585502f69722f6511}

1. While working in your dataset profile, use the [!DNL Profile Manager] to open the dataset configuration file that you want to edit.

   * ファイルを開くに [!DNL Log Processing.cfg] は、「ログ処 [理設定ファイルの編集」を参照してください](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)。

   * ファイルを開くに [!DNL Transformation.cfg] は、「変換設 [定ファイルの編集」を参照してください](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

   * ファイルを開く方法につ [!DNL Dataset Include] いては、「データセットインクル [ードファイル」を参照してくださ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)い。

1. データセット設定ファイル内で、定義する Log Entry Condition パラメーターまたは Condition パラメーターを探します。
1. パラメータを右クリックし、をクリックしま **[!UICONTROL Add new]**&#x200B;す。 次のいずれかのタイプの条件を選択します。

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. 条件のパラメーターを必要に応じて編集します。それぞれの条件のパラメーターについて詳しくは、この付録の該当する節を参照してください。
1. To save your changes, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager,] right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, where profile name is the name of the dataset profile or the inherited profile to which the file belongs.

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

## データセット設定ファイルから条件を削除するには {#section-677270f93f1648c3a268ca2aea7d4540}

1. 削除する条件の名前または条件に対応する番号を右クリックします。
1. Click **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, where number is the number corresponding to the condition that you want to remove.

## 条件をコピーするには {#section-00617bcf2c274f428686b2ec7f2d1db8}

条件は、同じファイル内の別の場所にコピーできるほか、2 つのデータセット設定ファイル間でコピーすることもできます。

1. Right-click the name of the condition or the number corresponding to the condition that you want to copy and click **[!UICONTROL Copy]**.
1. Right-click the name or number of the condition below which you want to place the copied condition and click **[!UICONTROL Paste]**.

