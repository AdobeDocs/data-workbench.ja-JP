---
description: 参照ページタグ実行呼び出しは、測定データを収集する Web ページに挿入されます。
title: 参照ページタグ実行呼び出しの追加
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# 参照ページタグ実行呼び出しの追加{#adding-reference-page-tag-execution-calls}

{{eol}}

参照ページタグ実行呼び出しは、測定データを収集する Web ページに挿入されます。

これは、HTMLドキュメントの本文に含め、必要に応じて、グローバルインクルードフッター内に配置できます。 この [!DNL Reference Page Tag Execution Call] は、Adobeコンサルティングサービスチームとの要件収集会議で特定される可能性のある追加情報を収集するために、チームが変更できます。

を使用したデータ収集を容易にする [!DNL Reference Page Tag]、次の手順を実行します。

1. 次のコードを、HTMLドキュメント本文にコピーします。

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

1. パスを [!DNL zig.js] および [!DNL zag.gif] ファイル。 次に例を示します。

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Web サーバー上で適切な HTTP Cache-Control ヘッダーが設定されていることを確認し、 [!DNL zig.js]および [!DNL zag.gif] ファイルは、ブラウザーによってキャッシュされません。 HTTP Cache-Control ヘッダー情報は、2 つの方法のいずれかを使用して設定できます。 1 つ目の方法は、Web サーバー経由で HTTP ヘッダーを設定する方法です。 2 つ目のメソッドは、スクリプトを使用して、特定のページまたは埋め込みオブジェクトごとに HTTP ヘッダーを設定する方法です。 このスクリプティングメソッドでは、JSP や ASP などのプログラミング言語を使用して Web ページを作成する必要があります。 次に、ページのスクリプトが作成され、適切なヘッダー情報が送信されます。 この方法には、次の 2 つの明白な欠点があります。1) すべてのページは、ヘッダーを送信するためにコード化する必要があります。2) ページは静的HTMLではなく、web サーバーのパフォーマンスに影響を与えます。

Microsoft IIS 上で動作する Web サイトでは、Microsoft管理コンソールを使用して適切な HTTP ヘッダーを追加できます。 Netscape iPlanet Web サーバから提供される Web サイトは、 [!DNL obj.conf] ファイルをサイトの設定ディレクトリ内に配置します。 Apache Web サーバーは、Web マスターに、付属の mod_headers モジュールを使用して HTTP ヘッダーをカスタマイズする機能を提供します。AOLServer は、Tcl モジュールを使用してカスタマイズ可能になります。 HTTP Cache-Control ヘッダーを実装する前に、Web サーバープラットフォームに固有のドキュメントを参照する必要があります。

一般に、HTTP ヘッダーは次のような構造にする必要があります。

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
