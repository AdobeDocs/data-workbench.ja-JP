---
description: 実験の制御を可能にするには、Webまたはアプリケーションサーバーに管理者がアクセスできる場合、SensorがインストールされているWebクラスター内の各WebまたはアプリケーションサーバーのSensor設定ファイルのExpFileパラメーター（通常はtxlogd.confを使用して）を変更する必要があります。
solution: Analytics,Analytics
title: 対照実験の有効化
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 4%

---

# 対照実験の有効化{#enabling-controlled-experimentation}

実験の制御を可能にするには、Webまたはアプリケーションサーバーに管理者がアクセスできる場合、SensorがインストールされているWebクラスター内の各WebまたはアプリケーションサーバーのSensor設定ファイルのExpFileパラメーター（通常はtxlogd.confを使用して）を変更する必要があります。

さらに、このファイル内の他の2つのパラメーターを変更して、テストツール（ExpCookieURLパラメーター）を実装するか、Webサイトの大部分のセクションを再マップします（ExpPartialMatchパラメーター）。 この章では、これらのパラメーターの詳細について説明します。

**txlogd.confファイルを編集するには**

管理者アクセス権がある場合は、次の手順を実行します。 管理者アクセス権がない場合は、システムアーキテクトに連絡して、次の手順で変更をリクエストします。

1. [!DNL Sensor]がインストールされているWebクラスターまたはアプリケーションサーバーの[!DNL Sensor]インストールフォルダーに移動します。
1. テキストエディターを使用して[!DNL Sensor]設定ファイル（通常は[!DNL txlogd.conf]という名前）を開き、[ExpFileパラメーター](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)の変更の指示に従ってファイルを編集します。

   (オプションとして、 [ExpCookieURLパラメーターの変更（オプション）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)および[ExpPartialMatchパラメーターの変更（オプション）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e)でも可能です)。

1. ファイルを保存して閉じます。
1. [!DNL Sensor]がインストールされているWebクラスター内のWebサーバーまたはアプリケーションサーバーごとに、この手順を繰り返します。
