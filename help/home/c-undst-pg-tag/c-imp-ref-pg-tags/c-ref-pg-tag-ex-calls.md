---
description: 測定データを収集するWebページに、参照ページタグの実行コールが挿入されます。
solution: Analytics
title: 参照ページタグの実行呼び出しの追加
topic: Data workbench
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 参照ページタグの実行呼び出しの追加{#adding-reference-page-tag-execution-calls}

測定データを収集するWebページに、参照ページタグの実行コールが挿入されます。

HTMLドキュメントの本文に含め、必要に応じてグローバルインクルードフッター内に配置できます。 アドビ [!DNL Reference Page Tag Execution Call] のコンサルティングサービスチームとの会議で要件を収集する際に特定される可能性のある追加情報を収集するように、チームが変更できます。

を使用したデータ収集を容易にするには、次 [!DNL Reference Page Tag]の手順を実行してください。

1. 次のコードをHTMLドキュメントの本文にコピーします。

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

1. とファイルの場所のパスを変更 [!DNL zig.js] しま [!DNL zag.gif] す。 次に例を示します。

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

およびファイルがブラウザーでキャッシュされないように、適切なHTTP Cache-ControlヘッダーがWebサーバー上に設定され [!DNL zig.js]てい [!DNL zag.gif] ることを確認してください。 HTTP Cache-Controlヘッダー情報は、次の2つの方法のいずれかを使用して設定できます。 1つ目の方法は、Webサーバーを介してHTTPヘッダーを設定する方法です。 2つ目の方法は、スクリプトを使用して、特定のページまたは埋め込みオブジェクトごとにHTTPヘッダーを設定する方法です。 スクリプティングメソッドを使用する場合、WebページはJSPやASPなどのプログラミング言語を使用して作成されている必要があります。 次に、適切なヘッダー情報を送信するために、ページのスクリプトが作成されます。 この方法には、次の2つの明らかな欠点があります。1)すべてのページをヘッダー送信用にコード化する必要があります。2)ページを静的HTMLにすることはできません。これは、Webサーバーのパフォーマンスに何らかの影響を与えます。

Microsoft IIS上で実行しているWebサイトでは、Microsoft管理コンソールを使用して適切なHTTPヘッダを追加できます。 Netscape iPlanet Webサーバーから提供されるWebサイトは、サイトの設定ディレクトリ内のフ [!DNL obj.conf] ァイルを編集することで、これを実現できます。 Apache Webサーバーは、Webマスターに、付属のmod_headersモジュールを使用してHTTPヘッダーをカスタマイズする機能を提供します。このモジュールでは、AOLServerはTclモジュールを使用してカスタマイズ可能です。 HTTP Cache-Controlヘッダーを実装する前に、使用しているWebサーバープラットフォームに固有のドキュメントを参照してください。

一般に、HTTPヘッダーは次のように構造化されます。

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```

