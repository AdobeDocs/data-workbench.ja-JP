---
description: Web サイトトラフィックから収集されたデータを扱う場合、Sessionize 変換を使用してセッションの定義を指定できます。
title: Sessionize
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
exl-id: bb25cb4b-7185-4524-8ff5-740b672e1cd9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 92%

---

# Sessionize{#sessionize}

Web サイトトラフィックから収集されたデータを扱う場合、Sessionize 変換を使用してセッションの定義を指定できます。

この変換は、タイムスタンプと追跡 ID をその入力として受け取り、ログエントリごとにセッション番号を出力します。特定の追跡 ID を持つ 1 つ目のセッションは「1」に、同じ追跡 ID を持つ 2 つ目のセッションは「2」にというように、セッション番号が 1 つずつ繰り上がります。出力データはセッションごとに一意の値を持つので、セッションキーとしてそのまま使用することができます。

>[!NOTE]
>
>[!DNL Sessionize] 変換が正しく動作するためには、ソースデータにおいて、データが時系列順に並んでおり、追跡 ID ごとにグループ化されている必要があります。したがって、[!DNL Sessionize]は[!DNL Transformation.cfg]ファイルまたは[!DNL Transformation Dataset Include]ファイルで定義されている場合にのみ機能します。

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> デフォルト </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> 変換のわかりやすい名前。ここには任意の名前を入力することができます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）変換についてのメモ。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> この変換が適用される条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Timestamp </td> 
   <td colname="col2"> 使用するタイムスタンプの値が格納されているフィールド。 </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Tracking ID </td> 
   <td colname="col2"> <p>使用する追跡 ID の値が格納されているフィールド。この値は、64 ビット（16 桁）以下の 16 進数か、または 16 桁以下の 10 進整数であることが必要です。 </p> <p> <p>注意：追跡 ID に x-trackingid 以外のフィールドを使用したい場合は、最初にそのフィールドをハッシュ化しておく必要があります。「<a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369">ハッシュ</a>」を参照してください。 </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximum Session Duration </p> </td> 
   <td colname="col2">セッションの最長期間。この期間を超えると、新しいセッションが開始されます（コンテンツが自動的に最新の情報に更新されるよう設定されている Web ページで、際限なく長いセッションが作成されるのを防ぎます）。<span class="wintitle">Timeout Condition</span> が満たされ、かつクリックのリファラーが、Internal Domains パラメーターのいずれかのエントリに設定された場合、Maximum Session Duration を使用してセッションの終了が定義されます。セッション期間は、そこで行われたクリック数に関係なく、指定された Maximum Session Duration が上限となります。推奨値は 48 時間です。Maximum Session Duration パラメーターと Internal Domains パラメーターについて詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Web データの設定</a>. </td> 
   <td colname="col3"> 48 時間 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Session Number </td> 
   <td colname="col2"> セッション番号が格納されるフィールド。このフィールドは、各訪問者のセッションごとに一意の値を持ちます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッションタイムアウト </td> 
   <td colname="col2"> <p>特定の訪問者について、1 セッションの終了（新しいセッションの開始）と見なすログエントリ間の経過時間。つまり、ユーザーの活動期間を定義するための標準的なタイムアウトを表します。このパラメーターの推奨値は 30 分です。Timeout Condition が満たされず、かつクリックのリファラーが、Internal Domains パラメーターのいずれのリファラーにも設定されなかった場合、Session Timeout を使用してセッションの終了が定義されます。 </p> <p> Timeout Condition が満たされ、かつログエントリの cs(referrer-domain) がいずれかの内部ドメインに該当した場合、現在のログエントリを既存のセッションに含めるか、新たに開始したセッションに含めるかは、Maximum Session Duration によって決定されます。 </p> <p> Session Timeout パラメーターについて詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Web データの設定</a>. </p> </td> 
   <td colname="col3"> 30 分 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timeout Condition </td> 
   <td colname="col2"> 新しいセッションの開始と見なすためにログエントリが満たしているべき条件。前のログエントリから、Session Timeout パラメーターの値以上の時間が経過していなければならないことに注意してください。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

次のいずれかの状況に該当する場合、新しいセッションが開始されます。

* 追跡 ID が変化したとき。
* 最後のログエントリからの経過時間が Session Timeout パラメーターの値以上で、なおかつ Timeout Condition が満たされたとき。
* 最後のセッションの 1 つ目のログエントリからの経過時間が、Maximum Session Duration パラメーターの値を超えたとき。

>[!NOTE]
>
>[!DNL Session Parameters.cfg]ファイルのパラメーターとしてMaximum Session DurationとSession Timeoutを既に定義している場合は、設定にこれらの値を入力しないでください。 以下の例に示したように、パラメーターは、*$(parameter name)* と入力することによって参照できます。これらのパラメーターについて詳しくは、 [Web データの設定](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

次の例の [!DNL Sessionize] 変換は、x-timestamp フィールドと x-trackingid フィールドを入力として受け取り、各ログエントリのセッション番号を x-session-key フィールドに記録します。この変換の [!DNL Timeout Condition] には [!DNL Neither] 条件が使用されています。ログエントリの cs(referrer-domain) フィールドが Internal Domains パラメーターのいずれかのドメインと一致した場合、条件が false に評価されます。Internal Domains パラメーターと Session Timeout パラメーターの参照に注目してください。

[!DNL NeitherCondition]について詳しくは、[条件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)を参照してください。 Internal DomainsパラメーターとSession Timeoutパラメーターについて詳しくは、[Webデータの構成設定](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)を参照してください。

![](assets/cfg_TransformationType_Sessionize.png)
