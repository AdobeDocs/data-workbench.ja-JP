---
description: レポートポータルは、一連のアプリケーションサーバーページ(ASP)とサポートファイルで構成されています。
solution: Analytics
title: レポートポータルアプリケーションファイルのインストール
topic: Data workbench
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# レポートポータルアプリケーションファイルのインストール{#install-the-report-portal-application-files}

レポートポータルは、一連のアプリケーションサーバーページ(ASP)とサポートファイルで構成されています。

をインストールす [!DNL Report Portal]るには、アドビから受け取った配布ファイルからこれらのファイルを抽出し、Microsoft IISが実行されているマシンにインストールする必要があります。

**アプリケーションファイルをイ[!DNL Report Portal]ンストールするには**

1. まだインストールパッケージ（.zipファイル）をダウンロードしていない場合は、アドビのFTPサ [!DNL Report Portal] イトからをダウンロードします。
1. IISが実行されているコンピューター上で、インストールパッケージ内のファイルを任意の場所に展開します。 この手順では、VSVirtualPortalNameフォルダーに次のサブフォルダーとファイルをインストールします。

   | フォルダまたはファイル | 説明 |
   |---|---|
   | [!DNL \data\users.mdb] | 許可されたユーザーのリストを含むデータベ [!DNL Report Portal] ースです。 |
   | [!DNL \PortalASP\] | 構成するASPファイルを含むフォルダーで [!DNL Report Portal]す。 |
   | [!DNL \PortalFiles\] | で使用されるサポートファイルを含む5つのサブフォルダー（Core、CSS、HTC、ImagesおよびOutput）を含むフォルダーで [!DNL Report Portal]す。 |
   | [!DNL ReportPortalSetup.xml] | に関連付けられた仮想ディレクトリを定義するために使用する構 [!DNL Report Portal] 成ファイル（IIS 6.0でのみ使用）。 |

   ディレクトリは次の例のようになります。

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >ディレクトリの名前は、例に示した名前と異なる場合があります。

1. VSVirtualPortalName（または他の名前）フォルダの名前を、ユーザのルート仮想ディレクトリ(以下PortalName [!DNL Report Portal] と呼びます **)として使用する名前に変更します。 仮想ディレクトリの詳細については、次のセクションを参照してください。
