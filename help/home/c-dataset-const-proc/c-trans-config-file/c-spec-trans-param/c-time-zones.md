---
description: 時間ディメンション、時刻の変換（x-local-timestring フィールドの定義など）、データセットプロファイル内の全ローカル時間の書式設定は、Transformation.cfg ファイルの Time Zone パラメーターによって制御されます。
title: タイムゾーン
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 85%

---

# タイムゾーン{#time-zones}

{{eol}}

時間ディメンション、時刻の変換（x-local-timestring フィールドの定義など）、データセットプロファイル内の全ローカル時間の書式設定は、Transformation.cfg ファイルの Time Zone パラメーターによって制御されます。

>[!NOTE]
>
>Time Zone パラメーターは、ステータスやイベントログのタイムスタンプなど、システムレベルの機能には影響しません。タイムスタンプはシステムのローカル時間で表されます。

Time Zone パラメーターでは、システムに依存しない、次のタイムゾーン形式（「協定世界時」）がサポートされます。

Time Zone = string: UTC +hhmm dstrules

記号（+）の部分にはプラス（+）記号かマイナス（-）記号を、*hhmm* には UTC からのオフセット（時と分）を指定します。*dstrules* は、夏時間などの時刻調整制度を導入するための一連のルールを指定する変数です（省略可能）。

*dstrules* を指定する場合、[!DNL dstrules .dst] という名前のタブ区切りファイルがデータセットプロファイルの Dataset\TimeZone サブディレクトリに存在している必要があります。タイムゾーンに依存しない、夏時間の一連のルールをこのファイルで指定します。一連のルールは、年度ごとに異なっていても構いません。アドビが提供している [!DNL DST.dst] ファイル（Base プロファイル内）には、2005 年エネルギー政策法（2007 年より施行）によって定められた米国の標準ルールと、それ以前の年度用の米国ルールが指定されています。

タイムゾーンの指定例を次に示します。

* 米国東部夏時間：Time Zone = string: UTC -0500 DST
* オフセットと dstrules を指定しない UTC 時刻：Time Zone = string: UTC -0000

この形式を使用する場合に、Data Workbench サーバー、Data Workbench コンピューター、[!DNL Report] コンピューターのシステムタイムゾーンを、指定したタイムゾーンに揃える必要はありません。また、Data Workbench サーバーコンピューター上で使用されているデータセットプロファイルについても、タイムゾーン設定をすべて揃える必要はありません。

1 台の Data Workbench サーバーコンピューターまたは 1 つの Data Workbench サーバークラスター上で複数のデータセットプロファイルを実行することはできるだけ避けてください。

Data Workbench のユーザーに表示されるデータには、そのシステムのタイムゾーンではなく、データセットプロファイルのタイムゾーンが使用されます。Data Workbench サーバーコンピューターのシステムタイムゾーンは、そのデータセットに使用されるタイムゾーンと揃えることをお勧めします。

>[!NOTE]
>
>Time Zone パラメーターは、 [!DNL Log Processing.cfg] ファイル。ログ処理時の時間の変換に使用されます。 Time Zone パラメーターについて詳しくは、 [!DNL Log Processing.cfg] ファイル： [ログ処理設定ファイル](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
