---
description: センサーは、アクティビティを測定するサーバーと同じコンピューターにインストールします。
title: センサーのインストール
uuid: 8d500fd0-daa0-453b-8284-b3f112a358ce
exl-id: cd5b54bf-301a-41a9-a69c-d9adb314be03
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 2%

---

# センサーのインストール{#installing-sensor}

センサーは、アクティビティを測定するサーバーと同じコンピューターにインストールします。

イベントデータの取り込み元の各サーバーは、[!DNL Sensor]を実行する必要があります。

[!DNL Sensor] は、サポート対象の幅広いWebサーバやアプリケーションサーバや、測定用にタグ付けされたページ、広告、その他のインターネットオブジェクトから情報を取得するために使用される専用のデータ収集サーバにインストールできます。

>[!NOTE]
>
>[!DNL Sensor] は、適切に設定されたweb、アプリケーションまたはデータ収集サーバーのパフォーマンスを低下させません。

Adobeは、Microsoft Windows、AIX、Linux、Solarisなどの一般的なオペレーティングシステム上で動作するAOLServer、Apache、iPlanet、JBoss、Microsoft IIS、Netscape Enterprise、Tomcat、Weblogicなど、Webアプリケーションサーバーのファミリーが増えているのをサポートするように設計しました。 [!DNL Sensor][!DNL Sensor’s] モジュラーアーキテクチャを使用すると、Adobeは必要に応じて、他のアプリケーション用の新しいデータ獲得ロジックを迅速に作成できます。

この章では、Webサーバー/オペレーティングシステムの組み合わせに対して[!DNL Sensor]をインストールする手順について説明します。

[!DNL Sensor]からデータを収集する[!DNL data workbench server]をまだインストールしていない場合は、この章の手順を実行する前にインストールする必要があります。
