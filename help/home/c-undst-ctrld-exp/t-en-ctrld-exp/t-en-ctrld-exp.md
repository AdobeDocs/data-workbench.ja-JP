---
description: 管理者が実験を制御できるようにするには、Webまたはアプリケーションサーバーに対する管理者アクセス権を持つユーザーが、SensorがインストールされているWebクラスター内の各WebまたはアプリケーションサーバーのSensor設定ファイル（通常はtxlogd.confを使用）のExpFileパラメーターを変更する必要があります。
solution: Insight,Analytics
title: 対照実験の有効化
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 対照実験の有効化{#enabling-controlled-experimentation}

管理者が実験を制御できるようにするには、Webまたはアプリケーションサーバーに対する管理者アクセス権を持つユーザーが、SensorがインストールされているWebクラスター内の各WebまたはアプリケーションサーバーのSensor設定ファイル（通常はtxlogd.confを使用）のExpFileパラメーターを変更する必要があります。

さらに、このファイル内の他の2つのパラメータを変更して、テストツール（ExpCookieURLパラメータ）を実装したり、Webサイトの大きなセクションを再マップしたり（ExpPartialMatchパラメータ）できます。 この章では、これらのパラメーターの詳細について説明します。

**txlogd.confファイルを編集するには**

管理者アクセス権を持っている場合は、次の手順を実行します。 管理者アクセス権を持っていない場合は、システムアーキテクトに問い合わせて、次の手順で変更をリクエストします。

1. をインストールす [!DNL Sensor] るWebクラスターまたはWebクラスターのアプリケーションサーバー上のインストールフォルダーに [!DNL Sensor] 移動します。
1. テキスト・エデ [!DNL Sensor] ィタを使用して構成ファイル(通常 [!DNL txlogd.conf]はを使用して名前付け)を開き、ExpFileパラメータの変更で示されているとおりに [ファイルを編集します](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

   (また、ExpCookieURLパラメ [ータの変更（オプション）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) 、ExpPartialMatchパラ [メータの変更（オプション）でも可能](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e))。

1. ファイルを保存して閉じます。
1. をインストールするWebクラスター内のWebまたはアプリケーションサーバーごとに、この手順を [!DNL Sensor] 繰り返します。
