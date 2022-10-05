---
description: Tomcat java ライブラリパスに visual_sciences.dll を追加する手順。
title: Java ライブラリパスの変更
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
exl-id: bd853d95-3f44-4860-9965-c3210ec4adcf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 12%

---

# Java ライブラリパスの変更{#modify-the-java-library-path}

{{eol}}

Tomcat java ライブラリパスに visual_sciences.dll を追加する手順。

1. Windows サーバーで、Tomcat のインストールディレクトリに移動します。 (Tomcat > bin)
1. bin フォルダーで、Tomcat9w.exe（共通のデーモンサービスマネージャー）を実行します。

「Java」タブの「Java オプション」で、新しい行を追加します。

```
-Djava.library.path=C:\Sensor directory
```

ここで、C:\Sensor directory is the directory containing the visual_sciences.dllファイルを指定します。
