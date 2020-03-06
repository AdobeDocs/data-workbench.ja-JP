---
description: Data Workbench のユーザーがすぐに作業を再開できるよう、再処理または再変換を円滑に行うための手順を説明します。
solution: Analytics
title: 再処理または再変換の準備
topic: Data workbench
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 再処理または再変換の準備{#preparing-for-reprocessing-or-retransformation}

Data Workbench のユーザーがすぐに作業を再開できるよう、再処理または再変換を円滑に行うための手順を説明します。

1. Determine the elapsed time of previous processing or transformation by checking the dataset profile&#39;s [!DNL Processing Mode History] in the [!DNL Detailed Status] interface.

   1. While working in your dataset profile, open the [!DNL Detailed Status] interface.
   1. > **[!UICONTROL Processing Status]** &lt;> *>をク&#x200B;**[!UICONTROL dataset profile name]**リックし***[!UICONTROL Processing Mode History]** て、前の処理または変換の経過時間を表示します。

      * Fast Input は、ログ処理の合計所要時間です。
      * Fast Merge は、変換の合計所要時間です。
      * 2 つの時間の合計（Fast Input + Fast Merge）が、データセットの処理に必要な時間の合計となります。
      以下の例では、ログ処理の所要時間は約 43 秒で、変換の所要時間は 2 分未満となっています。

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      For more information about the [!DNL Detailed Status] interface, see the *Data Workbench User Guide*.


1. 再処理のスケジューリングとプランニングを行います。ログ処理の最中は、Data Workbench のユーザーがデータにアクセスできないので、再処理は適切な時間帯（週末など）にスケジューリングする必要があります。
1. 再処理と再変換の進行状況を監視します。に関する詳細は、『 [!DNL Processing Legend.] Data Workbenchユーザーガ [!DNL Processing Legend]イド』のフィールドを *参照してください*。
