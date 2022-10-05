---
description: Data Workbench のユーザーがすぐに作業を再開できるよう、再処理または再変換を円滑に行うための手順を説明します。
title: 再処理または再変換の準備
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 66%

---

# 再処理または再変換の準備{#preparing-for-reprocessing-or-retransformation}

{{eol}}

Data Workbench のユーザーがすぐに作業を再開できるよう、再処理または再変換を円滑に行うための手順を説明します。

1. データセットプロファイルの [!DNL Processing Mode History] 内 [!DNL Detailed Status] インターフェイス。

   1. データセットプロファイル内で、 [!DNL Detailed Status] インターフェイス。
   1. クリック **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** をクリックして、以前の処理または変換の経過時間を表示します。

      * Fast Input は、ログ処理の合計所要時間です。
      * Fast Merge は、変換の合計所要時間です。
      * 2 つの時間の合計（Fast Input + Fast Merge）が、データセットの処理に必要な時間の合計となります。

      以下の例では、ログ処理の所要時間は約 43 秒で、変換の所要時間は 2 分未満となっています。

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      詳しくは、 [!DNL Detailed Status] インターフェイスについては、 *Data Workbenchユーザーガイド*.


1. 再処理のスケジューリングとプランニングを行います。ログ処理の最中は、Data Workbench のユーザーがデータにアクセスできないので、再処理は適切な時間帯（週末など）にスケジューリングする必要があります。
1. 再処理と再変換の進行状況を監視するには、 [!DNL Processing Legend.] 詳しくは、 [!DNL Processing Legend]を参照し、 *Data Workbenchユーザーガイド*.
