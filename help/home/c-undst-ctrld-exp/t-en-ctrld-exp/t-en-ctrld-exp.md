---
description: 対照実験を有効にするには、Web またはアプリケーションサーバーへの管理者アクセス権を持つユーザーが、Sensor がインストールされている Web クラスター内の各 Web またはアプリケーションサーバーの Sensor 設定ファイル（通常は txlogd.conf を使用して名前が付けられます）の ExpFile パラメーターを変更します。
solution: Analytics
title: 対照実験の有効化
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 4%

---

# 対照実験の有効化{#enabling-controlled-experimentation}

対照実験を有効にするには、Web またはアプリケーションサーバーへの管理者アクセス権を持つユーザーが、Sensor がインストールされている Web クラスター内の各 Web またはアプリケーションサーバーの Sensor 設定ファイル（通常は txlogd.conf を使用して名前が付けられます）の ExpFile パラメーターを変更します。

さらに、このファイル内の他の 2 つのパラメーターを変更して、テストツール（ExpCookieURL パラメーター）を実装したり、Web サイトの大きなセクションを再マッピングしたり（ExpPartialMatch パラメーター）できます。 この章では、これらのパラメーターの詳細について説明します。

**txlogd.conf ファイルを編集するには**

管理者アクセス権がある場合は、次の手順を実行します。 管理者アクセス権がない場合は、システムアーキテクトに連絡して変更をリクエストし、次の手順を実行します。

1. 次に移動： [!DNL Sensor] Web クラスター内の web またはアプリケーションサーバー上のインストールフォルダーで、 [!DNL Sensor] がインストールされている。
1. を開きます。 [!DNL Sensor] 設定ファイル ( 通常、 [!DNL txlogd.conf]) をテキストエディターで編集し、 [ExpFile パラメーターの変更](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   ( オプションで [ExpCookieURL パラメーターの変更（オプション）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) および [ExpPartialMatch パラメーターの変更（オプション）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. ファイルを保存して閉じます。
1. Web クラスタ内の Web またはアプリケーションサーバーごとに、以下の手順を繰り返します。 [!DNL Sensor] がインストールされている。
