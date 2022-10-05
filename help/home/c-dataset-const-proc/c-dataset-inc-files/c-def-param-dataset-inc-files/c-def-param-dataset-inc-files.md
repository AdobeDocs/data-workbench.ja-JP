---
description: データセットを設定するときに、特定の意味を持った値の変数（パラメーター）を定義することができます。
title: データセットインクルードファイルでのパラメーターの定義
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 51%

---

# データセットインクルードファイルでのパラメーターの定義{#defining-parameters-in-dataset-include-files}

{{eol}}

データセットを設定するときに、特定の意味を持った値の変数（パラメーター）を定義することができます。

パラメーターに値を割り当てる（つまり、パラメーターを定義する）には、ログ処理で Parameters ベクトルにパラメーターの名前と値を追加します。 [!DNL Transformation Dataset Include] ファイル。 定義したパラメーターは、データセットプロファイルの設定ファイルから参照することができます。こうしたパラメーターを定義して参照することを「パラメーターの置き換え」といいます。データセットを設定する際、パラメーターの置き換えを行うことによって、パラメーターの定義を 1 箇所にまとめることができます。繰り返し参照されるパラメーターや多数のファイルから参照されるパラメーターの更新が必要になったときに、1 回で変更を済ませることができます。

>[!NOTE]
>
>このガイドでは、パラメータという用語は、設定ファイル内の設定の名前（Log Entry Condition、Reprocess、Transformations など）を指す場合に使用されています。 しかし、この節に限っては、パラメーターという用語が出現した場合、設定ファイル内の設定名ではなく、データセットインクルードファイル内の Parameters ベクトルのメンバーを指すものとします。

パラメーターを定義する際は次の点に注意してください。

* パラメーターの定義は 1 回のみとしてください。したがって、複数のデータセットインクルードファイルで同じ変数を定義することはできません。
* 独自に定義したすべてのパラメーターはログ処理段階または変換段階のどちらか一方についてのみ（ローカルに）有効となります。ただし、その一方の段階に関しては、複数のデータセット設定ファイルで（グローバルに）参照できます。例えば、 [!DNL Transformation Dataset Include] ファイル内に定義されたパラメーターは、変換フェーズ全体に対して定義され、 [!DNL Transformation.cfg] ファイルとその他すべて [!DNL Transformation Dataset Include] 継承されたプロファイルのファイル。 このパラメーターは、ログ処理用に定義されません。したがって、 [!DNL Log Processing.cfg] ファイルまたは [!DNL Log Processing Dataset Include] ファイルを削除すると、処理エラーが発生します。

**パラメーターを定義するには**

文字列、数値およびベクトルの各パラメーターは、 [!DNL Log Processing] および [!DNL Transformation Include] ファイル。

1. Data Workbench ウィンドウで、 [!DNL Log Processing] または [!DNL Transformation Dataset Include] ファイル、右クリック **[!UICONTROL Parameters]**&#x200B;を選択し、「 **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. 選択 **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]**&#x200B;または **[!UICONTROL Vector Parameter]**&#x200B;をクリックし、次の節で説明するように、「名前」および「値」パラメーターに入力します。

1. パラメーターを定義したデータセットインクルードファイルを保存するには、右クリックします **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。

>[!NOTE]
>
>アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

**パラメーターを参照するには**

* 別のデータセット設定ファイルで定義したパラメーターを参照する場合は、その名前をと入力する必要があります。 [!DNL $(parameter name)].

定義できるパラメーターのタイプについては、次の節で説明しています。

* [文字列パラメーターと数値パラメーター](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [ベクターパラメーター](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
