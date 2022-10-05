---
description: Data Workbenchの実装時に、マーケティング環境に適したビジネス上の質問を収集し、説明します。
title: Data Workbench 実装のための発見と要件
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
exl-id: 25cc2940-800a-4ad2-a7bb-c343e3d65500
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 9%

---

# Data Workbench 実装のための発見と要件{#data-workbench-discovery-and-requirements}

{{eol}}

Data Workbenchの実装時に、マーケティング環境に適したビジネス上の質問を収集し、説明します。

このセクションでは、Data Workbench(DWB) でのソリューションの考案に必要な質問やタスクに関する入力を収集できます。これらの質問には、明確に、テクノロジーに依存せず、ビジネス用語やAdobe Analytics Premiumソリューションの参照を提供します。 このセクションでは、これらの目標と関連する要件に関する情報を提供します。

## フェーズ 1:主なビジネス目標 {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

次の表では、顧客ベースを特定し、DWB 実装の構造を分析するように求められます。

* カスタマーベースについて
* 特定のビジネス事例について（セルフサービスと他のデータチャネル/オフラインデータソースの有効性など）

**カスタマーベースについて**

お客様がサイトを利用する理由、直面する課題、DWB がビジネスモデルに基づいてお客様を支援する方法を理解します。 例えば、他の製品やサービスをクロスセルするための顧客の測定、監視、分析方法、アクティブなユーザーとアカウントの浸透率のリスト、その他の目標を取得する方法などです。

| ID | ビジネス上の質問/要件 | 優先度 | フェーズ | 依存関係 |
|---|---|---|---|---|
| 1a | 特定のビジネスに関する質問 1 | 高/中/低 | 1 | 共通キー（他のキーなどに依存） |
| 1b | 特定のビジネスに関する質問 2 | 高 | 1 | 任意の依存関係 |

解析構成

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">Workspace Analysis データソース</td> 
   <td colname="col2"> ワークスペース名を追加 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Workspace のDimensionと指標が必要 </p> </td> 
   <td colname="col2"> <p>Dimensionの特定： </p> <p>指標の特定： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Workspace のフィルター、フラグ、および必要なツール </td> 
   <td colname="col2"> <p>セグメントの特定： </p> <p>ツールの指定： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> この分析からは、どのようなアクションを導き出すことができますか？ </td> 
   <td colname="col2"> 特定の DWB ワークスペースを使用して、タスクとコンテンツを理解します。 </td> 
  </tr> 
 </tbody> 
</table>

## フェーズ 2:特定のビジネスケースについて {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

他のデータソースやチャネルを理解し、これらがビジネスケースとどのように関連するかを学びます。

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> ビジネスに関する質問/要件 </th> 
   <th colname="col3" class="entry"> 優先度 </th> 
   <th colname="col04" class="entry"> フェーズ </th> 
   <th colname="col4" class="entry"> 依存関係 </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> 特定のビジネス要件 1 </td> 
   <td colname="col3"> <p>高/中/低 </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>共通キー（他のキー、アカウントのフラグ/識別子などに応じて異なる） </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>特定のビジネス要件 2 </p> </td> 
   <td colname="col3"> 高/中/低 </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>依存関係 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**解析構造**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">Workspace Analysis データソース
     </td> 
   <td colname="col2">
     サンプルのワークスペース名 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Workspace のDimensionと指標が必要 </p> </td> 
   <td colname="col2"> <p>Dimension:必要なディメンションを定義します。 </p> <p>指標：必要な指標を定義します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Workspace のフィルター、フラグ、および必要なツール </td> 
   <td colname="col2"> <p>セグメント：顧客セグメントを特定する。 </p> <p>ツール：必要なツールを選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> この分析からは、どのようなアクションを導き出すことができますか？ </td> 
   <td colname="col2"> このワークスペースから理解すべきこと </td> 
  </tr> 
 </tbody> 
</table>

**データソース**

| データソース | 優先度 | データはどのくらいの頻度で受信されますか？ |
|---|---|---|
| サイト 1 名レポートスイート (RSID) | 1 | 1 時間ごと |
| サイト 2 名（存在する場合） (RSID) | 1 | 1 時間ごと |
| データソース 1（該当する場合） | 2 | 毎日? |
| データソース 2（該当する場合） | 3 | 毎日? |
