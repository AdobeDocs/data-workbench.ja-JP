---
description: Data Workbenchクライアントの詳細テーブルビジュアライゼーションから、セグメントエクスポートの定義を簡単に作成できます。
title: セグメントエクスポート
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 55%

---

# セグメントエクスポート{#segment-export}

Data Workbenchクライアントの詳細テーブルビジュアライゼーションから、セグメントエクスポートの定義を簡単に作成できます。

また、[!DNL Segment Exports]は、外部プロセスを使用して結合する必要のある各DPU上で部分的な結果を生成するのではなく、自動的に1つのサーバーに結果を結合します。 セグメントエクスポートファイルを作成して[!DNL Profile Manager]に保存し、任意のサーバーに出力ファイルをアップロードできます。

**セグメントエクスポートサーバーを設定するには**

[!DNL Segment Export]機能により、各DPUに個別の出力ファイルを作成するのではなく、セグメントエクスポートサーバーに単一の出力ファイルが作成されます。 セグメントエクスポートサーバーは、通常 FSU 上で動作するように設定されます。

[!DNL Profile Manager]のDataset\ディレクトリで、ワークステーションの[!DNL Segment Export.cfg]を開き、サーバーのアドレスを指定します。 （アドレスは IP または完全修飾ドメイン名です）。

![](assets/segment_export_cfg.png)

これは、セグメントエクスポートの結果を受け取るData WorkbenchサーバーのIPです。 これは 1 回だけの設定です。[!DNL Segment Export.cfg] が存在しない場合、エクスポートは実行されません。

**エクスポートディレクトリを設定するには**

セキュリティの点から、セグメントエクスポートの後に実行する実行可能ファイルやバッチファイルは、セグメントエクスポートサーバーの設定可能なスクリプトディレクトリに置く必要があります。

[!DNL .part]と最終出力は、設定可能なエクスポートディレクトリに置く必要があります。 実行するコマンドは、Command および Command Arguments に存在します。Command Arguments 内の %file% のインスタンスは、出力ファイルのパスに置き換えられます。

>[!NOTE]
>
>Data Workbench5.4以降では、¥Exportsフォルダーが自動的に作成されます。 バージョン 5.4 より前に設定した以前のエクスポートディレクトリでは、各セグメントエクスポートのファイル名の前に Exports\ プレフィックスが必要でした。現在このプレフィックスの追加は不要です。

1. [!DNL Segment Exports]の宛先サーバーの[!DNL Communications.cfg]で、サーバーのリストにSegmentExportServerを追加します。 （例を赤で示します）。

   ![](assets/communications_cfg_example.png)

   Exports Directory:[!DNL .part]と出力ファイルを置く場所を指定します。 共有ディレクトリも指定できます。

   Scripts Directory：実行するすべての実行可能ファイルまたはバッチファイルのあるディレクトリを指定します。

1. 同じサーバー上の [!DNL Access Control.cfg] で、URI /SegmentExportServer/ への読み書きアクセス権をクラスターサーバー AccessGroup に追加します。

   ![](assets/accesscontrol_cfg_example.png)

1. [!DNL .export]ファイルを変更します。

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

1. 詳細テーブルのヘッダーで右クリックし、**[!UICONTROL Create Segment Export File]**&#x200B;を選択します。
1. [!DNL Save as]に[!DNL .export]ファイルの名前を入力します。
1. [!DNL .export]ファイルで、必要に応じてパラメーターを設定します。

   ワークスペース内の選択やフィルターは、エクスポートファイルに組み込まれます。

1. [!DNL .export]ファイルを保存します。

   保存したファイルは[!DNL Profile Manager]に表示され、サーバに保存できます。 ファイルをサーバーに保存すると、エクスポートが開始されます。
