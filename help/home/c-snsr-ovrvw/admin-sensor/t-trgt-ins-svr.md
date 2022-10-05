---
description: センサーが通信する Data Workbench サーバー（ターゲットサーバー）を変更するには、センサーがインストールされている各 Web サーバーで txlogd.conf ファイルを編集する必要があります。
title: ターゲット Data Workbench サーバーの変更
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 6%

---

# ターゲット Data Workbench サーバーの変更{#changing-the-target-data-workbench-server}

{{eol}}

センサーが通信する Data Workbench サーバー（ターゲットサーバー）を変更するには、センサーがインストールされている各 Web サーバーで txlogd.conf ファイルを編集する必要があります。

**ターゲットに変更するには[!DNL data workbench server]**

1. 元のターゲット・サーバと新しいターゲット・サーバの両方を停止します。
1. 最新の [!DNL .vsl] ファイルを元のターゲット・サーバから新しいターゲット・サーバに送信します。 後の手順で新しいターゲットサーバーを再起動すると、新しいサーバーがすべて [!DNL Sensor] 現在の既存のデータに追加するデータ [!DNL .vsl] 新しい [!DNL .vsl] ファイル。 それには、次の手順を実行します。

   1. 元のターゲットサーバーで、 [!DNL \Logs] フォルダーを [!DNL data workbench server] インストールディレクトリ。

   1. 最新の [!DNL .vsl] ファイルをフォルダーに格納します。
   1. 新しいターゲットサーバーで、 [!DNL \Logs] フォルダーを [!DNL data workbench server] インストールディレクトリに、 [!DNL .vsl] ファイルをこのフォルダーに保存します。

1. 次のいずれかの Web サーバー上： [!DNL Sensor] がインストールされ、開いて編集されている [!DNL txlogd.conf] ファイル。 それには、次の手順を実行します。

   1. 次を参照： [!DNL Sensor] インストールディレクトリを開き、 [!DNL txlogd.conf] ファイルを編集します。

   1. ServerAddress パラメーターを探し、新しいターゲットサーバーのアドレスを反映するように変更します。
   1. ファイルを保存して閉じます。

1. 手順 2 ～ 3 を、 [!DNL Sensor] がインストールされている。
1. 元のターゲット・サーバ（まだ使用されている場合）と新しいターゲット・サーバを再起動します。
1. データは、指定した新しいターゲットサーバーへの送信を開始します。
