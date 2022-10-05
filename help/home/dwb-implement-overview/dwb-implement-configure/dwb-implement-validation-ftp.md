---
description: これは、内部および外部 FTP の設定を検証するために必要な最小限の手順を説明するクイックガイドです。
title: 内部および外部 FTP サーバーの検証
uuid: bc381c1d-df27-4009-920b-1a804b36c204
exl-id: 8eecfda7-ffa0-458c-a518-434758344bfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 9%

---

# 内部および外部 FTP サーバーの検証{#validation-of-internal-and-external-ftp-servers}

{{eol}}

これは、内部および外部 FTP の設定を検証するために必要な最小限の手順を説明するクイックガイドです。

内部 FTP は、Adobe内部のコンサルタントやアーキテクトがファイルのアップロードまたはダウンロードのために FTP サイトに接続する必要がある場合に使用します。外部 FTP は、主にユーザーが必要なデータファイルをアップロードする際に使用します。

FTP サーバーの設定について詳しくは、 [ファイル転送プロトコル](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-overview.html?lang=ja).

## 検証手順 — 外部 FTP {#section-24428111b5c542ce81a765cd63424b97}

1. コマンドプロンプトを開きます。 （Windows+R で cmd と入力）
1. ftp と入力 `<ftp server>`
1. ユーザー名とパスワードを入力します。 ![](assets/dwb_impl_ftp1.png)

1. 一部のファイルを移動できる場所からローカルディレクトリを変更します。 次のコマンドを使用します。

[!DNL ftp> lcd C:\Users\andixit\Desktop]

ローカルディレクトリを今すぐ [!DNL C:\Users\andixit\Desktop].

1. ローカルからリモートの場所にファイルをコピーします。 ![](assets/dwb_impl_ftp2.png)

1. リモートサーバーからログアウトします。 （以下のコマンドを使用）

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>FTP を検証する別の方法は、Filezilla を使用することです。 ホスト名、ユーザー名、パスワード、ポートを入力します。 パネルの右側はリモートサイトで、左側はローカルサイトです。 FTP を検証するには、ローカルからリモートサイトおよび v.v にファイルをドラッグ&amp;ドロップします。

![](assets/dwb_impl_ftp3.png)

## 検証手順 — 内部 FTP {#section-b1f7a789ad6848cf9027f7953d81066e}

上記の手順に従って、任意のAdobeサーバーからの内部 ftp を検証できます。
