---
description: Sensor設定ファイルtxlogd.confには、SensorがData Workbenchサーバーとの接続を確立する際に使用するパラメーターが含まれています。
solution: Analytics
title: センサーの txlogd.conf ファイルの編集
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 7%

---


# センサーの txlogd.conf ファイルの編集{#editing-the-sensor-txlogd-conf-file}

Sensor設定ファイルtxlogd.confには、SensorがData Workbenchサーバーとの接続を確立する際に使用するパラメーターが含まれています。

これらのパラメーターには、サーバーのアドレス、ポート番号、通信プロトコル（HTTPまたはHTTPS）が含まれます。 設定ファイルには、ログコンテンツのフィルタリングオプションと制御実験情報も含まれています。 制御下の実験を使用すると、サイトデザイナーはコンテンツをテストしたり、すべてのサイト訪問者のサブセットに対してデザインの変更を行ったりする実験を実行できます。

のIPアドレス [!DNL txlogd.conf] やの名前など、他の [!DNL data workbench server] パラメーターを変更する場合は、単に更新バージョン [!DNL Sensor]に置き換えて、変更内容を自動的に取得できる場合があ [!DNL txlogd.conf][!DNL Sensor] ります。 一部のシステムでは、Webサーバーまたは送信者プロセスを停止しないと、ファイルの編集や置き換えができない場合があります。

**txlogd.confを開いて編集するには**

1. インストー [!DNL Sensor] ルディレクトリを参照し、テキストエディターで [!DNL txlogd.conf] ファイルを開きます。
1. 必要に応じてファイルを編集します。
1. ファイルを保存して閉じます。

   * 制御実験設定ファイルの場所（ファイル内のExpFileパラメータで定義）は、Webコンテンツ開発者がアクセスできる、またはコンテンツ管理システムが制御するWebサーバー上のディレクトリにある必要があります。 [!DNL txlogd.conf]
   * ExpCookieURLパラメータの値は、Webサイトのテストに使用される仮想ページです。 そのページを訪問しているユーザーには、新しい追跡IDが与えられます。

を使用する方法の詳細については、Adobeのコンサルティングサービス [!DNL txlogd.conf]にお問い合わせください。
