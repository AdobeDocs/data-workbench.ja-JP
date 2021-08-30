---
description: これは、内部および外部FTPの設定を検証するために必要な最小限の手順を説明するクイックガイドです。
title: 内部および外部 FTP サーバーの検証
uuid: bc381c1d-df27-4009-920b-1a804b36c204
exl-id: 8eecfda7-ffa0-458c-a518-434758344bfe
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 9%

---

# 内部および外部 FTP サーバーの検証{#validation-of-internal-and-external-ftp-servers}

これは、内部および外部FTPの設定を検証するために必要な最小限の手順を説明するクイックガイドです。

内部FTPは、Adobe内のコンサルタント/アーキテクトがファイルのアップロードまたはダウンロード用にFTPサイトに接続する必要がある場合に使用されます。一方、外部FTPは主にユーザーが必要なデータファイルをアップロードします。

FTPサーバーの設定について詳しくは、[ファイル転送プロトコル](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-overview.html?lang=ja)を参照してください。

## 検証手順 — 外部FTP {#section-24428111b5c542ce81a765cd63424b97}

1. コマンドプロンプトを開きます。 （Windows+Rを押して「cmd」と入力）
1. ftp `<ftp server>`と入力します。
1. ユーザー名とパスワードを入力します。![](assets/dwb_impl_ftp1.png)

1. 一部のファイルを移動できる場所からローカルディレクトリを変更します。 次のコマンドを使用します。

[!DNL ftp> lcd C:\Users\andixit\Desktop]

ローカルディレクトリが[!DNL C:\Users\andixit\Desktop]になりました。

1. ローカルからリモートの場所にファイルをコピーします。![](assets/dwb_impl_ftp2.png)

1. リモートサーバーからログアウトします。 （次のコマンドを使用）

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>FTPを検証するもう1つの方法は、Filezillaを使用することです。 ホスト名、ユーザー名、パスワード、ポートを入力します。 パネルの右側はリモートサイトで、左側はローカルサイトです。 ローカルサイトからリモートサイトおよびv.vへのFTPドラッグ&amp;ドロップファイルを検証するには

![](assets/dwb_impl_ftp3.png)

## 検証手順 — 内部FTP {#section-b1f7a789ad6848cf9027f7953d81066e}

上記の手順に従って、任意のAdobeサーバーからの内部ftpを検証できます。
