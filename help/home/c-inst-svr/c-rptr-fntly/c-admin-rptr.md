---
description: リピーター機能の管理タスクは、Insight Serverの管理環境と非常に似ています。
title: リピーターの管理
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
exl-id: 5c7a4f95-be4b-4c2c-8dea-19037ba0b5cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 12%

---

# リピーターの管理{#administering-repeater}

リピーター機能の管理タスクは、Insight Serverの管理環境と非常に似ています。

次の管理タスクが適用されます。[!DNL Insight Server] DPUをリピーターサーバと共に使用できるようにするために必要な例外または変更は、各手順の後に記録されます。

* [電子証明書の再検証](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [サービスの実行状態の確認](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) [サービス]コントロールパネルのサービスのリストで、[リピータ]を探します。

* [アクセス制御の設定](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Monitoring Disk ](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) Spaceリピータサーバに適用されるデータタイプは、イベント、オペレーティングシステム、およびシステムデータです。バックアップストレージにリピーターサーバーを使用していて、そのコンピューター上でより多くのデータストレージ容量を使用できるようになった場合は、最新のログファイル以外のすべてを別のマシンまたはデータストレージ媒体（zipドライブ、テープなど）に移動できます。 データを移動する場合、リピーターサービスを停止する必要はありません。

   >[!NOTE]
   >
   >[!DNL .vsl]ファイルをリピータから削除する前に、そのバックアップコピーの整合性を確認する必要があります。

* [管理アラートの設定](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [管理イベントの監視](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [監査ログの監視](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [通信の設定](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [Service機能の再起動は、連続して実行するように設計されてい](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)  [!DNL Repeater] ます。マシンを再起動すると、リピーターが自動的に再起動します。 リピーターを手動で開始して停止する必要がある場合は、Windowsの[サービス]コントロールパネルを使用して実行できます。
