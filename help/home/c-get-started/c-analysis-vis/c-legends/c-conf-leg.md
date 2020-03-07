---
description: 信頼性の凡例は、表示されている数字が偶然によるものである可能性を判断したり、データ内に存在する可能性がある偏差を理解するのに役立ちます。
solution: Analytics
title: 信頼性の凡例
topic: Data workbench
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Confidence legends{#confidence-legends}

信頼性の凡例は、表示されている数字が偶然によるものである可能性を判断したり、データ内に存在する可能性がある偏差を理解するのに役立ちます。

データをサンプリングしているのではない場合でも、特定の期間、他の期間のサブセット、完全に信頼できるサブセットから数字を推定することはできません。信頼性の凡例を使用すると、数字が特定の範囲内にある確率を調べられます。

大規模なテストとして現実世界のデータを考えた場合、正確な数字を扱っていても、現実世界にはなお偶然が存在します。例えば、ある火曜日の午前 8 時から午後 12 時の間にトランザクションを完了した人数がわかっても、次の火曜日にまったく同じ数の人がトランザクションを完了するわけではありません。

以下の信頼性の凡例には、コンバージョン指標に関する信頼性の詳細が表示されています。以下の表では、各データポイントの意味を詳しく説明しています。

![](assets/lgd_ConfidenceLegend.png)

<table id="table_387F22C7EF4E4DE9AD810D3D9204676F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>指標または数式 </p> </td> 
   <td colname="col2"> <p>信頼性情報を表示する指標名または指標の式。ワークスペース内に作成した選択範囲が凡例に反映されます。この例では、コンバージョン指標に関する詳細が表示されます。 </p> <p>式の入力に関する構文ルールについては、「<a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f">クエリー言語構文</a>」を参照してください。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>測定した値 </p> </td> 
   <td colname="col2"> <p>収集された実際のデータの値です。この例では、現在の選択範囲に対するコンバージョン率は 2.3 ％です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準偏差 </p> </td> 
   <td colname="col2"> <p>測定した値の標準偏差です。 この例では、現在の選択範囲に対するコンバージョン率の標準偏差は 0.1 ％です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「true」値 </p> </td> 
   <td colname="col2"> <p>測定した値がそれぞれの確率でリストされている範囲内にある可能性。この例では、この「現実社会実験」を何度も繰り返すとすると、測定した値が 2.1 ％と 2.4 ％の間になる可能性は 90 ％です。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>計算の結果を分析する際は、次の点を考慮する必要があります。>
>* 数字は予測です。異なるデータセットで同じ計算を繰り返すと、異なる結果が得られます。これは、ランダム変動として知られています。
>* より高い確率の推定は正規性の前提に依存しますが、この前提はすべての指標に対して正しいとは限りません。 そのため、確率 99 ％の値は、確率 90 ％の値より信頼性が低くなります。
>
>
より正確な数字が必要な場合は、統計の専門家に相談してください。

## 指標または数式の変更 {#section-7f09ff84c3514f26b78d29294e1f03d9}

* In the confidence legend, click in the **[!UICONTROL Metric or Formula]** field and type the desired metric or expression. 式の構文ルールについては、「クエリー言語の構 [文」を参照してくださ](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)い。

## Microsoft Excelにエクスポート {#section-f36e2db7273740b7af278f8a2b79d564}

ウィンドウの書き出しの詳細については、「ウィンドウデータの書き [出し」を参照してくださ](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)い。