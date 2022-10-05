---
description: セグメントクライアントの詳細テーブルビジュアライゼーションから、セグメントエクスポート定義を簡単にData Workbenchできます。
title: セグメントエクスポート
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 55%

---

# セグメントエクスポート{#segment-export}

{{eol}}

セグメントクライアントの詳細テーブルビジュアライゼーションから、セグメントエクスポート定義を簡単にData Workbenchできます。

さらに、 [!DNL Segment Exports] 各 DPU 上に部分的な結果が生成されるのではなく、外部プロセスを使用して結合する必要があるので、結果は 1 台のサーバーに自動的に結合されます。 セグメントエクスポートファイルを作成し、 [!DNL Profile Manager]をクリックし、任意のサーバーに出力ファイルをアップロードします。

**セグメントエクスポートサーバーを設定するには**

この [!DNL Segment Export] 機能は、各 DPU に個別の出力ファイルを作成するのではなく、セグメントエクスポートサーバー上に単一の出力ファイルを作成します。 セグメントエクスポートサーバーは、通常 FSU 上で動作するように設定されます。

次の Dataset\ディレクトリ内： [!DNL Profile Manager]、 [!DNL Segment Export.cfg] ワークステーションで、サーバーのアドレスを指定します。 （アドレスは IP または完全修飾ドメイン名です）。

![](assets/segment_export_cfg.png)

これは、セグメントエクスポートの結果を受け取るData Workbenchサーバーの IP です。 これは 1 回だけの設定です。[!DNL Segment Export.cfg] が存在しない場合、エクスポートは実行されません。

**エクスポートディレクトリを設定するには**

セキュリティの点から、セグメントエクスポートの後に実行する実行可能ファイルやバッチファイルは、セグメントエクスポートサーバーの設定可能なスクリプトディレクトリに置く必要があります。

この [!DNL .part] 最終出力は、設定可能な書き出しディレクトリに配置する必要があります。 実行するコマンドは、Command および Command Arguments に存在します。Command Arguments 内の %file% のインスタンスは、出力ファイルのパスに置き換えられます。

>[!NOTE]
>
>Data Workbench5.4 が初めての場合は、\Exports フォルダーが自動的に作成されます。 バージョン 5.4 より前に設定した以前のエクスポートディレクトリでは、各セグメントエクスポートのファイル名の前に Exports\ プレフィックスが必要でした。現在このプレフィックスの追加は不要です。

1. In [!DNL Communications.cfg] 宛先サーバーで [!DNL Segment Exports]をクリックし、 SegmentExportServer をサーバーのリストに追加します。 （例を赤で示します）。

   ![](assets/communications_cfg_example.png)

   エクスポートディレクトリ：置く場所を指定します [!DNL .part] 出力ファイル 共有ディレクトリも指定できます。

   Scripts Directory：実行するすべての実行可能ファイルまたはバッチファイルのあるディレクトリを指定します。

1. 同じサーバー上の [!DNL Access Control.cfg] で、URI /SegmentExportServer/ への読み書きアクセス権をクラスターサーバー AccessGroup に追加します。

   ![](assets/accesscontrol_cfg_example.png)

1. を [!DNL .export] ファイル：

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

1. 詳細テーブルのヘッダーで、右クリックして「 」を選択します。 **[!UICONTROL Create Segment Export File]**.
1. In [!DNL Save as]、 [!DNL .export] ファイル。
1. の [!DNL .export] ファイルを開き、必要に応じてパラメーターを設定します。

   ワークスペース内の選択やフィルターは、エクスポートファイルに組み込まれます。

1. 保存する [!DNL .export] ファイル。

   保存したファイルは、 [!DNL Profile Manager] サーバーに保存するために使用します。 ファイルをサーバーに保存すると、エクスポートが開始されます。
