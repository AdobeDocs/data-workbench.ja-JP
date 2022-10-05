---
description: この節では、Data Workbenchデータセットのタイムスタンプを作成する方法について説明します。
title: イベント時刻のセットアップ
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
exl-id: 9632e713-5cf9-4acf-aafa-bfdf79a51ad9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 11%

---

# イベント時刻のセットアップ{#setting-up-event-time}

{{eol}}

この節では、Data Workbenchデータセットのタイムスタンプを作成する方法について説明します。

## イベント時間について {#section-e10ef2b5b6244dc5b215836e3c77d663}

Event Time は、リクエスト（またはイベント）が発生した日時です。

通常、オンラインデータの場合は *x_hit_time_gmt* はタイムスタンプフィールドとして使用されます。 呼び出しの時刻は、オフラインデータ（コールセンターデータなど）のタイムスタンプとして使用できます。 これは必須フィールドで、すべてのデータソースにタイムスタンプとして使用できる 1 つのフィールドが含まれている必要があります。 この情報は、組織から提供される必要があります。

DWB では、次の事前定義済みの変数がタイムスタンプを取り込みます。

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> リクエストがサーバーによって受信された日付と時刻（GMT）。時刻は、1600 年 1 月 1 日からの 100 ナノ秒数で表されます。 </p> <p>例：127710989320000000は <i>x-timestamp</i> 11 の値:28:2005 年 9 月 13 日（火）:52.0000000 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> 形式 YYYY-MM-DD HH:MM:SS.mmm </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> は、1970 年 1 月 1 日 (00) からの秒数を表すエポック時間です:00:01. </td> 
  </tr> 
 </tbody> 
</table>

日付フィールドの形式に基づいて、x-timestamp、x-unixtime、または x-timestring が使用されます。 例えば、受信データの形式が YYYY-MM-DD の場合、x-timestring が使用されます。

タイムスタンプはいずれかの形式で定義され、DWB は内部的に他の 2 つの形式を生成します。 また、これらは事前に定義された DWB フィールドであり、同じ名前を他のフィールドに使用しないでください。

## DWB で定義されたタイムゾーン {#section-3cdd12254342442b917376661e1d9c9f}

日付フィールドに以下のタイムゾーンのいずれかが含まれている場合、DWB はその特定のタイムゾーンで行全体を考慮します。 例えば、あるファイルの日付が2015-01-01 00 と定義されているとします。:00:00 gmt と別のファイルの値は2015-01-01 00 です。:00:00cst の場合、最初のファイルの日付は GMT タイムゾーンで考慮され、2 番目のファイルの日付は CST タイムゾーンで考慮されます。

| コード | タイムゾーン |
|---|---|
| gmt | グリニッジ標準時 |
| est | 東部標準時 |
| edt | 東部夏時間 |
| cst | 中部標準時 |
| cdt | 中部夏時間 |
| mst | 山岳部標準時 |
| mdt | 山地夏時間 |
| pst | 太平洋標準時 |
| pdt | 太平洋夏時間 |

>[!NOTE]
>
>DWB は上記のタイムゾーンのみを処理します。

## カスタムタイムゾーンの設定 {#section-7c351921f22b439b81c73f40d5b47536}

DWB はタイムゾーン内のオフセットを処理しません。 タイムゾーンでのオフセットを考慮するには、そのオフセットタイムゾーンでデータをフォーマットする必要があります。

例：CST タイムゾーンでの日付形式を考慮するには、データは YYYY-MM-DD HH で記述する必要があります。:MM:SS UTC +/-HHMM 形式をクライアントから取得します。

2015-10-18 05:00:00 UTC -0200

## イベント時間/タイムスタンプの設定方法 {#section-81507080f0b44ae6b83d3650ba019812}

日付フィールドの形式に基づいて、 *x-timestamp, x-unixtime* または *x-timestring* 変数が使用されます。 次の例では、 *x-hit_time_gmt* は unix epoc 形式で提供されます。 *x-unixtime* が使用されます。

DWB 内 [!DNL foundation.cfg] ファイル（または、データセットログ処理フォルダーの下にあるその他の設定ファイル）に対して、 Copy 変換を使用して、次に示すようにイベント時間を設定します。

日付フィールドの形式に基づいて、x-timestamp、x-unixtime または x-timestring 変数が使用されます。 以下の例では、x-hit_time_gmt は unix epoc 形式なので、x-unixtime が使用されます。

insight foundation.cfg（または Datasetà ログ処理フォルダーの下のその他の設定）で、 Copy 変換を使用して、次に示すようにイベント時間を設定します。 ![](assets/dwb_impl_timestamp1.png)

の日付が YYYY-MM-DD HH の場合:MM:SS.mmm 形式の場合は x-timestring が使用されます。 ![](assets/dwb_impl_timestamp2.png)例：日付フィールドが YYYY/MM/DD と DWB で定義されていない形式の場合、まず DWB で受け入れられるタイムスタンプ形式の 1 つに書式設定し、対応する変数に割り当てます。 以下のスクリーンショットでは、日付は最初に YYYY-MM-DD 形式に変換され、次に*x-timestring *variable に割り当てられます。 ![](assets/dwb_impl_timestamp3.png)
