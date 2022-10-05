---
description: Report Portal を仮想ディレクトリ（IIS 7.0 以降）にマッピングする手順です。
title: 仮想ディレクトリ（IIS 7.0 以降）への Report Portal のマッピング
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 5%

---

# 仮想ディレクトリ（IIS 7.0 以降）への Report Portal のマッピング{#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

{{eol}}

Report Portal を仮想ディレクトリ（IIS 7.0 以降）にマッピングする手順です。

現在、ほとんどの Managed Service クライアントには、Windows Server 2008 オペレーティングシステムと IIS 7.0 以降の Web サーバーを持つサーバーがあります。

## 前提条件 {#section-7b1cff24fc4f4c8591540b78de686f2f}

* ASP と [!DNL ASP.Net] コンポーネントは、IIS 7.0 以降用にインストールされています。
* IIS Web ユーザーが [!DNL Modify] へのアクセス [!DNL E:\Portal\data\users.mdb] ファイル。 これは、 **[!UICONTROL users.mdb]** ファイルと [!DNL Properties]、 [!DNL Security] タブをクリックします。 IIS Web ユーザーが表示されない場合や、IIS Web ユーザーをリストに追加する機能がない場合は、 [!DNL Users] グループ化 [!DNL Modify] にアクセスします。

* 実行に使用されているユーザーアカウントを確認します。 [!DNL Application Pools] 次を含む [!DNL Modify] へのアクセス [!DNL E:\Portal\data\users.mdb] および [!DNL C:\Windows\Temp\] フォルダーに保存されている必要があります。

## インストール手順 {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. 次のマシンで [!DNL Report Portal] がインストールされている場合は、 [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. 右クリック **[!UICONTROL Default Web Site]** を選択し、 **[!UICONTROL Add Virtual Directory]**.

1. エイリアスの場合は、 Portal と入力します。
1. 物理パスに、 [!DNL E:\Portal\PortalASP].
1. 「**[!UICONTROL OK]**」をクリックします。

   作成した仮想ディレクトリが、 [!DNL Default Web Site].

1. 作成した仮想ディレクトリの下に、次の仮想ディレクトリを追加します。

   | このエイリアスを作成… | この物理リソースの場合 |
   |---|---|
   | コア | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 画像 | [!DNL E:\Portal\PortalFiles\Images] |
   | 出力 | ディレクトリの物理的な場所 [!DNL Report Server] レポートセットの出力を保存します。 出力フォルダーは任意の場所に配置し、任意の名前を付けることができます。 各レポートセットにはサブフォルダーが含まれます。 次の項目を削除できます。 [!DNL E:\Portal\PortalFiles\Output]をクリックし、 [!DNL profiles.xml] を Output ファイルの物理的な場所に追加します。 |

1. 終了したら、IIS に 4 つの新しい仮想ディレクトリが表示されることを確認します。 ディレクトリ構造に、1 つの親フォルダー（ポータルと同じ名前）と 4 つのサブフォルダーがあることを確認します。
1. クリック **[!UICONTROL Application Pools]**&#x200B;を、 **[!UICONTROL DefaultAppPool]** （これがポータルで設定したものであると仮定）。

1. クリック **[!UICONTROL Advanced Settings]** 「32 ビットアプリケーションを有効にする」で「True」を選択します。
1. 次の手順で [!DNL Portal] 機能させるには、アプリケーションに変換する必要があります。 仮想ディレクトリを設定した後、ポータル仮想ディレクトリを右クリックし、「 」を選択します。 **[!UICONTROL Convert to Application]**.

## その他のヒントとテクニック {#section-ff84ab3f66c94620a6a11f0e60471d44}

* 次をダウンロード： [!DNL Portal] Softdocs の **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. 次の URL をダウンロードするだけで、 [!DNL ReportPortal-Release-1-0-0-7.zip].

* 不要になった [!DNL ReportPortalSetup.xml]削除できます。
* 標準化のために、この zip ファイルの内容を [!DNL E:\Portal].
* SMTP サーバーを決定する Managed Services クライアントの場合は、ここを参照してください。
* NetOps とのリクエストを設定し、IIS でのレポートサーバーのドメイン名のエントリをよりわかりやすいものに変更します。例： [!DNL reports.clientname.insight.omniture.com]に設定されている場合、ポータルの URL 全体は [!DNL https://reports.clientname.insight.omniture.com/Portal]. の設定 [!DNL email.asa] ファイルを作成します。
