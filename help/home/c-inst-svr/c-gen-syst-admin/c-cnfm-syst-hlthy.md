---
description: Adobeサーバー製品がインストールされているコンピューターが、必要システム構成ドキュメントで定義された最小システム要件を満たしていることを確認する必要があります。
solution: Analytics
title: システムの正常性の確認
uuid: 6d132865-36ab-40fc-be24-e031f356fce2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 5%

---


# システムの正常性の確認{#confirming-your-systems-are-healthy}

Adobeサーバー製品がインストールされているコンピューターが、必要システム構成ドキュメントで定義された最小システム要件を満たしていることを確認する必要があります。

**推奨頻度：** 5 ～ 10分ごと

また、次の項目を監視するなど、特定のハードウェアを動作させる上でのベストプラクティスに従って、システムを監視する必要があります。

* CPU使用率
* ディスク容量
* ハードウェアシステムメッセージ
* 内部システム温度
* メモリ使用量
* 電源の状態
* RAIDまたはディスク・コントローラのパフォーマンスとエラー

Adobeでは、サーバーマシン上のシステムパラメータが設定したしきい値を超えた場合に管理者に警告を出すように管理ツールを設定することをお勧めします。

また、 [!DNL Insight Server] マシンの場合は、各ディスクが設定した最小ディスク容量の制限に達した時点 [!DNL Insight Server] を示すように設定することをAdobeにお勧めします。 これらのアラートの詳細については、「管理アラートの [設定](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)」を参照してください。
