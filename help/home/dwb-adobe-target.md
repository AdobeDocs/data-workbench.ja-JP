---
description: Data WorkbenchをAdobe Targetと統合する。 データセグメントのエクスポートとエクスポートファイルの自動入力。
title: Data Workbench と Adobe Target の統合
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Data Workbench と Adobe Target の統合

AdobeData WorkbenchとAdobe Targetの統合が容易になり、データセグメントを書き出し、書き出しファイルを自動的に設定するData Workbench機能が追加されました。

AdobeData Workbenchは、データの共有とレポートの生成を行うために、Adobe Targetとのクローズドループ統合を提供します。 Data Workbench内で、電話、店舗などのチャネルを通じたオフラインコンバージョンを含む、利用可能なすべてのデータを使用して、母集団を意味のあるセグメントに分析できます。

例えば、訪問者がWebサイトで靴を探してもコンバージョンに至らないとします。 訪問者は、次の購入を20%オフするクーポンをダウンロードし、店舗でシャツを購入します。 Data Workbenchを使用すると、そのデータを収集し、そのプロファイルデータをTargetにプッシュして、訪問者がオフラインでシャツを購入したことを示すことができます。 その後、通常は靴をその訪問者に再マーケティングしようとする可能性があるのに、ネクタイを提供するキャンペーンをターゲットに設定できます。

## Adobe TargetとのData Workbenchの設定

1. [!UICONTROL Detail Table]ウィンドウでヘッダーを右クリックします。

   ![](assets/insight-to-tnt.png)

1. **[!UICONTROL New Target Export]**&#x200B;を選択し、メニューの&#x200B;**[!UICONTROL Save As]**&#x200B;コマンドに新しいエクスポートファイルの名前を入力します。

1. 「**[!UICONTROL Save Export File]**」をクリックします。

   エクスポートテンプレートウィンドウが開きます。

   すべてのAdobe Target情報が自動的に入力されます。 セグメントエクスポートに何を配置したかに基づいて、パラメーターリストが作成されます。 完了すると、Data WorkbenchはAdobe Targetサーバーにデータを送信します。

   **注意：** テンプレートファイルは、で設定する必要があり [!UICONTROL Profile Architect]ます。[!UICONTROL Client Name]、[!UICONTROL Domain Postfix]、[!UICONTROL Mbox Host]、および[!UICONTROL Mbox Name]を入力する必要があります。 複数のサイトがある場合は、複数のテンプレートに入力し、サーバーに保存します。 プロファイルマネージャーのテンプレートは`Context\FileNew\Detail Table\Export\Copy`にあります。

   ![](assets/insight-to-tnt1.png)

1. [!UICONTROL mboxPC]クエリパラメーターを指定します。

   Data Workbench属性の名前が[!UICONTROL mboxPC]以外の場合は、適切なクエリパラメーターを編集し、名前を&#x200B;_mboxPC_&#x200B;に変更する必要があります。

   ![](assets/insight-to-tnt2.png)

   エクスポートファイルをサーバーに保存すると、エクスポートが開始されます。 完了すると、[!UICONTROL TnTSend.exe]アプリケーションが起動し、Targetアカウントへのデータの送信が開始されます。

## TargetのData Workbenchの設定

Adobe Targetで次の作業を実行します。

Data WorkbenchがユーザープロファイルをAdobe Targetに渡している。 Targetへの書き出し用にを設定するには、APIを設定して有効にし、書き出し設定ファイル(`export.cfg`)の&#x200B;**[!UICONTROL clientname]**&#x200B;パラメーターと&#x200B;**[!UICONTROL domain postfix]**&#x200B;パラメーターを指定する必要があります。

**[!UICONTROL Oneshot]**&#x200B;という新しいブール型オプションがセグメントエクスポートファイルに追加されました。 このオプションは、新しいプロファイルと共に配布されるテンプレートファイルに含まれます。 [!UICONTROL Oneshot]を&#x200B;_true_&#x200B;に設定した場合、エクスポートが完了すると、`.export`ファイルの名前が`.export.done-TIMESTAMP`に変更され、セグメントが2回以上エクスポートされることはありません。 これは、Adobe Targetにエクスポートする場合に重要です。

**注意：** Data WorkbenchからAdobe Targetへの呼び出しは呼び出しとしてカウントさ [!UICONTROL mbox] れ、送信されるプロファイルごとに1回の呼び出しが必要です。その結果、2つのソリューション間で複数の呼び出しが必要な場合はコストが増加します。

不完全な設定では、ログに次のエラーメッセージが表示されます。

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Adobe TargetのData Workbench

Adobe Target内では、顧客がプロファイルデータを送信するための特別な設定は必要ありません。 通常、ユーザーのプロファイル情報は通常の[!UICONTROL mbox]リクエストで渡され、サーバーは、追加の設定なしに、ターゲットキャンペーンの設定で使用できるプロファイルパラメーターを標準機能として使用します。

Adobe TargetにはData Workbench統合が組み込まれており、スーパーユーザークライアントの詳細ページから有効にできます。 このオプションを有効にすると、Adobe Target内のData Workbenchから共有されたセグメントが表示され、ターゲティングで使用できるようになります。

## ExportIntegration.exeでのHTTPログレポートの設定

[!UICONTROL ExportIntegration.exe]を使用してAdobe Target統合ファイルをエクスポートする場合、[!UICONTROL HTTP.log]に対する長いレポートを減らします。

新しい[!UICONTROL httpLoggingEI.cfg]設定ファイル（`server\Admin\Export\httpLoggingEI.cfg`にあります）を使用すると、[!UICONTROL ExportIntegration.exe]を使用してデータをエクスポートする際に、[!UICONTROL HTTP.log]ファイルに対する詳細ログを減らすことができます。 これにより、詳細な要求/応答のログを停止できます。

詳細ログは既に[!UICONTROL TnTSend.log]ファイルにキャプチャされています。

__ Truesets詳細ログを実行し、Falseを指定する __ と、ファイルに対する詳細ログを [!UICONTROL HTTP.log] 停止します。

False設定の場合、警告メッセージのみが[!UICONTROL HTTP.log]ファイルに送信されます（情報コンテンツは送信されません）。
