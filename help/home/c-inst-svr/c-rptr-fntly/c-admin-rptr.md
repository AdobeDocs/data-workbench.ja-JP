---
description: リピータ機能の管理タスクは、Insightサーバーの管理タスクと非常に似ています。
solution: Insight
title: リピータの管理
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# リピータの管理{#administering-repeater}

リピータ機能の管理タスクは、Insightサーバーの管理タスクと非常に似ています。

次の管理タスクが適用されます。リピーターサーバーで [!DNL Insight Server] DPUを使用できるようにする必要がある例外または変更は、各手順の後に記録されます。

* [デジタル証明書の再検証](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Confirming that the Service Is Running](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) Servicesコントロールパネルのサービスのリストで、「Repeater」を探します。

* [アクセス制御の設定](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Monitoring Disk Space](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) ：リピータ・サーバに適用されるデータ・タイプは、イベント、オペレーティング・システム、システム・データです。 バックアップストレージにリピータサーバを使用している場合、マシン上で使用可能なデータストレージ領域を増やす必要が生じた場合は、最新の日のログファイルを除くすべてのファイルを別のマシンまたはデータストレージメディア（zipドライブ、テープなど）に移動できます。 データを移動する際に、リピーターサービスを停止する必要はありません。

   >[!NOTE]
   >
   >Repeaterからファイルを削除する前に、ファイルのバックアップコ [!DNL .vsl] ピーの整合性を検証する必要があります。

* [管理アラートの設定](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [管理イベントの監視](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [監査ログの監視](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [通信の設定](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [サービス機能の再起動は](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)[!DNL Repeater] 、継続的に実行するように設計されています。 コンピューターを再起動すると、リピーターが自動的に再起動します。 リピーターを手動で起動および停止する必要がある場合は、Windowsの[サービス]コントロールパネルを使用して実行できます。

