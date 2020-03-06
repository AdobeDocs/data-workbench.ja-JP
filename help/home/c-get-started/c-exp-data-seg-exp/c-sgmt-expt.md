---
description: Data Workbenchクライアントの詳細テーブルビジュアライゼーションから、セグメントエクスポートの定義を簡単に作成できます。
solution: Analytics
title: セグメントのエクスポート
topic: Data workbench
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Segment export{#segment-export}

Data Workbenchクライアントの詳細テーブルビジュアライゼーションから、セグメントエクスポートの定義を簡単に作成できます。

In addition, [!DNL Segment Exports] automatically combine their results to a single server, rather than producing partial results on each DPU that you must combine using an external process. You can create a segment export file, save it to the [!DNL Profile Manager], and upload the output file to a server of your choice.

**セグメントエクスポートサーバーを設定するには**

The [!DNL Segment Export] feature creates a single output file on the segment export server, rather than separate output files created on each DPU. セグメントエクスポートサーバーは、通常 FSU 上で動作するように設定されます。

In the Dataset\ directory in the [!DNL Profile Manager], open the [!DNL Segment Export.cfg] in Workstation, and specify your server’s address. （アドレスは IP または完全修飾ドメイン名です）。

![](assets/segment_export_cfg.png)

これは、セグメントエクスポートの結果を受け取るData WorkbenchサーバーのIPです。 これは 1 回だけの設定です。[!DNL Segment Export.cfg] が存在しない場合、エクスポートは実行されません。

**エクスポートディレクトリを設定するには**

セキュリティの点から、セグメントエクスポートの後に実行する実行可能ファイルやバッチファイルは、セグメントエクスポートサーバーの設定可能なスクリプトディレクトリに置く必要があります。

The [!DNL .part] and final output must reside in the configurable Exports directory. 実行するコマンドは、Command および Command Arguments に存在します。Command Arguments 内の %file% のインスタンスは、出力ファイルのパスに置き換えられます。

>[!NOTE]
>
>Data Workbench 5.4では、¥Exportsフォルダーが自動的に作成されます。 バージョン 5.4 より前に設定した以前のエクスポートディレクトリでは、各セグメントエクスポートのファイル名の前に Exports\ プレフィックスが必要でした。現在このプレフィックスの追加は不要です。

1. In [!DNL Communications.cfg] on the destination server for [!DNL Segment Exports], add a SegmentExportServer to the list of servers. （例を赤で示します）。

   ![](assets/communications_cfg_example.png)

   Exports Directory: Specifies where to put [!DNL .part] and output files. 共有ディレクトリも指定できます。

   Scripts Directory：実行するすべての実行可能ファイルまたはバッチファイルのあるディレクトリを指定します。

1. 同じサーバー上の [!DNL Access Control.cfg] で、URI /SegmentExportServer/ への読み書きアクセス権をクラスターサーバー AccessGroup に追加します。

   ![](assets/accesscontrol_cfg_example.png)

1. Change your [!DNL .export] files:

   ![](assets/segment_export_query_example.png)

1. 各プロファイルに対して、次の内容の [!DNL Segment Export.cfg] を Dataset\ ディレクトリ内に置きます。

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. Exports Directory と Scripts Directory で参照するディレクトリが存在することを確認します。

   スクリプトディレクトリ内の実行可能ファイルとバッチファイルのみ、セグメントエクスポートのコマンドとして実行できます。

**セグメントエクスポートファイルを作成するには**

1. ワークスペースで、データのサブセットを表示する詳細テーブルを作成し（ビジュアライゼーション／詳細テーブル）、属性を追加します。
1. 必要に応じて、ワークスペースで選択を行います（選択やフィルターを行うと、エクスポートに適用されます）。

   ![](assets/create_segment_export_file.png)

1. 詳細テーブルのヘッダーで右クリックし、を選択しま **[!UICONTROL Create Segment Export File]**&#x200B;す。
1. にフ [!DNL Save as]ァイルの名前を入力し [!DNL .export] ます。
1. On the [!DNL .export] file, configure the parameters as necessary.

   ワークスペース内の選択やフィルターは、エクスポートファイルに組み込まれます。

1. Save the [!DNL .export] file.

   The saved file displays in the [!DNL Profile Manager] for you to save to the server. ファイルをサーバーに保存すると、エクスポートが開始されます。

