---
description: Data Workbench のユーザーがすぐに作業を再開できるよう、再処理または再変換を円滑に行うための手順を説明します。
title: 再処理または再変換の準備
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 66%

---

# 再処理または再変換の準備{#preparing-for-reprocessing-or-retransformation}

Data Workbench のユーザーがすぐに作業を再開できるよう、再処理または再変換を円滑に行うための手順を説明します。

1. [!DNL Detailed Status]インターフェイスでデータセットプロファイルの[!DNL Processing Mode History]をチェックし、前回の処理または変換の経過時間を調べます。

   1. データセットプロファイルで[!DNL Detailed Status]インターフェイスを開きます。
   1. **[!UICONTROL Processing Status]**/*&lt;**[!UICONTROL dataset profile name]**>*/**[!UICONTROL Processing Mode History]**&#x200B;をクリックして、前回の処理または変換の経過時間を表示します。

      * Fast Input は、ログ処理の合計所要時間です。
      * Fast Merge は、変換の合計所要時間です。
      * 2 つの時間の合計（Fast Input + Fast Merge）が、データセットの処理に必要な時間の合計となります。

      以下の例では、ログ処理の所要時間は約 43 秒で、変換の所要時間は 2 分未満となっています。

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      [!DNL Detailed Status]インターフェイスの詳細については、『*Data Workbenchユーザーガイド*』を参照してください。


1. 再処理のスケジューリングとプランニングを行います。ログ処理の最中は、Data Workbench のユーザーがデータにアクセスできないので、再処理は適切な時間帯（週末など）にスケジューリングする必要があります。
1. [!DNL Processing Legend.]のフィールドを使用して再処理と再変換の進行状況を監視します。[!DNL Processing Legend]について詳しくは、『*Data Workbenchユーザーガイド*』を参照してください。
