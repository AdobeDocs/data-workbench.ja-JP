---
description: 条件の追加、削除またはコピーについて取り上げます。
title: 条件の操作
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 54%

---

# 条件の操作{#working-with-conditions}

条件の追加、削除またはコピーについて取り上げます。

* [データセット設定ファイルに条件を追加するには](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [データセット設定ファイルから条件を削除するには](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [条件をコピーするには](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## データセット設定ファイルに条件を追加するには {#section-3e2a34db047b462585502f69722f6511}

1. データセットプロファイル内で[!DNL Profile Manager]を使用して、編集するデータセット設定ファイルを開きます。

   * [!DNL Log Processing.cfg]ファイルを開くには、[ログ処理設定ファイルの編集](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)を参照してください。

   * [!DNL Transformation.cfg]ファイルを開くには、[変換設定ファイルの編集](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)を参照してください。

   * [!DNL Dataset Include]ファイルを開くには、[データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)を参照してください。

1. データセット設定ファイル内で、定義する Log Entry Condition パラメーターまたは Condition パラメーターを探します。
1. パラメーターを右クリックし、**[!UICONTROL Add new]**&#x200B;をクリックします。 次のいずれかのタイプの条件を選択します。

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. 条件のパラメーターを必要に応じて編集します。それぞれの条件のパラメーターについて詳しくは、この付録の該当する節を参照してください。
1. 変更を保存するには、ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

1. ローカルでおこなった変更を有効にするには、[!DNL Profile Manager,]で[!DNL User]列のファイルのチェックマークを右クリックし、 **[!UICONTROL Save to]** / &lt;* **[!UICONTROL profile name]***>をクリックします。profile nameは、ファイルが属するデータセットプロファイルまたは継承されたプロファイルの名前です。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

## データセット設定ファイルから条件を削除するには {#section-677270f93f1648c3a268ca2aea7d4540}

1. 削除する条件の名前または条件に対応する番号を右クリックします。
1. **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>をクリックします。numberは、削除する条件に対応する番号です。

## 条件をコピーするには {#section-00617bcf2c274f428686b2ec7f2d1db8}

条件は、同じファイル内の別の場所にコピーできるほか、2 つのデータセット設定ファイル間でコピーすることもできます。

1. コピーする条件の名前または条件に対応する番号を右クリックし、「**[!UICONTROL Copy]**」をクリックします。
1. コピーした条件を配置する条件の名前または番号を右クリックし、「**[!UICONTROL Paste]**」をクリックします。
