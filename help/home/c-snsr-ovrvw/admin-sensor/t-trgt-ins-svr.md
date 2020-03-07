---
description: Sensorが通信するData Workbenchサーバー（ターゲットサーバー）を変更するには、Sensorがインストールされている各Webサーバーのtxlogd.confファイルを編集する必要があります。
solution: Insight
title: Target Data Workbenchサーバーの変更
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Target Data Workbenchサーバーの変更{#changing-the-target-data-workbench-server}

Sensorが通信するData Workbenchサーバー（ターゲットサーバー）を変更するには、Sensorがインストールされている各Webサーバーのtxlogd.confファイルを編集する必要があります。

**ターゲットに変更するには[!DNL data workbench server]**

1. 元のターゲットサーバーと新しいターゲットサーバーの両方を停止します。
1. 元のターゲット・サーバ [!DNL .vsl] ーから新しいターゲット・サーバーに最新のファイルをコピーします。 後で新しいターゲットサーバーを再起動すると、新しいファイルを作成する代わりに、新しいデ [!DNL Sensor] ータがすべて現在の既存のフ [!DNL .vsl] ァイルに追加され [!DNL .vsl] ます。 これを行うには、次の手順を実行します。

   1. 元のターゲットサーバー上で、インストールディレク [!DNL \Logs] トリ内のフォルダーを [!DNL data workbench server] 参照します。

   1. フォルダー内の最新のフ [!DNL .vsl] ァイルをコピーします。
   1. 新しいターゲットサーバーで、インストールデ [!DNL \Logs] ィレクトリ内のフ [!DNL data workbench server] ォルダーを参照し、このフ [!DNL .vsl] ォルダーにファイルを貼り付けます。

1. がインストールされているWebサーバーの1 [!DNL Sensor] つで、ファイルを開いて編集し [!DNL txlogd.conf] ます。 これを行うには、次の手順を実行します。

   1. インストールディレ [!DNL Sensor] クトリを参照し、テキストエ [!DNL txlogd.conf] ディターでファイルを開きます。

   1. ServerAddressパラメーターを探し、新しいターゲットサーバーのアドレスを反映するように変更します。
   1. ファイルを保存して閉じます。

1. インストールされている残りのWebサーバーすべてで、手順2 ～ 3を [!DNL Sensor] 繰り返します。
1. 元のターゲットサーバー（まだ使用する場合）と新しいターゲットサーバーを再起動します。
1. 指定した新しいターゲットサーバーへのデータの送信が開始されます。
