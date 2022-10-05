---
description: デシジョンツリーメニューには、ポジティブユースケース、フィルター、リーフ配分オプション、混同行列などの高度なオプションを設定する機能が用意されています。
title: デシジョンツリーのオプション
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
exl-id: e139562d-4613-4159-a858-2a78a2e896dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 100%

---

# デシジョンツリーのオプション{#decision-tree-options}

{{eol}}

デシジョンツリーメニューには、ポジティブユースケース、フィルター、リーフ配分オプション、混同行列などの高度なオプションを設定する機能が用意されています。

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ツールバーのボタン </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 移動 </td> 
   <td colname="col2"> クリックすると、デシジョンツリーアルゴリズムが実行され、ビジュアライゼーションが表示されます。これは、入力があるまで、グレー表示です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> リセット </td> 
   <td colname="col2"> 入力とデシジョンツリーモデルをクリアし、プロセスをリセットします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 保存 </td> 
   <td colname="col2"><b>デシジョンツリーを保存します</b>。デシジョンツリーは、様々な形式で保存できます。 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">予測マークアップ言語（<b>PMML</b>）：アプリケーションでデシジョンツリーモデルを記述および交換するために使用される XML ベースのファイル形式。 </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55">true または false、パーセンテージ、メンバーの数および入力値のシンプルな列と行を表示する<b>テキスト</b>。 </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57"><b>ディメンション</b>と、予測結果のエレメントに対応する分岐。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> オプション </td> 
   <td colname="col2"> オプションメニューについては、以下の表を参照してください。 </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプションメニュー </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ポジティブケースを設定 </td> 
   <td colname="col2"> 現在のワークスペースの選択をモデルのポジティブケースとして定義します。何も選択されていない場合は、ケースをクリアします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 母集団フィルターを設定 </td> 
   <td colname="col2"> 現在のワークスペースの選択をモデルの母集団フィルターとして定義し、この条件を満たす訪問者から取得します。デフォルトは「全員」です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 複雑なフィルターの説明を表示 </td> 
   <td colname="col2"> 定義されたフィルターの説明を表示します。クリックすると、ポジティブケースと母集団フィルターのフィルタースクリプトが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ノードを非表示 </td> 
   <td colname="col2"> 母集団の割合が小さいノードを非表示にします。このメニューコマンドは、デシジョンツリーが表示されているときにのみ表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 混同行列 </td> 
   <td colname="col2"> <p><span class="uicontrol">オプション</span>／<span class="uicontrol">混同行列</span>をクリックすると、正解率、再現率、精度、F-スコアの値が表示されます。100％に近いほど、よいスコアです。 </p> <p>混同行列は、次の値の組み合わせを使用して、モデルの正解率の 4 カウントを付与します。 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">実際の陽性（AP） </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">予測された陽性（PP） </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">実際の陰性（AN） </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">予測された陰性（PN） </li> 
     </ul> </p> <p>ヒント：これらの数は、真の正解とわかっている 20％を差し引いた検定データに、結果のスコアリングモデルを適用することで取得されます。スコアが 50％を超える場合、（定義されたフィルターに一致する）ポジティブケースとして予測されます。このとき、正解率 = (TP + TN)/(TP + FP + TN + FN)、再現率 = TP / (TP + FN)、精度 = TP / (TP + FP) です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 凡例を表示 </td> 
   <td colname="col2">デシジョンツリーの凡例キーのオンとオフを切り替えることができます。<img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />このメニューコマンドは、デシジョンツリーが表示されているときにのみ表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アドバンス </td> 
   <td colname="col2"> クリックすると、デシジョンツリーを細かく制御するための詳細メニューが開きます。メニューオプションについては、以下の表を参照してください。 </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 詳細メニュー </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> トレーニングセットサイズ </td> 
   <td colname="col2"> <p>モデルの構築に使用するトレーニングセットのサイズを制御します。セットが大きいほどトレーニングの時間は長くなり、セットが小さいほど時間は短くなります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 入力の正規化 </td> 
   <td colname="col2"> <p> 最小 - 最大と Z-スコア手法のどちらを使用してモデルへの入力を正規化するかをユーザーが指定できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMOTE オーバーサンプリング係数 </td> 
   <td colname="col2"> トレーニングサンプルでポジティブケースがあまり頻繁に発生しない（10％未満の）場合、SMOTE を使用して、追加のサンプルを提供します。このオプションを使用すると、ユーザーが SMOTE を使用して追加作成するサンプルの数を指定することができます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> リーフクラス配分しきい値 </td> 
   <td colname="col2"> ツリー構築処理時にリーフとして想定されるしきい値を設定できます。デフォルトでは、ノードがリーフになるには、（プルーニングステージの前に）そのノードのすべてのメンバーが同一である必要があります。 </td> 
  </tr> 
 </tbody> 
</table>
