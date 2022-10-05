---
description: Report Portal は、一連のアプリケーションサーバーページ (ASP) とサポートファイルで構成されています。
title: Report Portal アプリケーションファイルのインストール
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Report Portal アプリケーションファイルのインストール{#install-the-report-portal-application-files}

{{eol}}

Report Portal は、一連のアプリケーションサーバーページ (ASP) とサポートファイルで構成されています。

をインストールするには、以下を実行します。 [!DNL Report Portal]を使用する場合は、Adobeから受け取った配布ファイルからこれらのファイルを抽出し、Microsoft IIS が実行されているマシンにインストールする必要があります。

**をインストールするには、以下を実行します。 [!DNL Report Portal] アプリケーションファイル**

1. まだの場合は、 [!DNL Report Portal] をAdobeFTP サイトから取得します。
1. IIS が実行されているマシン上で、インストールパッケージ内のファイルを任意の場所に展開します。 この手順では、次のサブフォルダとファイルを VSVirtualPortalName フォルダにインストールします。

   | フォルダーまたはファイル | 説明 |
   |---|---|
   | [!DNL \data\users.mdb] | 認証済みのリストを含むデータベース [!DNL Report Portal] ユーザー。 |
   | [!DNL \PortalASP\] | を構成する ASP ファイルを含むフォルダー [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | で使用されるサポートファイルが格納される 5 つのサブフォルダー (Core、CSS、HTC、Images、Output) が格納されるフォルダー [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | に関連付けられた仮想ディレクトリを定義するために使用する構成ファイル [!DNL Report Portal] （IIS 6.0 でのみ使用） |

   ディレクトリは次の例のようになります。

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >ディレクトリの名前は、例で示す名前とは異なる場合があります。

1. VSVirtualPortalName（または他の名前）フォルダの名前を、ユーザのルート仮想ディレクトリとして使用するフォルダに変更します。 [!DNL Report Portal] 以下、 *PortalName*) をクリックします。 仮想ディレクトリの詳細については、次の節を参照してください。
