---
description: Sensorが通信するData Workbenchサーバー(ターゲットサーバー)を変更するには、Sensorがインストールされている各Webサーバーのtxtlogd.confファイルを編集する必要があります。
title: ターゲット Data Workbench サーバーの変更
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 6%

---

# ターゲット Data Workbench サーバーの変更{#changing-the-target-data-workbench-server}

Sensorが通信するData Workbenchサーバー(ターゲットサーバー)を変更するには、Sensorがインストールされている各Webサーバーのtxtlogd.confファイルを編集する必要があります。

**ターゲットに変更するには[!DNL data workbench server]**

1. 元のターゲットサーバーと新しいターゲットサーバーの両方を停止します。
1. 最新の[!DNL .vsl]ファイルを元のターゲットサーバから新しいターゲットサーバにコピーします。 新しいターゲットサーバーを後の手順で再起動すると、新しい[!DNL Sensor]データがすべて現在の既存の[!DNL .vsl]ファイルに追加され、新しい[!DNL .vsl]ファイルが作成されるのではなくなります。 これを行うには、次の手順を実行します。

   1. 元のターゲットサーバーで、[!DNL data workbench server]インストールディレクトリの[!DNL \Logs]フォルダーを参照します。

   1. フォルダー内の最新の[!DNL .vsl]ファイルをコピーします。
   1. 新しいターゲットサーバーで、[!DNL data workbench server]インストールディレクトリの[!DNL \Logs]フォルダーを参照し、[!DNL .vsl]ファイルをこのフォルダーに貼り付けます。

1. [!DNL Sensor]がインストールされているWebサーバーの1つで、[!DNL txlogd.conf]ファイルを開いて編集します。 これを行うには、次の手順を実行します。

   1. [!DNL Sensor]インストールディレクトリを参照し、テキストエディターで[!DNL txlogd.conf]ファイルを開きます。

   1. ServerAddressパラメーターを探し、新しいターゲットサーバーのアドレスを反映するように変更します。
   1. ファイルを保存して閉じます。

1. [!DNL Sensor]がインストールされている残りのすべてのWebサーバーで、手順2 ～ 3を繰り返します。
1. 元のターゲットサーバー（まだ使用できない場合）と新しいターゲットサーバーを再起動します。
1. 指定した新しいターゲットサーバーにデータが送信され始めます。
