---
description: 出力形式の指定に関するガイドラインです。
solution: Analytics
title: 出力形式
topic: Data workbench
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Output format{#output-format}

出力形式の指定に関するガイドラインです。

* 各指標名またはディメンション名は、パーセント記号（%）で開始および終了する必要があります。

   * %XYZ% は、レベルの要素に対応しているディメンション XYZ の要素を指定します。ディメンション XYZ がレベルと 1 対 1 または 1 対多ではない場合、エラーが生成されます。
   * %=XYZ% は、指定されたレベルの要素に対する指標または指標の数式 XYZ の値を指定します。

* 2 語以上のディメンション名にアンダースコアは必要ありません。
* 2 語以上の指標名にはアンダースコアが必要です。

>[!NOTE]
>
>If you hold down the Ctrl key and right-click within the [!DNL Output Format] field, an [!DNL Insert menu] appears. このメニューには、区切り文字としてよく使用される特殊文字（Tab など）の一覧が含まれています。

セグメントのセッション時間データをエクスポートする場合は、Session Duration（セッション時間）指標に基づく新しい指標を作成する必要があります。The new metric, which is for use only with the [!DNL Output Format] field of segment export, enables Microsoft Excel to correctly interpret sessions lasting less than one hour. To create a new session duration metric, open the [!DNL Session Duration.metric] file (from the [!DNL Profile Manager]) and insert a pound sign (#) into the ftime string: [!DNL ftime = string: %#H:%M:%S]

ポンド記号を挿入することにより、1 時間未満のセッション時間の前に &quot;0&quot; が付加されます。その結果、Excel は 0:53:21 を 53 分 21 秒と解釈します。Save the new metric with a different name and upload it to the appropriate profile for others to use by right-clicking the check mark for the file in the [!DNL User] column and clicking **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
