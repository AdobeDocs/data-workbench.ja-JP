---
description: データセットを設定するときに、特定の意味を持った値の変数（パラメーター）を定義することができます。
title: データセットインクルードファイルでのパラメーターの定義
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 51%

---

# データセットインクルードファイルでのパラメーターの定義{#defining-parameters-in-dataset-include-files}

データセットを設定するときに、特定の意味を持った値の変数（パラメーター）を定義することができます。

パラメーターに値を割り当てる（パラメーターを定義する）には、ログ処理ファイルまたは[!DNL Transformation Dataset Include]ファイルのParametersベクトルにパラメーターの名前と値を追加します。 定義したパラメーターは、データセットプロファイルの設定ファイルから参照することができます。こうしたパラメーターを定義して参照することを「パラメーターの置き換え」といいます。データセットを設定する際、パラメーターの置き換えを行うことによって、パラメーターの定義を 1 箇所にまとめることができます。繰り返し参照されるパラメーターや多数のファイルから参照されるパラメーターの更新が必要になったときに、1 回で変更を済ませることができます。

>[!NOTE]
>
>このガイドでは、パラメーターという用語は、設定ファイル内の設定の名前（Log Entry Condition、Reprocess、Transformationsなど）を指しています。 しかし、この節に限っては、パラメーターという用語が出現した場合、設定ファイル内の設定名ではなく、データセットインクルードファイル内の Parameters ベクトルのメンバーを指すものとします。

パラメーターを定義する際は次の点に注意してください。

* パラメーターの定義は 1 回のみとしてください。したがって、複数のデータセットインクルードファイルで同じ変数を定義することはできません。
* 独自に定義したすべてのパラメーターはログ処理段階または変換段階のどちらか一方についてのみ（ローカルに）有効となります。ただし、その一方の段階に関しては、複数のデータセット設定ファイルで（グローバルに）参照できます。例えば、[!DNL Transformation Dataset Include]ファイルでパラメーターを定義した場合、変換フェーズ全体に対してパラメーターが定義され、[!DNL Transformation.cfg]ファイル内で参照し、継承されたプロファイルに対して他のすべての[!DNL Transformation Dataset Include]ファイルを参照できます。 このパラメーターは、ログ処理用に定義されません。したがって、[!DNL Log Processing.cfg]ファイルまたは[!DNL Log Processing Dataset Include]ファイル内のパラメーターを参照すると、処理エラーが発生します。

**パラメーターを定義するには**

文字列、数値およびベクトルの各パラメーターは、[!DNL Log Processing]ファイルと[!DNL Transformation Include]ファイルで定義できます。

1. [!DNL Log Processing]または[!DNL Transformation Dataset Include]ファイルのData Workbenchウィンドウで、**[!UICONTROL Parameters]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Parameter]**&#x200B;をクリックします。

1. **[!UICONTROL String Parameter]**、**[!UICONTROL Numeric Parameter]**&#x200B;または&#x200B;**[!UICONTROL Vector Parameter]**&#x200B;を選択し、次の節で説明するように、「名前」および「値」パラメーターを入力します。

1. パラメーターを定義したデータセットインクルードファイルを保存するには、ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

1. ローカルで作成した変更を反映するには、[!DNL Profile Manager]で[!DNL User]列のファイルのチェックマークを右クリックし、 **[!UICONTROL Save to]** / *&lt;**[!UICONTROL profile name]***&#x200B;をクリックします。profile nameは、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です。

>[!NOTE]
>
>アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

**パラメーターを参照するには**

* 定義したパラメーターを別のデータセット設定ファイルで参照する場合は、その名前を[!DNL $(parameter name)]と入力する必要があります。

定義できるパラメーターのタイプについては、次の節で説明しています。

* [文字列パラメーターと数値パラメーター](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [ベクターパラメーター](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
