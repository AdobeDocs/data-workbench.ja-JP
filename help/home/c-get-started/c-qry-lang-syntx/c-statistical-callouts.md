---
description: 統計コールアウトでは、オーディエンスクラスタリングや訪問者の反応スコアリングにおけるより高度なデータマイニング機能のために、意味のある関係を測定して、隠れた機会や関心のある変数を特定します。
title: 統計コールアウト
uuid: 04911ac4-bc3f-4813-800b-087d9668a782
exl-id: d4ed540e-f837-4db9-a81e-b8a30c15f270
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 95%

---

# 統計コールアウト{#statistical-callouts}

{{eol}}

統計コールアウトでは、オーディエンスクラスタリングや訪問者の反応スコアリングにおけるより高度なデータマイニング機能のために、意味のある関係を測定して、隠れた機会や関心のある変数を特定します。

統計コールアウトは、2 項変数（はい／いいえ、0／1 または購入者／非購入者）を可算指標（訪問回数、注文件数またはダウンロード）と相関させるなど、より多くのタイプのデータを相関させることができるようにアルゴリズムを拡張します。

統計コールアウトを追加するには：

1. テーブルで、指標ヘッダーを右クリックします。
1. 選択 **[!UICONTROL Statistics]** 必要な各設定のチェックマークをオンまたはオフにします。 デフォルト設定では、「引き出し線を表示」のすべてが選択されています。

   ![](assets/statistical_callouts.png)

コールアウトでは、統計値をデータセット列に分けて返すことができます。

<table id="table_B2A4F9D5938D4756A81ACF6F4D77E63D">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 計算 </th>
   <th colname="col2" class="entry"> 説明 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> カウント </td>
   <td colname="col2"><p>データセットの行数を返します。 </p></td>
  </tr>
  <tr>
   <td colname="col1"> 最大 </td>
   <td colname="col2"><p> ディメンションのすべてのエレメントの最大指標値を示します。 </p></td>
  </tr>
  <tr>
   <td colname="col1"> 最小 </td>
   <td colname="col2"><p> ディメンションのすべてのエレメントの最小指標値を示します。 </p></td>
  </tr>
  <tr>
   <td colname="col1"> 平均値 </td>
   <td colname="col2"><p> 平均は、ディメンションのエレメントの指標値の合計をカウント数で割る（合計/カウント数）ことによって算出します。 </p></td>
  </tr>
  <tr>
   <td colname="col1"> 標準偏差 </td>
   <td colname="col2"> 標準偏差は、予想される平均からのばらつきの大きさを示すものです。標準偏差の値が小さいほど、各データポイントが平均に近いことになります。逆に、標準偏差の値が大きいほど、各データポイントが幅広い値に分散していることになります。 </td>
  </tr>
  <tr>
   <td colname="col1"> 合計 </td>
   <td colname="col2"><p> 指標値の合計を返します。 </p></td>
  </tr>
  <tr>
   <td colname="col1"> 平方偏差 </td>
   <td colname="col2"><p> そのディメンションの指標平均から測定した指標値の平方偏差。これは、標準偏差の 2 乗に等しくなります。 </p></td>
  </tr>
 </tbody>
</table>
