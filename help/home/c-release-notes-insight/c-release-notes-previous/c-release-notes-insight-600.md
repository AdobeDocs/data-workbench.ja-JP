---
description: Data Workbench 6.0.4 で導入された新機能、バグの修正および既知の問題が含まれています。
title: Data Workbench 6.0 のリリースノート
uuid: b348425e-3304-4db7-a280-479a34452bdb
exl-id: be69b3be-24e7-4a8c-9dc8-1360a9b6fb3a
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 87%

---

# Data Workbench 6.0 のリリースノート

Data Workbench 6.0.4 で導入された新機能、バグの修正および既知の問題が含まれています。

## 新機能 {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench（Insight 6.0）には、追加されたレポート機能と予測分析ツールの次の新機能とビジュアライゼーションが含まれています。

| Data Workbench の機能 | 説明 |
|---|---|
| [ファネルビジュアライゼーション](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | ファンネルビジュアライゼーションでは、顧客の連続するプロセスフローを定義し、プロセスの各手順での訪問者のフォールアウトを視覚化できます。 |
| [訪問者クラスタリング](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | クラスタリングを使用すると、顧客の特性を活用して訪問者を動的に分類し、選択したデータ入力に基づいてクラスターセットを生成して、顧客分析とターゲティングに活かすことができます。 |
| [相関分析](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | 相関分析を使用すると、関連するデータの関係をすばやく特定して、分析を拡張および強化できます。 |
| [更新された DeviceAtlas の配布](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | DeviceAtlas JSON ファイルは、DeviceAtlas.dll と DeviceAtlas64.dll と共に .bundle ファイル（.tar.gz に名前が変更）で配布されます。 |

## クライアントのアップグレード要件 {#section-f316103b48374b6eac77e8feb5c47ecf}

Data Workbench（Insight 6.0）のクライアント機能のために、次のアップグレードタスクを実行します。

**クライアントの .zbin ファイルの更新**

Data Workbench では、現在、補助的なテキスト入力プロセスとして Input Method Editor（IME）をサポートしており、フローティングテキストボックスを使用して、キーボードから国際文字を入力できます。Data Workbench はデフォルトで英語をサポートしていますが、中国語の仮想キーボード（Pinyin IME）など、国際言語をサポートする他のファイルをロードすることもできます。

バージョン 6.0 に更新する前に、クライアントアプリケーションには新しい辞書ファイル（.zbin ファイル）が必要です。

前提条件:

* Insight の管理者は、Insight 6.0 クライアントと Report Server 6.0 にアップグレードする前に、Insight Server 6.0 にアップグレードする必要があります。
* Insight の管理者は、言語に基づいた zbin ファイル（en-us.zbin、zh-cn.zbin）を選択し、言語ファイルをコピーして、名前を insight.zbin に変更し、名前を変更したファイルを Report Server の（実行可能ファイルが配置されている）ルートディレクトリに配置する必要があります。その後、Insight Report Server を再起動します。

サーバー側のアップグレードの追加情報については、[サーバーのアップグレード要件](../../../home/c-release-notes-insight/release-notes.md)を参照してください。

**クライアントのzbinファイルを（バージョン5.xから6.0に）アップグレードするには**

1. このアップグレード中にクライアントが Insight Server から更新されないようにするために、Insight.cfg 引数を false に設定します。

   ```
   Update Software = bool: false
   ```

1. Insight クライアントを再起動します。
1. ソフトウェアおよびドキュメントプロファイル（SoftDocsプロファイル）に移動し、必要な&#x200B;**[!UICONTROL Insight.zbin]**&#x200B;ファイルをダウンロードします。[!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Insight.exe ファイルと同じフォルダーに Insight.zbin ファイルをコピーします。
1. Insight クライアントが Insight Server から更新されるように、Insight.cfg ファイル引数を true に変更します。

   ```
   Update Software = bool: true
   ```

1. クライアントを再起動します。

   クライアントがサーバーと同期され、クライアントがダウンロード中であることを示すメッセージが表示されます。ダウンロードが終了すると、Insight クライアントを再起動するかどうかを尋ねるメッセージが表示されます。
1. 「**OK**」をクリックして、クライアントを再起動します。

   クライアントが起動し、バージョン 6.0 にアップグレードされます。

1. Insight.zbin クライアントの同期を有効にするために、クライアントをもう一度再起動します。

   次のメッセージが表示された場合は、zbin が Insight.exe ファイルと一緒に正しいフォルダーの場所に配置されていなかったことを示しています。

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   この問題を解決するには、Insight.exe を削除し、最新バージョンの Insight.exe.old の名前を Insight.exe に変更した後、上記の手順 1 から再度開始します。

## サーバーのアップグレード要件 {#section-d6edba8b36234957ba8d06b555667a5a}

Insight 6.0 のサーバー機能のために、次のアップグレードタスクを実行します。

**すべての Insight Server 6.0 パッケージを更新します**。Insight 6.0 には、新しい予測分析プロファイルなど、更新する必要があるサーバーパッケージが含まれています。

>[!IMPORTANT]
>
>更新する際に、Insight Server 6.0を新規インストールしてサーバークラスターをアップグレードすることをお勧めします。

また、クライアントで Insight Server 6.0 を新規インストールしてサーバークラスターをアップグレードすることもお勧めします。

## サーバークラスターのアップグレード

**言語ファイル（.zbin ファイル）を準備します。** Insight管理者は、必要な言 `<language>.zbin` 語のファイル(例：en-us.zbin 、 zh-cn.zbin)は、フォルダー内にあり `/localization/<language>.zbin` ます。次に、言語ファイルをコピーし、名前を「insight.zbin」に変更します。

言語ファイル（.zbin）の準備ができたら、Insight Client と Report Server の両方を更新する必要があります。Insight Client は、[クライアントのアップグレード処理](../../../home/c-release-notes-insight/release-notes.md)中に更新されますが、Report Server は、ほとんどの場合、Insight の管理者が更新します。

**言語ファイル（.zbin ファイル）を使用して、Report Server を更新します**。

どの言語でも、Report Server 6.0 では、「insight.zbin」ファイルを Report Server のルートフォルダーにコピーする必要があります。

Report Server の言語ファイルを更新します。

1. 名前を変更した「insight.zbin」ファイルをルートの ReportServer ディレクトリに追加します。
1. Report Server の設定ファイル（reportserver.cfg）に、全角文字言語用のフォントを設定する必要があります。例えば、中国語では SimSun フォントを追加する必要があります。

   ```
   Report Server.cfg - Add Fonts 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. ローカリゼーションのために、コマンドラインで Report Server 6.0 のパラメーターを渡す必要があります。次に例を示します。

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >ロケールが指定されていない場合、Report Serverはinsight.zbinファイルで選択された言語をデフォルトにします。

   次の手順に従って、Locale パラメーターを使用して、ReportServer をサービスとして開始します。

   1. 管理者としてコマンドプロンプトを起動します。
   1. ReportServer のフォルダーに移動します。
   1. 次のコマンドを入力して、サービスを開始します。

      * 英語の場合：[!DNL ReportServer.exe -RegServer -Locale -en-us]
      * 中国語の場合：[!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. ReportServer が正しいパラメーターで実行されていることを確認するには：

   1. Windows サービスマネージャーを開きます。
   1. [!DNL Adobe Insight Report Server - Properties]を右クリックします。

   実行可能ファイルのパスには、次のパラメーターが含まれています。

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**予測分析のプロファイル設定ファイルを変更します**。Insight の管理者は、カスタム profile.cfg ファイルを変更して、予測分析プロファイルを含めて、Insight で利用できるようにする必要があります。

profile.cfg エントリの例：

```
Example ("profile.cfg"): 
Profile = profileInfo:  
  Active = bool: true 
  Directories = vector: 5 items 
    0 = string: Base\\  
    1 = string: Predictive Analytics\\ 
    2 = string: Geography\\ 
    3 = string: Adobe SC\\ 
    4 = string: Custom Profile\\ 
```

**PAServer.cfg ファイルを更新します**。Insight Server に予測分析クラスタリングジョブを送信する場合は、サーバー側でクラスタリング送信を処理するように PAServer.cfg ファイルを設定する必要があります。

カスタムプロファイルは、予測分析プロファイル（Server\Profiles\Predictive Analytics\Dataset）から PAServer.cfg を継承する必要があります。実装サイトごとに PAServer.cfg を設定して保存します。

>[!NOTE]
>
>PAServer.cfgを設定し、カスタムプロファイルに保存したら、サイト全体でInsight Serverを再起動する必要があります。

**Report Server をアップグレードします。** Report Server のフォントと起動パラメーターを更新する必要があります。

前提条件:

* Insight の管理者は、Report Server 6.0 にアップグレードする前に、Insight Server 6.0 にアップグレードする必要があります。
* どの言語でも、Report Server 6.0 では、Insight.zbin を Report Server のルートフォルダーに追加する必要があります。`base/localization/<language>.zbin`がコピーされ、名前が「insight.zbin」に変更されていることを確認します。 Report Server ディレクトリのルートにコピーします。

フォントと起動パラメーターを更新します。

1. Report Server では、別の言語に出力するために、全角文字用のフォントを設定する必要があります。

   次に例を示します。

   Report Server.cfg - Add Fonts

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. ローカリゼーションのために、コマンドラインで Report Server 6.0 のパラメーターを渡す必要があります。

   Locale パラメーターを使用して、Report Server をサービスとして開始するには：

   1. Report Server サービスを停止します。
   1. 管理者としてコマンドプロンプトを起動します。
   1. Report Server の install フォルダーに移動します。
   1. 次のコマンドを入力して、サービスを開始します。

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

Report Server が正しいパラメーターで実行されていることを確認するには：

1. Windows サービスマネージャーを開きます。
1. [!DNL Adobe Insight Report Server - Properties]を右クリックします。
1. 実行可能ファイルのパスには、次のパラメーターが含まれています。

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

Insight 6.0 の SiteCatalyst データフィード&#x200B;**を**&#x200B;アップグレードします。Insight 6.0 の SiteCatalyst データフィードのファイル名の形式が変更されました。

現在のファイル名の形式：

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

新しいファイル名の形式：

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>この変更は、SiteCatalystデータフィードの&#x200B;*wbench/ecom*&#x200B;バージョンで現在デプロイされているユーザーには影響しません。

ファイル名の形式の変更は、ログ処理中の Insight の開始時刻と終了時刻の宣言をフルに使用できるようにするためのものです。これにより、処理中に、1 行ずつ検索してすべてのソースファイルをフィルターせずに、ファイルの内容を読み込む必要があるかどうかを評価できます。

ほとんどの場合、この機能をフルに使用できるように、ファイルを受け取ったときに名前変更処理が実装されています。この変更により、追加の処理の必要性やオーバーヘッドなしに、デフォルトで必要な命名規則が提供されます。

新しい SiteCatalyst データフィードを使用するには：

1. 受信プロセスが新しいファイル名の形式を処理する方法を決定します。

   実装時にデプロイされた標準の名前変更／移動スクリプトにより、拡張子が「.gz」のファイルが移動され、ファイル名が先頭に RSID を含むファイル名の形式に一致した場合にのみ、名前の変更が実行されます。

   新しいファイル名の形式は、次のとおりです。

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. 定義されたログソースパスを評価して、すべてのファイルが読み込まれることを確認します。

   既に名前変更スクリプトを実装している場合は、この新しいファイル名の形式を読み取るようにログソースを既に定義しています。

## 修正点 {#section-203f917dd6224114a1f801309c4c2cee}

* 現在は、変更を保存せずにワークスペースを終了するためのキーの組み合わせが&#x200B;**[!UICONTROL `<Ctrl>`+`<Backspace>`]**&#x200B;に更新されています。 以前は、変更を無効にし、`<Ctrl>` + `<Delete>`を押してワークスペースを閉じていました。

## Data Workbench 6.0.4 のリリースノート{#data-workbench-release-notes}

Data Workbench 6.0.4 で導入された新機能、バグの修正および既知の問題が含まれています。

以前の各リリースに基づいた以前の機能や修正を確認するには、[リリースノートのアーカイブ](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html)を参照してください。

## 新機能 {#section-2-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.0.4 には、追加されたレポート機能と予測分析ツールの次の新機能とビジュアライゼーションが含まれています。

**傾向スコアリングビジュアライゼーション**。Data Workbench では、各訪問者のスコアを、指定されたイベントが発生するおよその確率として計算します。訪問者スコアリングビジュアライゼーションでは、入力変数に基づいて興味のあるすべての訪問者について指定されたイベントの確率を示すスコアディメンションを作成できます。

![](assets/visitor_scoring_visual.png)

この機能について詳しくは、[傾向スコアリング](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40)を参照してください。

## アップグレード要件 {#section-08bd6fe3da8740fcb19688e8cac6f223}

**ログソース ID を定義する必要があります**。バージョン 6.04 以降では、ログソース ID が定義されていないと、次のエラーが表示されます。

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

ログソースあたりの行数の記録は、Data Workbench 6.0 で追加され、カスタムプロファイルの Log Processing.cfg ファイルで一意のログソース ID を追加することによって定義できます。ログソース ID が空の場合、ログソースデータの読み取りが完了しない、不一致が起こるなど、ログ処理の問題が発生する可能性があります。

```
Log Processing.cfg 
Log Sources = vector: 2 items 
  0 = VisualSensor: 
    Compressed = bool: false 
    Log Paths = vector: 1 items 
      0 = Path: \some path\ 
    Log Server = serverInfo:  
      Address = string:  
      Name = string:  
      Port = int: 80 
      Proxy Address = string:  
      Proxy Password = string:  
      Proxy Port = int: 8080 
      Proxy User Name = string:  
      SSL Client Certificate = string: Certificates\\server_cert.pem 
      SSL Server Common Name = string:  
      Use SSL = bool: false 
     
Log Source ID = string: <Name your ID Here>
    Name = string:  
    Recursive = bool: false
```

**FSU リソースを委任する機能**

[!DNL Profiles/`<profilename>`/dataset/Cluster.cfg]で、正規化リストサーバーとソースリストサーバーに別々のファイルサーバーユニット(FSU)を指定できるようになりました。 これらのサービスがマスター FSU に関連付けられることはなくなりました。

>[!NOTE]
>
>リストサーバーが指定されていない場合、リストサーバーは正規化サーバーの構成設定を継承します。

[!DNL cluster.cfg]ファイルの例。

```
Cluster = ClusterConfig: 
  Normalize Server = serverInfo: 
    Address = string: normalizeserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false 
  List Server = serverInfo: 
    Address = string: sourcelistserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false
```

## 修正されたバグ {#section-3b4b85a35f534288adf8a5246ef028cc}

* Data Workbench 6.0 では、相関行列およびクラスタービルダーでバックグラウンドでの計算がサポートされていませんでした。この問題がバージョン 6.0.4 で修正されました。
* 以前は、ファンネルで選択を行っている状態で手順を削除すると、アクセス違反が発生する可能性がありました。この問題は解決されました。
* 負荷が大きい場合に問題を引き起こす可能性があった、セグメントエクスポートの潜在的なロック状態を修正しました。
