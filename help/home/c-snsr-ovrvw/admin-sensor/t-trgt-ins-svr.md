---
description: Sensorが通信するData Workbenchサーバー(ターゲットサーバー)を変更するには、Sensorがインストールされている各Webサーバーのtxtlogd.confファイルを編集する必要があります。
solution: Analytics
title: ターゲット Data Workbench サーバーの変更
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 6%

---


# ターゲット Data Workbench サーバーの変更{#changing-the-target-data-workbench-server}

Sensorが通信するData Workbenchサーバー(ターゲットサーバー)を変更するには、Sensorがインストールされている各Webサーバーのtxtlogd.confファイルを編集する必要があります。

**ターゲットに変更するには[!DNL data workbench server]**

1. 元のターゲットサーバーと新しいターゲットサーバーの両方を停止します。
1. 元のターゲットサーバーから新しいターゲットサーバーに最新の [!DNL .vsl] ファイルをコピーします。 後の手順で新しいターゲットサーバーを再起動すると、新しいフ [!DNL Sensor] ァイルを作成する代わりに、新しいすべての新しいデータが現在の既存の [!DNL .vsl][!DNL .vsl] ファイルに追加されます。 これを行うには、次の手順を実行します。

   1. 元のターゲットサーバーで、インストールディレクトリ内の [!DNL \Logs] フォルダーを参照 [!DNL data workbench server] します。

   1. フォルダー内の最新の [!DNL .vsl] ファイルをコピーします。
   1. 新しいターゲットサーバーで、インストールディレクトリ内の [!DNL \Logs] フォルダーを参照し、 [!DNL data workbench server] このフォルダーに [!DNL .vsl] ファイルを貼り付けます。

1. がインストールされているWebサーバーの1つ [!DNL Sensor] で、ファイルを開いて編集し [!DNL txlogd.conf] ます。 これを行うには、次の手順を実行します。

   1. インストー [!DNL Sensor] ルディレクトリを参照し、テキストエディターで [!DNL txlogd.conf] ファイルを開きます。

   1. ServerAddressパラメーターを探し、新しいターゲットサーバーのアドレスを反映するように変更します。
   1. ファイルを保存して閉じます。

1. インストールされている残りのWebサーバーすべてで、手順2 ～ 3を繰り返 [!DNL Sensor] します。
1. 元のターゲットサーバー（まだ使用できない場合）と新しいターゲットサーバーを再起動します。
1. 指定した新しいターゲットサーバーにデータが送信され始めます。
