---
description: 実装をより詳細に監視するには、サーバーコンピューター上のすべてのポートと、それらの各ポートで実行されるソフトウェア製品を監視します。
solution: Analytics
title: ポートとアプリケーションの監視
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---


# ポートとアプリケーションの監視{#monitoring-ports-and-applications}

実装をより詳細に監視するには、サーバーコンピューター上のすべてのポートと、それらの各ポートで実行されるソフトウェア製品を監視します。

**推奨頻度：** 5 ～ 10分ごと

アプリケーションまたはスクリプトを使用して、各アプリケーションが実行されているTCPポート（通常はポート80または443）を監視し、そのポートにアプリケーションがバインドされていることを確認できます。 これを行うには、監視対象のマシンから申し込みステータスページを要求します。

**申し込みステータスページをリクエストするには**

1. 監視対象のマシン上で、監視アプリケーションまたはスクリプトがマシンにアクセスできるようにアクセス制御を変更します。 手順については、「アクセス制御の [設定](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)」を参照してください。
1. Connect [!DNL https://IP Address/Status/]（「IP Address」は、ステータスを受け取るマシンのIPアドレスです）。

   例：[!DNL https://127.0.0.1/Status/]

   マシンは、サーバーステータスの説明を返す必要があります。 応答しない場合は、イベントログを確認し、Adobeカスタマーケアにお問い合わせください。

   この種類の高度な監視の詳細については、Adobeコンサルティングサービスにお問い合わせください。

