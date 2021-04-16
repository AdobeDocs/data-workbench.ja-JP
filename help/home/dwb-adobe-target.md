---
description: Data WorkbenchとAdobe Targetを統合。 データセグメントを書き出し、書き出しファイルを自動的に埋め込みます。
title: Data Workbench と Adobe Target の統合
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Data Workbench と Adobe Target の統合

データセグメントの書き出しと書き出しファイルの自動入力のData Workbench機能により、AdobeData WorkbenchのAdobe Targetとの統合が容易になりました。

AdobeData Workbenchは、データの共有とレポートの生成を行うために、Adobe Targetとのクローズドループ統合を提供します。 Data Workbench内では、電話、店舗などのチャネルを介したオフラインコンバージョンを含む、利用可能なすべてのデータを使用して、訪問者を意味のあるセグメントに分類できます。

例えば、Webサイト上で訪問者が靴を探してもコンバージョンが行われないとします。 訪問者は、次の購入時に20%引きのクーポンをダウンロードし、店頭でシャツを購入します。 Data Workbenchを使用して、そのデータを収集し、そのプロファイルデータをターゲットに戻して、訪問者がオフラインでシャツを購入したことを示すことができます。 その訪問者に靴を売り込もうとすると、通常はターゲットが靴の再売り込みを試みても、ネクタイを提供するキャンペーンをターゲットできます。

## Adobe TargetとのData Workbenchの設定

1. [!UICONTROL Detail Table]ウィンドウのヘッダーを右クリックします。

   ![](assets/insight-to-tnt.png)

1. **[!UICONTROL New Target Export]**&#x200B;を選択し、メニューの&#x200B;**[!UICONTROL Save As]**&#x200B;コマンドの下に新しいエクスポートファイルの名前を入力します。

1. 「**[!UICONTROL Save Export File]**」をクリックします。

   書き出しテンプレートウィンドウが開きます。

   すべてのAdobe Target情報が自動的に入力されます。 セグメントエクスポートに入力した内容に基づいて、パラメーターのリストが構築されます。 完了すると、Data WorkbenchはデータをAdobe Targetサーバに送信します。

   **注意：テンプレ** ートファイルは、で設定する必要があり [!UICONTROL Profile Architect]ます。[!UICONTROL Client Name]、[!UICONTROL Domain Postfix]、[!UICONTROL Mbox Host]、および[!UICONTROL Mbox Name]を入力する必要があります。 複数のサイトがある場合は、複数のテンプレートに入力し、サーバーに保存します。 プロファイルマネージャのテンプレートは`Context\FileNew\Detail Table\Export\Copy`にあります。

   ![](assets/insight-to-tnt1.png)

1. [!UICONTROL mboxPC]クエリパラメーターを指定します。

   Data Workbench属性の名前が[!UICONTROL mboxPC]以外の値の場合は、適切なクエリパラメーターを編集し、_mboxPC_&#x200B;に名前を変更する必要があります。

   ![](assets/insight-to-tnt2.png)

   エクスポートファイルをサーバーに保存すると、エクスポートが開始されます。 完了すると、[!UICONTROL TnTSend.exe]アプリケーションが起動し、ターゲットアカウントへのデータの送信が開始されます。

## ターゲット用のData Workbenchの設定

Adobe Targetで次のタスクを実行します。

Data WorkbenchがユーザープロファイルをAdobe Targetに渡しています。 ターゲットへの書き出しを設定するには、そのAPIを設定して有効にし、書き出し設定ファイルの&#x200B;**[!UICONTROL clientname]**&#x200B;パラメーターと&#x200B;**[!UICONTROL domain postfix]**&#x200B;パラメーター(`export.cfg`)を指定する必要があります。

セグメントエクスポートファイルに、**[!UICONTROL Oneshot]**&#x200B;という新しいブール値オプションが追加されました。 このオプションは、新しいプロファイルと共に配布されるテンプレートファイルに含まれます。 [!UICONTROL Oneshot]を&#x200B;_true_&#x200B;に設定した場合、`.export`ファイルは、エクスポートの完了後に`.export.done-TIMESTAMP`に名前が変更され、セグメントが複数回エクスポートされなくなります。 これは、Adobe Targetに書き出す際に重要です。

**注意：Data WorkbenchからAdobe Target** への呼び出しは、 [!UICONTROL mbox] 呼び出しとしてカウントされ、送信されたプロファイルごとに1回の呼び出しが必要となります。その結果、2つのソリューション間で複数の呼び出しが必要な場合は、コストが増加します。

設定が不完全なとき、ログに次のエラーメッセージが表示されます。

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Data Workbench用のAdobe Targetの設定

Adobe Target内では、お客様がプロファイルデータを送信する際に特別な設定は必要ありません。 通常、ユーザーのプロファイル情報は通常の[!UICONTROL mbox]リクエストに渡され、サーバーは、追加の設定なしに、ターゲットキャンペーンの設定に対して標準機能としてプロファイルパラメーターを使用できるようにします。

Adobe TargetにはData Workbench統合が組み込まれており、「スーパーユーザーのクライアントの詳細」ページから有効にできます。 このオプションを有効にすると、Adobe Target内のData Workbenchから共有されるセグメントが表面化され、ターゲティングで使用できるようになります。

## ExportIntegration.exeにHTTPログレポートを設定します

[!UICONTROL ExportIntegration.exe]を使用してAdobe Target統合ファイルをエクスポートする場合、長いレポートを[!UICONTROL HTTP.log]に減らします。

新しい[!UICONTROL httpLoggingEI.cfg]設定ファイル（`server\Admin\Export\httpLoggingEI.cfg`にあります）を使用すると、[!UICONTROL ExportIntegration.exe]を使用してデータを書き出す際に、[!UICONTROL HTTP.log]ファイルに対する詳細ログを減らすことができます。 これにより、詳細な要求/応答のログ記録を停止できます。

詳細ログは既に[!UICONTROL TnTSend.log]ファイルにキャプチャされています。

__ Trueset詳細ログを記録し、Falseを __ 指定すると、 [!UICONTROL HTTP.log] ファイルへの詳細ログの記録を停止します。

False設定の場合、警告メッセージのみが[!UICONTROL HTTP.log]ファイルに送信されます（情報の内容は送信されません）。
