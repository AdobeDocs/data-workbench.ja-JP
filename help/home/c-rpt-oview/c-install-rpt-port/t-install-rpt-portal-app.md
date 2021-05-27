---
description: Report Portalは、一連のアプリケーションサーバーページ(ASP)とサポートファイルで構成されています。
title: Report Portal アプリケーションファイルのインストール
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Report Portal アプリケーションファイルのインストール{#install-the-report-portal-application-files}

Report Portalは、一連のアプリケーションサーバーページ(ASP)とサポートファイルで構成されています。

[!DNL Report Portal]をインストールするには、Adobeから受け取った配布ファイルからこれらのファイルを抽出し、Microsoft IISが実行されているマシンにインストールする必要があります。

**アプリケーションファイルをイ [!DNL Report Portal] ンストールするには**

1. まだの場合は、AdobeのFTPサイトから[!DNL Report Portal]のインストールパッケージ（.zipファイル）をダウンロードします。
1. IISを実行しているマシン上で、インストールパッケージ内のファイルを任意の場所に展開します。 この手順では、VSVirtualPortalNameフォルダーに次のサブフォルダーとファイルをインストールします。

   | フォルダーまたはファイル | 説明 |
   |---|---|
   | [!DNL \data\users.mdb] | 許可された[!DNL Report Portal]ユーザーのリストを含むデータベース。 |
   | [!DNL \PortalASP\] | [!DNL Report Portal]を構成するASPファイルを含むフォルダー。 |
   | [!DNL \PortalFiles\] | [!DNL Report Portal]で使用されるサポートファイルを格納する5つのサブフォルダー(Core、CSS、HTC、Images、Output)を含むフォルダー。 |
   | [!DNL ReportPortalSetup.xml] | [!DNL Report Portal]に関連付けられた仮想ディレクトリを定義するために使用する構成ファイル（IIS 6.0でのみ使用）。 |

   ディレクトリは次の例のようになります。

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >ディレクトリの名前は、例に示す名前とは異なる場合があります。

1. VSVirtualPortalName（または他の名前）フォルダーの名前を、[!DNL Report Portal]のルート仮想ディレクトリ（以下&#x200B;*PortalName*&#x200B;と呼びます）として使用する名前に変更します。 仮想ディレクトリの詳細については、次の節を参照してください。
