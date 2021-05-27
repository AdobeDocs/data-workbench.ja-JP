---
description: Insightサーバーでの時間ベースのパラメーターに関する手順の形式を設定します。
title: タイムゾーンのコード
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 55%

---

# タイムゾーンのコード{#time-zone-codes}

Insightサーバーでの時間ベースのパラメーターに関する手順の形式を設定します。

[!DNL Insight Server]内の時間ベースのパラメーターのほとんどは、次の形式で指定されます。

*月DD、YYYY HH:MM:SS TimeZone*

例：August 13, 2013 22:30:00 EST

タイムゾーンの表現には、システムに依存しない次の形式（協定世界時）が使用されます。

UTC +hhmm *dstrules*

記号（+）の部分にはプラス（+）記号かマイナス（-）記号を、*hhmm* には UTC からのオフセット（時と分）を指定します。*dstrules* は、夏時間などの時刻調整制度を導入するための一連のルールを指定する変数です（省略可能）。

*dstrules*&#x200B;を指定する場合、*&lt; [!DNL dstrules]* [!DNL .dst]というタブ区切りファイルが、（特定のデータセットに関連付けられていない設定ファイルの）BaseプロファイルまたはデータセットプロファイルのDataset\TimeZoneディレクトリ内に存在する必要があります。 タイムゾーンに依存しない、夏時間の一連のルールをこのファイルで指定します。一連のルールは、年度ごとに異なっていても構いません。アドビが提供している [!DNL DST.dst] ファイル（Base プロファイル内）には、2005 年エネルギー政策法（2007 年より施行）によって定められた米国の標準ルールと、それ以前の年度用の米国ルールが指定されています。

タイムゾーンの指定例を次に示します。

* 米国東部夏時間：Time Zone = string: UTC -0500 DST
* オフセットなし、*dstrules*&#x200B;なしのUTC時間（GMTに対応）:Time Zone = string:UTC -0000

この形式を使用する場合、[!DNL Insight Server]、[!DNL Insight]、[!DNL Report]の各マシンのシステムタイムゾーンを、指定したタイムゾーンと同じにする必要はありません。 また、[!DNL Insight Server]マシン上のすべてのアクティブなデータセットプロファイルに同じタイムゾーン設定を設定する必要はありません。

次の表は、時刻ベースのパラメーターでタイムゾーンの指定に使用できるコードを一覧にしたものです。

## タイムゾーンコード表 {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>夏時間などの時刻調整制度を導入する場合は、*profile name*\Dataset\Timezone directory on the [!DNL Insight Server]マシンに適切なルールを含む[!DNL .dst]ファイルを保存する必要があります。

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
