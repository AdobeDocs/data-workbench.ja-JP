---
description: Sensor設定ファイルのtxlogd.confには、SensorがData Workbenchサーバーとの接続を確立する際に使用するパラメーターが含まれています。
title: センサーの txlogd.conf ファイルの編集
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 7%

---

# センサーの txlogd.conf ファイルの編集{#editing-the-sensor-txlogd-conf-file}

Sensor設定ファイルのtxlogd.confには、SensorがData Workbenchサーバーとの接続を確立する際に使用するパラメーターが含まれています。

これらのパラメーターには、サーバーのアドレス、ポート番号、通信プロトコル（HTTPまたはHTTPS）が含まれます。 設定ファイルには、ログコンテンツのフィルタリングオプションと、対照実験情報も含まれています。 対照実験を使用すると、サイトデザイナーは、すべてのサイト訪問者のサブセットに対して、コンテンツやデザインの変更をテストする実験を実行できます。

[!DNL data workbench server]のIPアドレスや[!DNL Sensor]の名前など、他の[!DNL txlogd.conf]パラメーターを変更する場合、[!DNL txlogd.conf]を更新版に置き換えれば、[!DNL Sensor]が自動的に変更内容を取得します。 一部のシステムでは、Webサーバーまたはトランスミッタープロセスを停止しないと、ファイルの編集や置き換えができない場合があります。

**txlogd.confを開いて編集するには**

1. [!DNL Sensor]インストールディレクトリを参照し、[!DNL txlogd.conf]ファイルをテキストエディターで開きます。
1. 必要に応じてファイルを編集します。
1. ファイルを保存して閉じます。

   * 対照実験設定ファイルの場所（[!DNL txlogd.conf]ファイルのExpFileパラメーターで定義）は、Webコンテンツ開発者がアクセスできる、またはコンテンツ管理システムが制御するWebサーバー上のディレクトリにある必要があります。
   * ExpCookieURLパラメーターの値は、Webサイトのテストに使用される仮想ページです。 そのページにアクセスするユーザーには、新しいトラッキングIDが付与されます。

[!DNL txlogd.conf]の使用に関する詳細は、Adobeコンサルティングサービスにお問い合わせください。
