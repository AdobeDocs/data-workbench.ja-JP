---
description: データセットを設定するときに、特定の意味を持った値の変数（パラメーター）を定義することができます。
solution: Analytics
title: データセットインクルードファイルでのパラメーターの定義
topic: Data workbench
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データセットインクルードファイルでのパラメーターの定義{#defining-parameters-in-dataset-include-files}

データセットを設定するときに、特定の意味を持った値の変数（パラメーター）を定義することができます。

To assign a value to a parameter (that is, to define the parameter), you add the parameter&#39;s name and value to the Parameters vector in a log processing or [!DNL Transformation Dataset Include] file. 定義したパラメーターは、データセットプロファイルの設定ファイルから参照することができます。こうしたパラメーターを定義して参照することを「パラメーターの置き換え」といいます。データセットを設定する際、パラメーターの置き換えを行うことによって、パラメーターの定義を 1 箇所にまとめることができます。繰り返し参照されるパラメーターや多数のファイルから参照されるパラメーターの更新が必要になったときに、1 回で変更を済ませることができます。

>[!NOTE]
>
>このガイドでは、設定ファイル（Log Entry Condition、Reprocess、Transformationsなど）内の設定の名前を指すために、パラメーターという用語が使用されています。 しかし、この節に限っては、パラメーターという用語が出現した場合、設定ファイル内の設定名ではなく、データセットインクルードファイル内の Parameters ベクトルのメンバーを指すものとします。

パラメーターを定義する際は次の点に注意してください。

* パラメーターの定義は 1 回のみとしてください。したがって、複数のデータセットインクルードファイルで同じ変数を定義することはできません。
* 独自に定義したすべてのパラメーターはログ処理段階または変換段階のどちらか一方についてのみ（ローカルに）有効となります。ただし、その一方の段階に関しては、複数のデータセット設定ファイルで（グローバルに）参照できます。For example, if you define a parameter in a [!DNL Transformation Dataset Include] file, the parameter is defined for the entire transformation phase, and you can reference it in the [!DNL Transformation.cfg] file and all other [!DNL Transformation Dataset Include] files for the inherited profiles. The parameter would not be defined for log processing; therefore, any references to the parameter in the [!DNL Log Processing.cfg] file or a [!DNL Log Processing Dataset Include] file would generate a processing error.

**パラメーターを定義するには**

文字列、数値、ベクトルの各パラメーターは、およびファイルで [!DNL Log Processing] 定義で [!DNL Transformation Include] きます。

1. またはファイルのData Workbenchウィンド [!DNL Log Processing] ウで右ク [!DNL Transformation Dataset Include] リックし、 **[!UICONTROL Parameters]**/をクリック **[!UICONTROL Add new]** します **[!UICONTROL Parameter]**。

1. 、、ま **[!UICONTROL String Parameter]**&#x200B;たは **[!UICONTROL Numeric Parameter]**&#x200B;を選択 **[!UICONTROL Vector Parameter]**&#x200B;し、次の節で説明するように、NameとValueのパラメーターを設定します。

1. To save the dataset include file in which you have defined the parameter, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

>[!NOTE]
>
>アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

**パラメーターを参照するには**

* When you reference a defined parameter in another dataset configuration file, you must type its name as [!DNL $(parameter name)].

定義できるパラメーターのタイプについては、次の節で説明しています。

* [文字列パラメーターと数値パラメーター](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [ベクトルパラメーター](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)

