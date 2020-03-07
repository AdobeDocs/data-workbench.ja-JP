---
description: Sensor設定ファイルtxlogd.confには、SensorがData Workbenchサーバーとの接続を確立するために使用するパラメーターが含まれています。
solution: Insight
title: Sensor txlogd.confファイルの編集
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Sensor txlogd.confファイルの編集{#editing-the-sensor-txlogd-conf-file}

Sensor設定ファイルtxlogd.confには、SensorがData Workbenchサーバーとの接続を確立するために使用するパラメーターが含まれています。

これらのパラメーターには、サーバーのアドレス、ポート番号、通信プロトコル（HTTPまたはHTTPS）が含まれます。 設定ファイルには、ログコンテンツのフィルタリングオプションと、制御された実験情報も含まれます。 制御実験を使用すると、サイトデザイナーは、すべてのサイト訪問者のサブセットに対してコンテンツをテストしたり、変更を設計したりする実験を行うことができます。

のIPアドレス [!DNL txlogd.conf] やの名前など、他のパラメータを変更する場合は、単に最新のバージョンに置き換えて、変更内容を [!DNL data workbench server] 自動的に取 [!DNL Sensor][!DNL txlogd.conf][!DNL Sensor] 得することができます。 一部のシステムでは、Webサーバーまたは送信機プロセスを停止しないと、ファイルの編集や置き換えができない場合があります。

**txlogd.confを開いて編集するには**

1. インストールディレ [!DNL Sensor] クトリを参照し、テキストエ [!DNL txlogd.conf] ディターでファイルを開きます。
1. 必要に応じてファイルを編集します。
1. ファイルを保存して閉じます。

   * 制御実験設定ファイルの場所（ファイル内のExpFileパラメータで定義）は、Webコンテンツ開発者がアクセスできる、またはコンテンツ管理システムで制御されるWebサーバー上のディレクトリ内に置く必要があります。 [!DNL txlogd.conf]
   * ExpCookieURLパラメータの値は、Webサイトのテストに使用される仮想ページです。 そのページを訪問したユーザーには、新しい追跡IDが割り当てられます。

との作業について詳しくは、アドビのコンサルテ [!DNL txlogd.conf]ィングサービスにお問い合わせください。
