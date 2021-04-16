---
description: Sensor設定ファイルtxlogd.confには、SensorがData Workbenchサーバーとの接続を確立する際に使用するパラメーターが含まれています。
title: センサーの txlogd.conf ファイルの編集
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 7%

---

# センサーの txlogd.conf ファイルの編集{#editing-the-sensor-txlogd-conf-file}

Sensor設定ファイルtxlogd.confには、SensorがData Workbenchサーバーとの接続を確立する際に使用するパラメーターが含まれています。

これらのパラメーターには、サーバーのアドレス、ポート番号、通信プロトコル（HTTPまたはHTTPS）が含まれます。 設定ファイルには、ログコンテンツのフィルタリングオプションと制御実験情報も含まれています。 制御下の実験を使用すると、サイトデザイナーはコンテンツをテストしたり、すべてのサイト訪問者のサブセットに対してデザインの変更を行ったりする実験を実行できます。

[!DNL data workbench server]のIPアドレスや[!DNL Sensor]の名前など、他の[!DNL txlogd.conf]パラメーターを変更する場合は、[!DNL txlogd.conf]を更新版に置き換えるだけで、[!DNL Sensor]が自動的に変更内容を取得します。 一部のシステムでは、Webサーバーまたは送信者プロセスを停止しないと、ファイルの編集や置き換えができない場合があります。

**txlogd.confを開いて編集するには**

1. [!DNL Sensor]インストールディレクトリを参照し、テキストエディターで[!DNL txlogd.conf]ファイルを開きます。
1. 必要に応じてファイルを編集します。
1. ファイルを保存して閉じます。

   * 制御実験設定ファイルの場所（[!DNL txlogd.conf]ファイルのExpFileパラメータで定義）は、Webコンテンツ開発者がアクセスできる、またはコンテンツ管理システムが制御するWebサーバー上のディレクトリにある必要があります。
   * ExpCookieURLパラメータの値は、Webサイトのテストに使用される仮想ページです。 そのページを訪問しているユーザーには、新しい追跡IDが与えられます。

[!DNL txlogd.conf]との連携の詳細については、Adobeコンサルティングサービスにお問い合わせください。
