---
description: 仮想ディレクトリ（IIS 7.0 以降）に Report Portal をマッピングする手順。
title: 仮想ディレクトリ（IIS 7.0 以降）への Report Portal のマッピング
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---

# 仮想ディレクトリ（IIS 7.0 以降）への Report Portal のマッピング{#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

仮想ディレクトリ（IIS 7.0 以降）に Report Portal をマッピングする手順。

現在、ほとんどの Managed Service クライアントには、Windows Server 2008 オペレーティングシステムと IIS 7.0 以降の Web サーバーを使用するサーバーがあります。

## 前提条件  {#section-7b1cff24fc4f4c8591540b78de686f2f}

* ASP および [!DNL ASP.Net] コンポーネントが IIS 7.0 以降用にインストールされていることを確認します。
* IIS Web ユーザーが [!DNL Modify] ファイルに対して [!DNL E:\Portal\data\users.mdb] アクセス権を持っていることを確認します。 **[!UICONTROL users.mdb]** ファイルを右クリックし、[!DNL Properties] の下の [!DNL Security] タブに移動して、この値を変更できます。 IIS Web ユーザーが表示されない場合や、IIS Web ユーザーをリストに追加する機能がない場合は、[!DNL Users] グループに [!DNL Modify] アクセス権を付与します。

* [!DNL Application Pools] の実行に使用されているユーザーアカウントにも、[!DNL E:\Portal\data\users.mdb] と  [!DNL C:\Windows\Temp\]  フォルダーへの [!DNL Modify] アクセス権があることを確認します。

## インストール手順 {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. [!DNL Report Portal] がインストールされているマシンで、[!DNL IIS Manager] を起動します。

   **[!UICONTROL Start]** >  **[!UICONTROL Administrative Tools]** >  **[!UICONTROL Internet Information Services (IIS) Manager]**。

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. **[!UICONTROL Default Web Site]** を右クリックし、**[!UICONTROL Add Virtual Directory]** を選択します。

1. エイリアスの場合は、 Portal と入力します。
1. 物理パスに [!DNL E:\Portal\PortalASP] と入力します。
1. 「**[!UICONTROL OK]**」をクリックします。

   作成した仮想ディレクトリが [!DNL Default Web Site] の下に表示されます。

1. 作成した仮想ディレクトリの下に、次の仮想ディレクトリを追加します。

   | エイリアスの作成… | この物理リソースの場合 |
   |---|---|
   | コア | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 画像 | [!DNL E:\Portal\PortalFiles\Images] |
   | 出力 | [!DNL Report Server] がレポートセットの出力を保存するディレクトリの物理的な場所。 出力フォルダーは任意の場所に配置し、任意の名前を付けることができます。 各レポートセットに対応するサブフォルダーが含まれます。 [!DNL E:\Portal\PortalFiles\Output] は削除できますが、[!DNL profiles.xml] を Output ファイルの物理的な場所に移動します。 |

1. 完了したら、IIS に 4 つの新しい仮想ディレクトリが表示されることを確認します。 ディレクトリ構造に、（ポータルと同じ名前の）1 つの親フォルダーと、4 つのサブフォルダーがあることを確認します。
1. **[!UICONTROL Application Pools]** をクリックし、**[!UICONTROL DefaultAppPool]**（ポータルで設定したもの）をクリックします。

1. **[!UICONTROL Advanced Settings]** をクリックし、「Enable 32-Bit Applications」で「True」を選択します。
1. [!DNL Portal] を機能させるには、アプリケーションに変換する必要があります。 仮想ディレクトリを設定した後、ポータル仮想ディレクトリを右クリックし、**[!UICONTROL Convert to Application]** を選択します。

## その他のヒントとテクニック {#section-ff84ab3f66c94620a6a11f0e60471d44}

* [!DNL Portal] は、Softdocs の **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]** からダウンロードできます。 [!DNL ReportPortal-Release-1-0-0-7.zip] をダウンロードするだけです。

* [!DNL ReportPortalSetup.xml] は不要になったので、削除できます。
* 標準化のために、この zip ファイルの内容を [!DNL E:\Portal] に配置します。
* SMTP サーバーを特定する管理対象サービスクライアントの場合は、ここを参照してください。
* NetOps とのリクエストを送信し、IIS のレポートサーバーのドメイン名エントリをよりわかりやすいもの（例：[!DNL reports.clientname.insight.omniture.com]）に変更して、ポータル全体の URL が [!DNL https://reports.clientname.insight.omniture.com/Portal] になるようにします。 この変更を適用したら、[!DNL email.asa] ファイルを設定します。
