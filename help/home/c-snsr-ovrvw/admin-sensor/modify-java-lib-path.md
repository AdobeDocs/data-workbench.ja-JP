---
description: Tomcat Javaライブラリパスにvisual_sciences.dllを追加する手順です。
title: Javaライブラリパスの変更
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Javaライブラリパスの変更{#modify-the-java-library-path}

Tomcat Javaライブラリパスにvisual_sciences.dllを追加する手順です。

1. Windowsサーバーで、Tomcatのインストールディレクトリに移動します。 (Tomcat > bin)
1. binフォルダーで、Tomcat9w.exe(Common Daemon Service Manager)を実行します。

「Java」タブの「Java options」で、次の新しい行を追加します。

```
-Djava.library.path=C:\Sensor directory
```

ここで、C:\Sensor directory is the directory containing the visual_sciences.dllファイル。
