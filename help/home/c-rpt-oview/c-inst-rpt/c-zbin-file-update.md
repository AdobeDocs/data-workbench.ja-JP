---
description: すべての言語で、Report Server 6.0 以降では、Report Server のルートフォルダーにコピーした「insight.zbin」ファイルが必要です。
title: 言語ファイル（.zbin ファイル）を使用したレポートサーバーの更新
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
exl-id: a76b7c01-83f0-4cf2-97a9-07d51cc75b3c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 70%

---

# 言語ファイル（.zbin ファイル）を使用したレポートサーバーの更新{#update-report-server-with-a-language-file-zbin-file}

{{eol}}

すべての言語で、Report Server 6.0 以降では、Report Server のルートフォルダーにコピーした「insight.zbin」ファイルが必要です。

Report Server の言語ファイルを更新します。

1. 名前を変更した「insight.zbin」ファイルをルートの ReportServer ディレクトリに追加します。
1. Report Server の設定ファイル（reportserver.cfg）に、全角文字言語用のフォントを設定する必要があります。例えば、中国語では SimSun フォントを追加する必要があります。

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
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
   >ロケールが指定されていない場合、レポートサーバーはデフォルトで英語に設定されます。

   次の手順に従って、Locale パラメーターを使用して、ReportServer をサービスとして開始します。

   1. 管理者としてコマンドプロンプトを起動します。
   1. ReportServer のフォルダーに移動します。
   1. 次のコマンドを入力して、サービスを開始します。

      * 英語の場合： [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * 中国語の場合： [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. ReportServer が正しいパラメーターで実行されていることを確認するには：

   1. Windows サービスマネージャーを開きます。
   1. 右クリック [!DNL Adobe Insight Report Server - Properties].

   実行可能ファイルのパスには、次のパラメーターが含まれています。

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```
