---
description: 障害が原因で Web サーバーがオフラインになった場合、このソリューションは、Log Processing Mode.cfg ファイルを開き、Data Workbenchの ID（この例では WEB2）を「Offline Sources」セクションに追加する適切な権限を持つユーザーが必要となる簡単なソリューションです。
title: 問題の解決
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 問題の解決{#solving-the-problem}

{{eol}}

障害が原因で Web サーバーがオフラインになった場合、このソリューションは、Log Processing Mode.cfg ファイルを開き、Data Workbenchの ID（この例では WEB2）を「Offline Sources」セクションに追加する適切な権限を持つユーザーが必要となる簡単なソリューションです。

ファイルのこのセクションは、 [!DNL data workbench server] 実際にはオフラインなので、このソースからのデータは今後予期されないものにする必要があります。

>[!NOTE]
>
>この変更は、Adobeコンサルタントが実行する必要はありません。 適切な権限を持つユーザーが [!DNL Log Processing Mode.cfg] ファイルがこの変更を加えることができます。

WEB2 がデータの送信を再開し始めた場合、 [!DNL data workbench server] ソースをオンラインに戻し、認識しているすべてのソースから最後にデータを受け取った時刻を反映するように「基準日」の時間を調整します。 つまり、システムに取り込まれる新しいデータは、 [!DNL Log Processing Mode.cfg file].

WEB2 が再びオフラインになった場合は、基準時間が再び停止し、 [!DNL Log Processing Mode.cfg] ファイルを再度作成する必要があります。 これは、基準時の定義に従った、製品のデザインのアーティファクトです。システムが既知のすべてのソースのデータを最後に保持した時刻。

さらに Web サーバー (WEB4、WEB5、WEB6) を追加すると、サーバーは、 [!DNL data workbench server]を使用する場合、 [!DNL data workbench server] 新しいソースを認識する。 システムは、前述のように、これらの新しいソースからのデータを期待する必要があることを単に認識します。
