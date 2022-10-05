---
description: センサー設定ファイルの txlogd.conf には、Sensor が Data Workbench サーバーとの接続を確立する際に使用するパラメーターが含まれています。
title: センサーの txlogd.conf ファイルの編集
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 7%

---

# センサーの txlogd.conf ファイルの編集{#editing-the-sensor-txlogd-conf-file}

{{eol}}

センサー設定ファイルの txlogd.conf には、Sensor が Data Workbench サーバーとの接続を確立する際に使用するパラメーターが含まれています。

これらのパラメータには、サーバーのアドレス、ポート番号、通信プロトコル（HTTP または HTTPS）が含まれます。 設定ファイルには、ログコンテンツのフィルタリングオプションと、対照実験情報も含まれています。 対照実験を使用すると、サイトデザイナーは、すべてのサイト訪問者のサブセットに対して、コンテンツをテストしたり、デザインの変更をテストしたりできます。

その他を変更する場合 [!DNL txlogd.conf] パラメータ ( [!DNL data workbench server] または [!DNL Sensor]を使用する場合、 [!DNL txlogd.conf] を更新し、 [!DNL Sensor] 変更が自動的に反映されます。 一部のシステムでは、Web サーバーまたはトランスミッタープロセスを停止しないと、ファイルを編集または置き換えることができない場合があります。

**txlogd.conf を開いて編集するには**

1. 次を参照： [!DNL Sensor] インストールディレクトリを開き、 [!DNL txlogd.conf] ファイルを編集します。
1. 必要に応じてファイルを編集します。
1. ファイルを保存して閉じます。

   * 対照実験設定ファイルの場所 ( [!DNL txlogd.conf] ファイル ) は、Web コンテンツ開発者がアクセスできる、またはコンテンツ管理システムによって制御される、Web サーバー上のディレクトリに存在する必要があります。
   * ExpCookieURL パラメーターの値は、Web サイトのテストに使用される仮想ページです。 そのページにアクセスするユーザーには、新しいトラッキング ID が割り当てられます。

の操作の詳細 [!DNL txlogd.conf]、Adobeコンサルティングサービスにお問い合わせください。
