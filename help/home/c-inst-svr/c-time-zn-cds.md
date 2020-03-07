---
description: Insightサーバーでの時間ベースのパラメーターに関する手順の形式設定を参照してください。
solution: Insight
title: タイムゾーンのコード
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# タイムゾーンのコード{#time-zone-codes}

Insightサーバーでの時間ベースのパラメーターに関する手順の形式設定を参照してください。

の時間ベースのパラメーターのほ [!DNL Insight Server] とんどは、次の形式で指定します。

*Month DD, YYYY HH:MM:SS TimeZone*

例：August 13, 2013 22:30:00 EST

タイムゾーンの表現には、システムに依存しない次の形式（協定世界時）が使用されます。

UTC +hhmm *dstrules*

記号（+）の部分にはプラス（+）記号かマイナス（-）記号を、*hhmm* には UTC からのオフセット（時と分）を指定します。*dstrules* は、夏時間などの時刻調整制度を導入するための一連のルールを指定する変数です（省略可能）。

*dstrules*( *&lt;[!DNL dstrules]>*[!DNL .dst] )を指定する場合、Baseプロファイル（特定のデータセットに関連付けられていない設定ファイルの場合）またはデータセットプロファイル（データセット固有の設定ファイルの場合）のDataset\TimeZoneディレクトリ内に、&lt;>という名前のタブ区切りファイルが存在する必要があります。 タイムゾーンに依存しない、夏時間の一連のルールをこのファイルで指定します。一連のルールは、年度ごとに異なっていても構いません。アドビが提供している [!DNL DST.dst] ファイル（Base プロファイル内）には、2005 年エネルギー政策法（2007 年より施行）によって定められた米国の標準ルールと、それ以前の年度用の米国ルールが指定されています。

タイムゾーンの指定例を次に示します。

* 米国東部夏時間：Time Zone = string: UTC -0500 DST
* UTC time with no offset and no *dstrules* (corresponding to GMT): Time Zone = string: UTC -0000

When this format is used, the system time zone of [!DNL Insight Server], [!DNL Insight], and [!DNL Report] machines need not be the same as the specified time zone. In addition, all active dataset profiles on an [!DNL Insight Server] machine need not have the same time zone setting.

次の表は、時刻ベースのパラメーターでタイムゾーンの指定に使用できるコードを一覧にしたものです。

## タイムゾーンコード表 {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>If you are implementing Daylight Saving Time or a similar clock-shifting policy, you must save the [!DNL .dst] file containing the appropriate rules in the *profile name*\Dataset\Timezone directory on the [!DNL Insight Server] machine.

| コード | タイムゾーン | GMT からのオフセット |
|---|---|---|
| gmt | グリニッジ標準時 | 0 |
| est | 東部標準時 | 5 |
| edt | 東部夏時間 | 5 |
| cst | 中部標準時 | 6 |
| cdt | 中部夏時間 | 6 |
| mst | 山岳部標準時 | 7 |
| mdt | 山地夏時間 | 7 |
| pst | 太平洋標準時 | 8 |
| pdt | 太平洋夏時間 | 8 |

