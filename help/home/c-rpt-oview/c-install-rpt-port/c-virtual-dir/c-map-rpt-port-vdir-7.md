---
description: レポートポータルを仮想ディレクトリ（IIS 7.0以降）にマップする手順です。
title: 仮想ディレクトリ（IIS 7.0 以降）への Report Portal のマッピング
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---

# 仮想ディレクトリ（IIS 7.0 以降）への Report Portal のマッピング{#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

レポートポータルを仮想ディレクトリ（IIS 7.0以降）にマップする手順です。

現在、ほとんどの管理対象サービスクライアントには、Windows Server 2008オペレーティングシステムとIIS 7.0以上のWebサーバーを持つサーバーが存在します。

## 前提条件 {#section-7b1cff24fc4f4c8591540b78de686f2f}

* ASPおよび[!DNL ASP.Net]コンポーネントがIIS 7.0以降用にインストールされていることを確認します。
* IIS Webユーザーが[!DNL E:\Portal\data\users.mdb]ファイルに対して[!DNL Modify]アクセス権を持っていることを確認してください。 **[!UICONTROL users.mdb]**&#x200B;ファイルを右クリックし、[!DNL Properties]の下の[!DNL Security]タブに移動して変更できます。 IIS Webユーザーが一覧に表示されない場合、またはIIS Webユーザーをリストに追加する機能がない場合は、[!DNL Users]グループに[!DNL Modify]アクセス権を与えるだけです。

* [!DNL Application Pools]の実行に使用されているユーザーアカウントが[!DNL E:\Portal\data\users.mdb]と [!DNL C:\Windows\Temp\] フォルダーへの[!DNL Modify]アクセス権も持っていることを確認してください。

## インストール手順{#section-2a6476a221fa43dfa91866c0d41f82e5}

1. [!DNL Report Portal]がインストールされているマシン上で、[!DNL IIS Manager]を開始します。

   **[!UICONTROL Start]** >  **[!UICONTROL Administrative Tools]** >  **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. **[!UICONTROL Default Web Site]**&#x200B;を右クリックし、**[!UICONTROL Add Virtual Directory]**&#x200B;を選択します。

1. エイリアスの場合は、Portalと入力します。
1. 物理パスには[!DNL E:\Portal\PortalASP]と入力します。
1. 「**[!UICONTROL OK]**」をクリックします。

   作成した仮想ディレクトリが[!DNL Default Web Site]の下に表示されます。

1. 先ほど作成した仮想ディレクトリの下にある追加次の仮想ディレクトリ。

   | このエイリアスを作成… | この物理リソース |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | 画像 | [!DNL E:\Portal\PortalFiles\Images] |
   | 出力 | [!DNL Report Server]がレポートセットの出力を保存するディレクトリの物理的な場所。 出力フォルダーは任意の場所に配置でき、任意の名前を付けることができます。 各レポートセット用のサブフォルダーが含まれます。 [!DNL E:\Portal\PortalFiles\Output]は削除できますが、[!DNL profiles.xml]は出力ファイルの物理的な場所に移動します。 |

1. 完了したら、IISに4つの新しい仮想ディレクトリが表示されることを確認します。 ディレクトリ構造に、（ポータルと同じ名前の）1つの親フォルダーと4つのサブフォルダーがあることを確認します。
1. **[!UICONTROL Application Pools]**&#x200B;をクリックし、次に&#x200B;**[!UICONTROL DefaultAppPool]**&#x200B;をクリックします（これがポータルで設定したものと仮定します）。

1. **[!UICONTROL Advanced Settings]**&#x200B;をクリックし、「32-Bit Applicationsを有効にする」で「True」を選択します。
1. [!DNL Portal]を動作させるには、それをアプリケーションに変換する必要があります。 仮想ディレクトリを設定した後、ポータル仮想ディレクトリを右クリックし、**[!UICONTROL Convert to Application]**&#x200B;を選択します。

## その他のヒントとテクニック{#section-ff84ab3f66c94620a6a11f0e60471d44}

* [!DNL Portal]は、**[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**&#x200B;の下のSoftdocsからダウンロードできます。 [!DNL ReportPortal-Release-1-0-0-7.zip]はダウンロードするだけです。

* [!DNL ReportPortalSetup.xml]は不要になったので、削除できます。
* 標準化のため、このzipファイルの内容を[!DNL E:\Portal]に配置します。
* SMTPサーバーを特定するには、ここを参照します。
* NetOpsにリクエストを入力して、IISのレポートサーバのドメイン名のエントリをよりわかりやすい（例：[!DNL reports.clientname.insight.omniture.com]）に変更し、ポータル全体のURLを[!DNL http://reports.clientname.insight.omniture.com/Portal]にします。 この変更が行われたら、[!DNL email.asa]ファイルを設定します。
