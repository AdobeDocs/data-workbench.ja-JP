---
description: オプションのセンサーのtxlogd.confファイルパラメーターに関する情報です。
title: オプションのパラメーター
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
exl-id: 5141f215-979c-4eb8-8c2c-94eef5815743
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 2%

---

# オプションのパラメーター{#optional-parameters}

オプションのセンサーのtxlogd.confファイルパラメーターに関する情報です。

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AddressFilter </td> 
   <td colname="col2"> <p>指定したIPアドレスをフィルターできます。 </p> <p>特定のアドレスをフィルタリングする場合、「パケット」はログに記録されません。 この機能により、ログ処理の前に内部または監視対象のエージェントを排除し、ログ処理の速度を向上させ、データの保存要件を軽減します。 アドレスを指定する場合は、ワイルドカードを使用できます。 </p> <p>例：<span class="filepath"> AddressFilter 10.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>特定の種類のコンテンツをログに含めるか除外するかを指定します。 </p> <p>パラメーターの値は、応答のコンテンツタイプに対してプレフィックス照合されます。 </p> <p>例えば、「image/」はすべての画像コンテンツタイプに一致し、「image/gif」はそのタイプにのみ一致します。 特定のcontent-typeに対して複数の一致が見つかった場合は、最も具体的な一致が使用されます。 したがって、 ContentFilterIncludeパラメーターに「image/gif」を、 ContentFilterExcludeパラメーターに「image/」を、応答に「image/gif」を指定できますが、他の画像タイプはすべて除外されます。 </p> <p>例：<span class="filepath"> ContentFilterInclude *</span> </p> <p>例：<span class="filepath"> ContentFilterExclude image/,text/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>このパラメーターは、Adobeコンサルティングサービスで作業する場合にのみ設定します。 </p> <p>Webモジュールおよびトランスミッターのデバッグログを有効にします。 </p> <p>このパラメーターは、<span class="wintitle"> Sensor</span>が正しく動作しない場合に使用します。 このパラメーターを設定した後、指定したパスの場所に空のファイルを作成し、すべてのユーザーに対して「書き込み」権限を付与する必要があります。 例えば、（WebサーバーのUNIXシェル内）: 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>デバッグのログは、短期間のみ有効にする必要があります。有効にした後、ログファイルをAdobeコンサルティングサービスに送信して分析します。 </p> <p>例：<span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobeでは、このパラメーターをまずテスト環境に設定して、システムへの影響を判断することをお勧めします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>指定されたフィールドを無効にします </p> <p>ユーザーは、使用しないフィールドや保存したくないフィールドを排除できます。 フィールドが文字列値を受け取る場合、無効にすると空白の文字列が渡されます。 フィールドが数値を取る場合、無効にすると数値0(0)が渡されます。 次のフィールドを無効にできます。 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-visitor </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-bytes </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-stem </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(referrer) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(content-type) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">x-experiment </li> 
     </ul> </p> <p>例：<span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>対照実験設定ファイルのパス。 </p> <p>例：<span class="filepath"> ExpFile C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>リクエストがあった場合に新しい追跡IDが生成され、ユーザーが実験グループに配置されるリソース。 </p> <p> <p>注意： このリソースは、Webサーバー上に物理的に存在する必要はありません。 </p> </p> <p>例：<span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>対照実験を有効にしてサイト全体またはサイトのサブディレクトリ全体を別の場所に再マップする場合は、このパラメーターを「on」に設定します。 デフォルトは「off」です。 </p> <p>例：<span class="filepath"> ExpPartialMatch off</span> </p> <p> <p>注意： このパラメーターを「on」に設定する場合は注意が必要です。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>ContentFilterExcludeパラメーターで除外されるドキュメントタイプをユーザーが要求した場合でも、新しいユーザーの最初のクリックが記録されるかどうかを指定します。 </p> <p>デフォルトは「no」です。 </p> <p>通常、画像ファイルはContentFilterExcludeパラメーターで除外されます。 LogAllNewUsersが「yes」に設定され、新しいユーザーがサーバーから取得する最初のドキュメントがイメージの場合、そのリクエストはログに記録されます。 LogAllNewUsersパラメーターが「いいえ」に設定されているか、まったく設定されていない（また、画像がContentFilterExcludeパラメーターで除外される）場合、新しいユーザーがサーバーから取得する最初のドキュメントが画像であると仮定した場合、要求はログに記録されません。 </p> <p>例：<span class="filepath"> LogAllNewUsers no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>トランスミッターが次のパケットのバッチを送信するのを待つ時間（秒）。 </p> <p>デフォルトは 15 です。 </p> <p>例：<span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>注意： このパラメータ値は、Adobeコンサルティングサービスに問い合わせる前に変更しないでください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyID </td> 
   <td colname="col2"> <p>訪問者トラッキングを無効にして、オプトアウトポリシーに従うことができます。 </p> <p>有効にすると、<span class="wintitle"> Sensor</span>は、V1st cookieが指定されたPrivacyIDに設定されている訪問者の「パケット」をログに記録しません。 これらの訪問者に関する情報は記録されないので、これらの訪問者に関する情報は<span class="keyword"> data workbenchサーバー</span>に送信されず、処理されます。 </p> <p>この機能を有効にするには、次の手順を実行する必要があります。 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> <span class="wintitle"> Sensor</span>の<span class="filepath"> txlogd.conf</span>ファイルで、PrivacyIDの値を0（ゼロ）に定義する必要があります。 <p>例：<span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">Webサイトの所有者は、Cookie IDの値が定義された「<span class="filepath"> txlogd.conf</span>」と一致するように、訪問者(V1st)Cookieを設定するコードを記述する必要があります。 </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>トランスミッター(txlogd)が定期的にリクエストを送信し、Webサイトが正しく動作しているかどうかを確認する場所。 </p> <p>場所は、URLではなく、次の形式で指定されます。 </p> <p>http,<i>serverAddress,port,/resource</i> </p> <p>ここで、<i>serverAddress</i>はサーバー名またはIPアドレス、<i>port</i>はサーバーのHTTPリスニングポート、<i>resource</i>はリクエストする特定のリソース（クエリー文字列を含むことができます）です。 </p> <p>複数のSiteTest行を指定できます。 </p> <p>例：<span class="filepath"> SiteTest http,localhost,80,/test.html</span> </p> <p> <p>注意： 現時点では、httpのみがサポートされています。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>訪問者のブラウザーに設定されたCookieの名前。 </p> <p>デフォルトは「v1st」です。 </p> <p>例：<span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>CertNameパラメーターに対してサーバーを検証するかどうかを示します </p> <p>デフォルトは「on」です。 </p> <p>例：<span class="filepath"></span>のVerifyCertName </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>このパラメーターは、Adobeコンサルティングサービスで作業する場合にのみ設定します。 </p> <p>IISに対し、パケットのログ記録に使用するログ「フック」を2つ選択します。<span class="wintitle"> Sensor</span> </p> <p>IIS <span class="wintitle"> Sensor</span>がパケットを正しくログに記録しない場合は、このパラメーターを使用します。 デフォルトのログフックが正しく機能しない場合、このパラメーターは「off」に設定されます。 デフォルトは「on」です。 </p> <p>例：<span class="filepath"></span>にIISCaptureBytesSent </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>このパラメーターは、Adobeコンサルティングサービスで作業する場合にのみ設定します。 </p> <p>v1st cookieの設定に使用する2つの「フック」のうち、<span class="wintitle"> Sensor</span>に指示します。 </p> <p>このパラメーターは、IIS <span class="wintitle"> Sensor</span>がv1st cookieを正しく設定していない場合に使用します。 デフォルトのフックでv1st cookieが正しく設定されていない場合、このパラメーターは「yes」に設定されます。 デフォルトは「no」です。 </p> <p>例：<span class="filepath"> IISUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>デフォルトでは、<span class="wintitle"> Sensor</span>は、各要求に対してキャッシュ制御応答ヘッダーを送信します。 キャッシュ制御機能が有効な場合、<span class="wintitle"> Sensor</span>は、値がThu, 01 Dec 1994 16:00:00 GMTのExpiresヘッダーをブラウザーに送信します。 </p> <p><span class="filepath"> txlogd.conf</span>ファイル内の次の2行を編集して、必要に応じて応答文字列を変更できます。 </p> <p> <span class="filepath"> </span> <i>&lt;&gt; NewUserCacheControlstring1</span>&gt;</i><span class="filepath"> </span></p> <p> <span class="filepath"> </span> <i>&lt;&gt; CacheControlstring2</span>&gt;</i><span class="filepath"> </span></p> <p>例： </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>キャッシュ制御応答ヘッダーの送信を無効にするには、次に示すように、各行のハイフンを入力します。 </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> このパラメーター内… </th> 
   <th colname="col2" class="entry"> ... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>このパラメーターは、Adobeコンサルティングサービスで作業する場合にのみ設定します。 </p> <p>v1st cookieの設定に使用する2つの「フック」のうち、<span class="wintitle"> Sensor</span>に指示します。 </p> <p>このパラメーターは、Apache <span class="wintitle"> Sensor</span>がv1st cookieを正しく設定していない場合に使用します。 デフォルトのフックでv1st cookieが正しく設定されていない場合、このパラメーターは「yes」に設定されます。 デフォルトは「no」です。 </p> <p>例：<span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>このパラメーターは、Adobeコンサルティングサービスで作業する場合にのみ設定します。 </p> <p><span class="wintitle"> Sensor</span>に対し、両方のフックでv1st cookieを設定しようと指示します。 </p> <p>このパラメーターは、Apache <span class="wintitle"> Sensor</span>がv1st cookieを正しく設定していない場合に使用します。 デフォルトは「yes」です。 </p> <p>「yes」に設定し、v1st cookieが最初のフックに正しく設定されていない場合は、2番目のフックが使用されます。 「no」に設定した場合、ApacheUseAlternateHandlerパラメーターを設定して、v1st cookieの設定に使用するフックを指定します。 </p> <p>例：<span class="filepath"> ApacheUseBothHandlers yes</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>デフォルトでは、<span class="wintitle"> Sensor</span>は、各要求に対してキャッシュ制御応答ヘッダーを送信します。 キャッシュ制御機能が有効な場合、<span class="wintitle"> Sensor</span>は、値がThu, 01 Dec 1994 16:00:00 GMTのExpiresヘッダーをブラウザーに送信します。 </p> <p><span class="filepath"> txlogd.conf</span>ファイル内の次の2行を編集して、必要に応じて応答文字列を変更できます。 </p> <p> <span class="filepath"> </span> <i>&lt;&gt; NewUserCacheControlstring1</span>&gt;</i><span class="filepath"> </span></p> <p> <span class="filepath"> </span> <i>&lt;&gt; CacheControlstring2</span>&gt;</i><span class="filepath"> </span></p> <p>例： </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>キャッシュ制御応答ヘッダーの送信を無効にするには、次に示すように、各行のハイフンを入力します。 </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>注意： Adobeでは、この機能を無効にしないことをお勧めします。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> このパラメーター内… </th> 
   <th colname="col2" class="entry"> ... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>このパラメーターは、Adobeコンサルティングサービスで作業する場合にのみ設定します。 </p> <p>v1st cookieの設定に使用する2つの「フック」のうち、<span class="wintitle"> Sensor</span>に指示します。 </p> <p>このパラメーターは、Apache <span class="wintitle"> Sensor</span>がv1st cookieを正しく設定していない場合に使用します。 デフォルトのフックでv1st cookieが正しく設定されていない場合、このパラメーターは「yes」に設定されます。 デフォルトは「no」です。 </p> <p>例：<span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>このパラメーターは、Adobeコンサルティングサービスで作業する場合にのみ設定します。 </p> <p><span class="wintitle"> Sensor</span>に対し、両方のフックでv1st cookieを設定しようと指示します。 </p> <p>このパラメーターは、Apache <span class="wintitle"> Sensor</span>がv1st cookieを正しく設定していない場合に使用します。 デフォルトは「yes」です。 </p> <p>「yes」に設定し、v1st cookieが最初のフックに正しく設定されていない場合は、2番目のフックが使用されます。 「no」に設定した場合、ApacheUseAlternateHandlerパラメーターを設定して、v1st cookieの設定に使用するフックを指定します。 </p> <p>例：<span class="filepath"> ApacheUseBothHandlers yes</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
