---
description: 実験を制御できるようにするには、Webサーバーまたはアプリケーションサーバーに管理者がアクセスできるユーザーは、SensorがインストールされているWebクラスター内の各WebまたはアプリケーションサーバーのSensor設定ファイル（通常はtxtlogd.confを使用して名前付け）のExpFileパラメーターを変更する必要があります。
solution: Analytics,Analytics
title: 対照実験の有効化
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 4%

---


# 対照実験の有効化{#enabling-controlled-experimentation}

実験を制御できるようにするには、Webサーバーまたはアプリケーションサーバーに管理者がアクセスできるユーザーは、SensorがインストールされているWebクラスター内の各WebまたはアプリケーションサーバーのSensor設定ファイル（通常はtxtlogd.confを使用して名前付け）のExpFileパラメーターを変更する必要があります。

さらに、このファイル内の他の2つのパラメータを変更して、テストツール（ExpCookieURLパラメータ）を導入したり、Webサイトの大きなセクションを再マップしたり（ExpPartialMatchパラメータ）できます。 この章では、これらのパラメーターについて詳しく説明します。

**txlogd.confファイルを編集するには**

管理者アクセス権を持っている場合は、次の手順を実行します。 管理者アクセス権がない場合は、システムアーキテクトに問い合わせて変更をリクエストし、次の手順を実行します。

1. をインストールするWebクラスターまたはWebクラスター内のアプリケーションサーバーの [!DNL Sensor] インストールフォルダーに移動 [!DNL Sensor] します。
1. テキスト・エディタを使用して [!DNL Sensor] 構成ファイル(通常は [!DNL txlogd.conf]を使用して名前付け)を開き、ExpFileパラメータの [変更で説明されているようにファイルを編集します](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

   (また、ExpCookieURLパラメータの [変更（オプション）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) およびExpPartialMatchパラメータの [変更（オプション）でも同様](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e))。

1. ファイルを保存して閉じます。
1. をインストールするWebクラスター内のWebサーバーまたはアプリケーションサーバーごとに、この手順を繰り返 [!DNL Sensor] します。
