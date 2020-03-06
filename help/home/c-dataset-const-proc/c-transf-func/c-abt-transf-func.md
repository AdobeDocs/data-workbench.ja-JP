---
description: 変換機能（Transform）は、ログソースデータを他のアプリケーションで使用できるようエクスポートすることを目的に、Data Workbench サーバーコンピューター上で実行されます。
solution: Analytics
title: 変換機能について
topic: Data workbench
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 変換機能について{#about-transformation-functionality}

変換機能（Transform）は、ログソースデータを他のアプリケーションで使用できるようエクスポートすることを目的に、Data Workbench サーバーコンピューター上で実行されます。

[!DNL Transform] は、ファイ [!DNL .vsl] ル、ログファイル、XMLファイル、ODBCデータを読み取り、DataWarehouseの読み込みルーチン、監査機関、または他のターゲットで使用できるファイル、テキストフ [!DNL .vsl] ァイル、区切り文字付きテキストファイルとしてデータを書き出すことができます。 データの抽出と変換は、常時実行できるほか、スケジュールに基づいて実行することもできます。

>[!NOTE]
>
>Typically, [!DNL Transform] is configured on a data workbench server FSU. ただし、実際の導入条件によっては、Data Workbench サーバーの DPU に対して設定することが必要になる場合もあります。詳しくは、アドビにお問い合わせください。

[!DNL Transform] のメモリ使用量に関する情報は、「詳細なステータス」インターフェイスで確認できます。詳しくは、『*Data Workbench ユーザーガイド*』の「管理インターフェイス」という章を参照してください。

アドビのアプリケーションからデータを書き出すもうひとつの方法として、セグメント エクスポート機能があります。[!DNL Transform] では、未処理のデータを外部ターゲットにエクスポートできるのに対し、セグメントエクスポート機能では、データセットから処理済みのデータを出力することができ、エクスポートするデータをデータセット内でディメンションとして定義しておく必要があります。セグメントのエクスポートについて詳しくは、『*Data Workbench ユーザーガイド*』を参照してください。
