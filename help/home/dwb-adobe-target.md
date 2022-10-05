---
description: Data WorkbenchをAdobe Targetと統合します。 データセグメントをエクスポートし、エクスポートファイルを自動的に設定します。
title: Data Workbench と Adobe Target の統合
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Data Workbench と Adobe Target の統合

{{eol}}

AdobeData WorkbenchとAdobe Targetの統合が容易になり、データセグメントを書き出し、書き出しファイルを自動的に設定するData Workbench機能が追加されました。

AdobeData Workbenchは、データの共有とレポートの生成を行うために、Adobe Targetとのクローズドループ統合を提供します。 Data Workbench内で、電話、店舗などのチャネルを通じたオフラインコンバージョンを含む、利用可能なすべてのデータを使用して、意味のあるセグメントに対する母集団を分析できます。

例えば、訪問者が Web サイトで靴を探してもコンバージョンに至らないとします。 訪問者は、次回の購入を 20%引きでクーポンをダウンロードし、ストアでシャツを購入します。 Data Workbenchを使用すると、そのデータを収集し、そのプロファイルデータを Target にプッシュして、訪問者がオフラインでシャツを購入したことを示すことができます。 その後、その訪問者に対してネクタイを提供するキャンペーンをターゲット設定できます。通常、Target はその訪問者に対して靴のリマーケティングを試みる場合があります。

## Adobe TargetとのData Workbenchの設定

1. ヘッダーを右クリックし、 [!UICONTROL Detail Table] ウィンドウ

   ![](assets/insight-to-tnt.png)

1. 選択 **[!UICONTROL New Target Export]** 新しいエクスポートファイルの名前を **[!UICONTROL Save As]** 」コマンドを使用して、

1. 「**[!UICONTROL Save Export File]**」をクリックします。

   エクスポートテンプレートウィンドウが開きます。

   すべてのAdobe Target情報が自動的に入力されます。 セグメントの書き出しに設定した内容に基づいて、パラメーターリストが構築されます。 完了すると、Data WorkbenchはAdobe Targetサーバーにデータを送信します。

   **注意：** テンプレートファイルは、 [!UICONTROL Profile Architect]. この [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host]、および [!UICONTROL Mbox Name] を入力する必要があります。 複数のサイトがある場合は、複数のテンプレートを入力し、サーバーに保存します。 プロファイルマネージャーのテンプレートは、次の場所にあります。 `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. 次を指定： [!UICONTROL mboxPC] クエリパラメーター。

   Data Workbench属性の名前が [!UICONTROL mboxPC]を使用する場合は、適切なクエリパラメーターを編集し、名前をに変更する必要があります。 _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   エクスポートファイルをサーバーに保存すると、エクスポートが開始されます。 完了したら、 [!UICONTROL TnTSend.exe] アプリケーションが起動し、Target アカウントへのデータの送信が開始されます。

## Target のData Workbenchの設定

Adobe Targetで、次の作業を実行します。

Data WorkbenchがユーザープロファイルをAdobe Targetに渡しています。 Target への書き出し用にを設定するには、API を設定して有効にし、 **[!UICONTROL clientname]** および **[!UICONTROL domain postfix]** 書き出し設定ファイルのパラメータ (`export.cfg`) をクリックします。

という新しいブール型オプションが追加されました。 **[!UICONTROL Oneshot]** は、セグメントエクスポートファイルに追加されました。 このオプションは、新しいプロファイルと共に配布されるテンプレートファイルに含まれます。 If [!UICONTROL Oneshot] が _true_、 `.export` ファイルの名前が次の値に変更されます： `.export.done-TIMESTAMP` エクスポートの完了後は、セグメントが 2 回以上エクスポートされないようにします。 これは、Adobe Targetにエクスポートする際に重要です。

**注意：** Data WorkbenchからAdobe Targetへの呼び出しは、 [!UICONTROL mbox] 呼び出しに使用する場合、送信されるプロファイルごとに 1 回の呼び出しが必要です。 その結果、2 つのソリューション間で複数の呼び出しが必要な場合は、コストが増加します。

設定が不完全な場合は、ログに次のエラーメッセージが表示されます。

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Adobe TargetのData Workbench

Adobe Target内では、顧客がプロファイルデータを送信するための特別な設定は必要ありません。 ユーザーのプロファイル情報は通常、通常、 [!UICONTROL mbox] リクエストを実行すると、サーバーは、追加の設定なしで、対象となるキャンペーンの設定に対してプロファイルパラメーターを標準機能として使用できるようになります。

Adobe TargetにはData Workbench統合が組み込まれており、スーパーユーザークライアントの詳細ページから有効にできます。 このオプションを有効にすると、Adobe Target内のData Workbenchから共有されたセグメントが表示され、ターゲティングで使用できるようになります。

## ExportIntegration.exe での HTTP ログレポートの設定

レポート作成の時間を短縮 [!UICONTROL HTTP.log] 使用時 [!UICONTROL ExportIntegration.exe] Adobe Target統合ファイルを書き出す

新しい [!UICONTROL httpLoggingEI.cfg] 設定ファイル ( 次の場所にあります： `server\Admin\Export\httpLoggingEI.cfg`) を使用すると、詳細ログを [!UICONTROL HTTP.log] 次を使用してデータをエクスポートする場合に使用するファイル [!UICONTROL ExportIntegration.exe]. これにより、詳細な要求/応答のログを停止できます。

詳細ログは、で既にキャプチャされています。 [!UICONTROL TnTSend.log] ファイル。

_True_ 詳細ログを設定し、 _False_ 詳細ログを停止 [!UICONTROL HTTP.log] ファイル。

False 設定の場合、警告メッセージのみが [!UICONTROL HTTP.log] ファイル（情報コンテンツは送信されません）。
