---
description: ワークスペースウィンドウメニュー（ワークスペース内で右クリックしてアクセス）および指標、ディメンション、マップレイヤーをリストするメニューなど、メニューの外観をカスタマイズできます。
solution: Analytics
title: メニューのカスタマイズ
topic: Data workbench
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# メニューのカスタマイズ{#customize-a-menu}

ワークスペースウィンドウメニュー（ワークスペース内で右クリックしてアクセス）および指標、ディメンション、マップレイヤーをリストするメニューなど、メニューの外観をカスタマイズできます。

The hierarchy of any menu mirrors the structure of its directory in the [!DNL Profile Manager]. 例えば、ワークスペースウィンドウメニューは Menu ディレクトリの構造を反映し、指標メニューは Metrics ディレクトリの構造を反映しています。 どのメニューでも、対応するディレクトリには以下の項目を含めることができます。

* **ファイル：**&#x200B;これらのファイルは、対応するメニュー項目をクリックして開けるビジュアライゼーション、凡例、注釈、管理インターフェイス、指標、ディメンション、マップレイヤーを表します。
* **[!DNL order.txt]ファイル：**&#x200B;このファイルでは、メニューに項目が表示される順序を指定します。
* **サブディレクトリ：**&#x200B;各サブディレクトリはサブメニューを表します。サブディレクトリごとに、独自のファイル、サブディレクトリ、[!DNL order.txt] ファイルを含めることができます。

For example, the [!DNL Add Legend] menu contains the menu items Metric, Color, Value, and Confidence, in that order. In comparison, the Menu\Add Legend directory in the [!DNL Profile Manager] contains the files [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw], and [!DNL Value.vw] files in alphabetical order, as well as an [!DNL order.txt] file to control the order of the other files.
