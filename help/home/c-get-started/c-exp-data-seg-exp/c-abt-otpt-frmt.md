---
description: 出力形式の指定に関するガイドラインです。
title: 出力形式
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 63%

---

# 出力形式{#output-format}

出力形式の指定に関するガイドラインです。

* 各指標名またはディメンション名は、パーセント記号（%）で開始および終了する必要があります。

   * %XYZ% は、レベルの要素に対応しているディメンション XYZ の要素を指定します。ディメンション XYZ がレベルと 1 対 1 または 1 対多ではない場合、エラーが生成されます。
   * %=XYZ% は、指定されたレベルの要素に対する指標または指標の数式 XYZ の値を指定します。

* 2 語以上のディメンション名にアンダースコアは必要ありません。
* 2 語以上の指標名にはアンダースコアが必要です。

>[!NOTE]
>
>Ctrlキーを押しながら[!DNL Output Format]フィールド内を右クリックすると、[!DNL Insert menu]が表示されます。 このメニューには、区切り文字としてよく使用される特殊文字（Tab など）の一覧が含まれています。

セグメントのセッション時間データをエクスポートする場合は、Session Duration（セッション時間）指標に基づく新しい指標を作成する必要があります。新しい指標は、セグメントエクスポートの[!DNL Output Format]フィールドでのみ使用され、Microsoft Excelが1時間未満のセッションを正しく解釈できるようにします。 新しいセッション期間指標を作成するには、[!DNL Profile Manager]から[!DNL Session Duration.metric]ファイルを開き、ポンド記号(#)をftime文字列に挿入します。[!DNL ftime = string: %#H:%M:%S]

ポンド記号を挿入することにより、1 時間未満のセッション時間の前に &quot;0&quot; が付加されます。その結果、Excel は 0:53:21 を 53 分 21 秒と解釈します。新しい指標を別の名前で保存し、適切なプロファイルにアップロードして、他のユーザーが使用できるようにします。そのためには、[!DNL User]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL profile name]***&#x200B;をクリックします。
