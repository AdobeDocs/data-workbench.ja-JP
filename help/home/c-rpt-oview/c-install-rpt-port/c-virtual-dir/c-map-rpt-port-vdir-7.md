---
description: レポートポータルを仮想ディレクトリ（IIS 7.0以降）にマップする手順です。
solution: Analytics
title: 仮想ディレクトリ（IIS 7.0以降）へのレポートポータルのマッピング
topic: Data workbench
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 仮想ディレクトリ（IIS 7.0以降）へのレポートポータルのマッピング{#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

レポートポータルを仮想ディレクトリ（IIS 7.0以降）にマップする手順です。

現在、ほとんどの管理サービスクライアントには、Windows Server 2008オペレーティングシステムとIIS 7.0以降のWebサーバーを持つサーバーが存在します。

## 前提条件 {#section-7b1cff24fc4f4c8591540b78de686f2f}

* ASPとコンポーネントがIIS 7.0 [!DNL ASP.Net] 以降用にインストールされていることを確認します。
* IIS Webユーザーがファイルにアクセスできる [!DNL Modify] ことを確認してく [!DNL E:\Portal\data\users.mdb] ださい。 ファイルを右クリックし、の下のタブに移 **[!UICONTROL users.mdb]** 動すると、 [!DNL Properties]変更でき [!DNL Security] ます。 IIS Webユーザが一覧に表示されない場合、またはIIS Webユーザを一覧に追加する権限がない場合は、グループにアクセス権を与え [!DNL Users] るだけで [!DNL Modify] す。

* を実行するために使用されているユーザーアカウントが、[!DNL C:\Windows\Temp\] [!DNL Application Pools] フォル [!DNL Modify] ダーおよび[!DNL [!DNL E:\Portal\data\users.mdb] ]フォルダーにもアクセスできることを確認します。

## インストール手順 {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. がインストールされてい [!DNL Report Portal] るコンピュータで、次を起動しま [!DNL IIS Manager]す。

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. 右クリックし、を **[!UICONTROL Default Web Site]** 選択しま **[!UICONTROL Add Virtual Directory]**&#x200B;す。

1. エイリアスの場合は、 Portalと入力します。
1. 物理パスに対して、と入力しま [!DNL E:\Portal\PortalASP]す。
1. クリック **[!UICONTROL OK]**.

   作成した仮想ディレクトリがに表示されま [!DNL Default Web Site]す。

1. 作成した仮想ディレクトリの下に、次の仮想ディレクトリを追加します。

   | このエイリアスを作成… | この物理リソース |
   |---|---|
   | コア | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 画像 | [!DNL E:\Portal\PortalFiles\Images] |
   | 出力 | レポートセットの出力を保存する [!DNL Report Server] ディレクトリの物理的な場所。 出力フォルダーは任意の場所に配置でき、任意の名前を付けることができます。 各レポートセットのサブフォルダが含まれます。 を削除できますが、 [!DNL E:\Portal\PortalFiles\Output]出力ファイルの [!DNL profiles.xml] 物理的な場所に移動することはできます。 |

1. 完了したら、IISで4つの新しい仮想ディレクトリが表示されることを確認します。 ディレクトリ構造に、（ポータルと同じ名前の）1つの親フォルダーと4つのサブフォルダーが含まれていることを確認します。
1. をクリック **[!UICONTROL Application Pools]**&#x200B;し、次 **[!UICONTROL DefaultAppPool]** に（ポータルで設定したものと仮定します）をクリックします。

1. 「32ビットア **[!UICONTROL Advanced Settings]** プリケーションを有効にする」で「True」をクリックします。
1. を機能させるに [!DNL Portal] は、アプリケーションに変換する必要があります。 仮想ディレクトリを設定したら、ポータル仮想ディレクトリを右クリックし、を選択しま **[!UICONTROL Convert to Application]**&#x200B;す。

## その他のヒントとテクニック {#section-ff84ab3f66c94620a6a11f0e60471d44}

* は、Softdocsの>からダウ [!DNL Portal] ンロードで **[!UICONTROL Softdocs]** きます **[!UICONTROL Report Portal]**。 は、単にをダウンロードするだけです [!DNL ReportPortal-Release-1-0-0-7.zip]。

* を削除できるように、こ [!DNL ReportPortalSetup.xml]れらは不要になりました。
* 標準化のため、このzipファイルの内容をに配置します [!DNL E:\Portal]。
* SMTPサーバーを特定する管理サービスクライアントの場合は、ここを参照します。
* NetOpsと共にリクエストを送信し、レポートサーバのIISのドメイン名のエントリをよりわかりやすいものに変更します。例えば、ポータ [!DNL reports.clientname.insight.omniture.com]ルのURL全体を次のように変更できま [!DNL http://reports.clientname.insight.omniture.com/Portal]す。 この変更を [!DNL email.asa] 行った後、ファイルを設定します。

