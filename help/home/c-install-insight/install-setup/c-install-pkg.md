---
description: Data Workbenchのインストールパッケージに含まれるファイル。
title: インストールパッケージに含まれているファイル
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# インストールパッケージに含まれているファイル{#files-included-in-the-installation-package}

Data Workbenchのインストールパッケージに含まれるファイル。

Insightパッケージには、次のディレクトリが含まれています。

## プログラムファイル {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

ワークステーションの実行ファイル（**[!DNL Insight.exe]**）およびサポートファイルは、デフォルトでは次のフォルダーにインストールされます。

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディレクトリ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span> </b> </td> 
   <td colname="col2"> Data Workbenchクライアントの実行可能ファイル。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span> </b> </td> 
   <td colname="col2"> 言語および <span class="filepath">Appdata</span> フォルダーのパスを設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span> </b> </td> 
   <td colname="col2"> <p>Data Workbench では、現在、補助的なテキスト入力プロセスとして Input Method Editor（IME）をサポートしており、フローティングテキストボックスを使用して、キーボードから国際文字を入力できます。Data Workbench はデフォルトで英語をサポートしていますが、中国語の仮想キーボード（Pinyin IME）など、国際言語をサポートする他のファイルをロードすることもできます。 </p> <p>クライアントアプリケーションで IME をサポートするには、新しい辞書ファイル（<span class="filepath">Insight.zbin</span>）が必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> ワークステーションをアンインストールしてファイルを削除するための実行ファイル。 </td> 
  </tr> 
 </tbody> 
</table>

## AppData ファイル{#section-afddeedf8d29451f996fa46b2dfe932c}

データファイル（**[!DNL Insight.cfg]**、プロファイル、証明書、トレースログおよびユーザーファイル）は、デフォルトでは以下に保存されます。

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディレクトリ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span> </b> </td> 
   <td colname="col2"> Data Workbench設定ファイル。 Data Workbenchが動作するパラメーターを定義します。 Insightサー <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> バーへの接続の設定を参照してくださ </a>い。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span> </b> </td> 
   <td colname="col2"> <p>Data Workbenchのプログラムファイルが含まれます。 </p> <p> <p>注意：これらのファイルを削除または変更することはできません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificates </span> </b> </td> 
   <td colname="col2"> Contains the certificate file, <span class="filepath"> trust_ca_cert.pem </span>, and the named user digital certificate for Data Workbench. See <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Downloading and Installing the Digital Certificate </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> 設定 </span> </b> </td> 
   <td colname="col2"> ワークステーションの設定に使用するファイルが含まれます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Geography </span></b> </td> 
   <td colname="col2"> 地理的ビジュアライゼーションのグラフィックレンダリングのためのファイルが含まれます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Trace </span></b> </td> 
   <td colname="col2"> ワークステーションが生成するログファイルが含まれます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Profiles </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>、<i>Predictive Analytics</i> および他のプロファイル設定ファイルが含まれます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> <b><span class="filepath">Software\Insight</span></b> フォルダー内の追加のクライアントコンピューターをインストールするセットアップウィザードです。 </td> 
  </tr> 
 </tbody> 
</table>

