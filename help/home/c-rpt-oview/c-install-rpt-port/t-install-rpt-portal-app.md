---
description: レポートポータルは、一連のアプリケーションサーバーページ(ASP)とサポートファイルで構成されています。
title: Report Portal アプリケーションファイルのインストール
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Report Portal アプリケーションファイルのインストール{#install-the-report-portal-application-files}

レポートポータルは、一連のアプリケーションサーバーページ(ASP)とサポートファイルで構成されています。

[!DNL Report Portal]をインストールするには、Adobeから受け取った配布ファイルからこれらのファイルを抽出し、Microsoft IISが実行されているマシンにインストールする必要があります。

**アプ [!DNL Report Portal] リケーションファイルをインストールするには**

1. まだインストールを行っていない場合は、AdobeのFTPサイトから[!DNL Report Portal]用のインストールパッケージ（.zipファイル）をダウンロードしてください。
1. IISが実行されているコンピューター上で、インストールパッケージ内のファイルを任意の場所に展開します。 この手順では、VSVirtualPortalNameフォルダーに次のサブフォルダーとファイルをインストールします。

   | フォルダまたはファイル | 説明 |
   |---|---|
   | [!DNL \data\users.mdb] | 許可された[!DNL Report Portal]ユーザーのリストを含むデータベース。 |
   | [!DNL \PortalASP\] | [!DNL Report Portal]を構成するASPファイルを含むフォルダー。 |
   | [!DNL \PortalFiles\] | [!DNL Report Portal]で使用されるサポートファイルを含む5つのサブフォルダー(Core、CSS、HTC、Images、Output)を含むフォルダーです。 |
   | [!DNL ReportPortalSetup.xml] | [!DNL Report Portal]に関連付けられた仮想ディレクトリを定義するために使用する構成ファイル（IIS 6.0でのみ使用）。 |

   ディレクトリは次の例のようになります。

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >ディレクトリの名前は、この例に示す名前とは異なる場合があります。

1. VSVirtualPortalName（または他の名前）フォルダーの名前を、[!DNL Report Portal]のルート仮想ディレクトリとして使用する（以下&#x200B;*PortalName*&#x200B;と呼ぶ）名前に変更します。 仮想ディレクトリの詳細については、次のセクションを参照してください。
