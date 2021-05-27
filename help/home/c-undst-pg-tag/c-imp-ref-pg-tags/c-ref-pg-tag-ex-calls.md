---
description: 参照ページタグ実行呼び出しは、測定データを収集するWebページに挿入されます。
title: 参照ページタグ実行呼び出しの追加
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# 参照ページタグ実行呼び出しの追加{#adding-reference-page-tag-execution-calls}

参照ページタグ実行呼び出しは、測定データを収集するWebページに挿入されます。

HTMLドキュメントの本文に含め、必要に応じてグローバルインクルードフッター内に配置できます。 Adobeコンサルティングサービスチームとのミーティングで要件を収集する際に特定される可能性のある追加情報を収集するために、チームが[!DNL Reference Page Tag Execution Call]を変更できます。

[!DNL Reference Page Tag]を使用したデータ収集を容易にするには、次の手順を実行します。

1. HTMLドキュメントの本文に次のコードをコピーします。

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
   
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
   
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. [!DNL zig.js]ファイルと[!DNL zag.gif]ファイルの場所へのパスを変更します。 次に例を示します。

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

ブラウザーで[!DNL zig.js]ファイルと[!DNL zag.gif]ファイルがキャッシュされないように、Webサーバーに適切なHTTPキャッシュ制御ヘッダーが設定されていることを確認してください。 HTTPキャッシュ制御ヘッダー情報は、2つの方法のいずれかを使用して設定できます。 1つ目の方法は、Webサーバーを介してHTTPヘッダーを設定することです。 2つ目のメソッドは、スクリプトを使用して、特定のページまたは埋め込みオブジェクトごとにHTTPヘッダーを設定する方法です。 スクリプティングメソッドを使用する場合、WebページはJSPやASPなどのプログラミング言語を使用して作成されている必要があります。 次に、適切なヘッダー情報を送信するために、ページのスクリプトが作成されます。 この方法には、次の2つの明らかな欠点があります。1)すべてのページは、ヘッダーを送信するためにコード化する必要があり、2)ページは静的HTMLではないので、Webサーバーのパフォーマンスに多少影響します。

Microsoft IIS上で動作するWebサイトでは、Microsoft管理コンソールを使用して適切なHTTPヘッダーを追加できます。 Netscape iPlanet Webサーバーから提供されるWebサイトは、サイトの設定ディレクトリ内の[!DNL obj.conf]ファイルを編集することでこれを実現できます。 Apache Webサーバーは、Tclモジュールを使用してAOLServerがカスタマイズ可能になる付属のmod_headersモジュールを使用してHTTPヘッダーをカスタマイズする機能をWebマスターに提供します。 HTTPキャッシュ制御ヘッダーを実装する前に、Webサーバープラットフォームに固有のドキュメントを参照する必要があります。

一般に、HTTPヘッダーは次のような構造にする必要があります。

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
