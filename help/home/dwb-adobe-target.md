---
description: Data WorkbenchとAdobe Targetの統合を参照してください。 データセグメントを書き出し、書き出しファイルを自動的に埋め込みます。
solution: Analytics
title: Data WorkbenchとAdobe Targetの統合
topic: Data workbench
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data WorkbenchとAdobe Targetの統合

Data Workbenchの機能を使用して、Adobe Data WorkbenchとAdobe Targetの統合が容易になりました。Data Workbenchの機能を使用して、データセグメントを書き出し、書き出しファイルを自動的に埋め込むことができます。

Adobe Data Workbenchは、データの共有とレポートの生成を行うために、Adobe Targetとのクローズループ統合を提供します。 Data Workbench内では、電話、店舗などのチャネルを介したオフラインコンバージョンを含む、使用可能なすべてのデータを使用して、訪問者の意味のあるセグメントを分析できます。

例えば、訪問者がWebサイトで靴を探しても、コンバージョンが行われないとします。 その代わり、訪問者は次回の購入時に20%引きのクーポンをダウンロードし、店頭でシャツを購入します。 Data Workbenchを使用すると、そのデータを収集し、そのプロファイルデータをTargetにプッシュして、訪問者がオフラインでシャツを購入したことを示すことができます。 その後、ネクタイを提供するキャンペーンをターゲットに設定できます。通常、Targetは靴をその訪問者に再マーケティングしようとします。

## Data WorkbenchとAdobe Targetの設定

1. ウィンドウのヘッダーを右クリック [!UICONTROL Detail Table] します。

   ![](assets/insight-to-tnt.png)

1. を選択 **[!UICONTROL New Target Export]** し、メニューのコマンドの下に新しい書き出しファイルの **[!UICONTROL Save As]** 名前を入力します。

1. クリック **[!UICONTROL Save Export File]**.

   書き出しテンプレートウィンドウが開きます。

   すべてのAdobe Target情報が自動的に入力されます。 セグメントエクスポートの内容に基づいて、パラメータリストが作成されます。 完了すると、Data WorkbenchはデータをAdobe Targetサーバーに送信します。

   **注意：** テンプレートファイルは、で設定する必要がありま [!UICONTROL Profile Architect]す。 、、 [!UICONTROL Client Name]およ [!UICONTROL Domain Postfix]びを入 [!UICONTROL Mbox Host]力する [!UICONTROL Mbox Name] 必要があります。 複数のサイトがある場合は、複数のテンプレートに入力し、サーバーに保存します。 プロファイルマネージャーのテンプレートは、にありま `Context\FileNew\Detail Table\Export\Copy`す。

   ![](assets/insight-to-tnt1.png)

1. クエリパラメータ [!UICONTROL mboxPC] ーを指定します。

   Data Workbench属性の名前が以外の名前の場合は、適切なクエリパラメ [!UICONTROL mboxPC]ーターを編集し、名前をmboxPCに変更する必要があ _ります_。

   ![](assets/insight-to-tnt2.png)

   エクスポートファイルをサーバーに保存すると、エクスポートが開始されます。 完了すると、アプリケーシ [!UICONTROL TnTSend.exe] ョンが起動し、Targetアカウントへのデータの送信が開始されます。

## Target用のData Workbenchの設定

Adobe Targetで次のタスクを実行します。

Data Workbenchは、ユーザープロファイルをAdobe Targetに渡します。 Targetへの書き出しを設定するには、APIを設定して有効にし、書き出し設定ファイルのパラメ **[!UICONTROL clientname]** ーターと **[!UICONTROL domain postfix]** パラメーターを指定する必要があり`export.cfg`ます()。

セグメントエクスポートファイルに、という **[!UICONTROL Oneshot]** 新しいブール値オプションが追加されました。 このオプションは、新しいプロファイルと共に配布されるテンプレートファイルに含まれます。 を [!UICONTROL Oneshot] trueに設定すると _、エクスポートの完了後_`.export``.export.done-TIMESTAMP` にファイル名がに変更され、セグメントが複数回エクスポートされないようになります。 これは、Adobe Targetに書き出す場合に重要です。

**注意：** Data WorkbenchからAdobe Targetへの呼び出しは、1回の呼び出しとしてカウントされ、送 [!UICONTROL mbox] 信される各プロファイルに対して1回の呼び出しが必要になります。 その結果、2つのソリューション間で複数の呼び出しが必要な場合は、コストが増加します。

設定が不完全な場合、ログに次のエラーメッセージが表示されます。

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Data Workbench用のAdobe Targetの設定

Adobe Target内では、顧客がプロファイルデータを送信する際に特別な設定は必要ありません。 通常、ユーザーのプロファイル情報は通常のリクエストで渡され、サーバーは、追加の設定を行わなくても、ターゲットキャンペーンの設定で使用できるプロファイルパラメーターを標準機能として使用できます。 [!UICONTROL mbox]

Adobe TargetにはData Workbench統合が組み込まれており、これはスーパーユーザーのクライアントの詳細ページで有効にできます。 このオプションを有効にすると、Adobe Target内のData Workbenchから共有されるセグメントが表示され、ターゲット設定で使用できるようになります。

## ExportIntegration.exeでHTTPログレポートを設定します。

を使用してAdobe Target統合ファイルを書き [!UICONTROL HTTP.log] 出す場合に、 [!UICONTROL ExportIntegration.exe] 長いレポートを減らします。

新しい設定フ [!UICONTROL httpLoggingEI.cfg] ァイル(にあ `server\Admin\Export\httpLoggingEI.cfg`ります)を使用すると、を使用してデータを書き出す際に、ファイルに対 [!UICONTROL HTTP.log] する詳細ログを減らすことができま [!UICONTROL ExportIntegration.exe]す。 これにより、詳細な要求/応答のログを停止できます。

詳細ログは既にファイルに取り込まれ [!UICONTROL TnTSend.log] ています。

_Trueを指定すると_ 、詳細ログの記録が行われ、 _Falseを指定すると_ 、ファイルへの詳細ログの記録が停止 [!UICONTROL HTTP.log] されます。

「False」設定の場合、警告メッセージのみがファイルに送信さ [!UICONTROL HTTP.log] れます（情報の内容は送信されません）。