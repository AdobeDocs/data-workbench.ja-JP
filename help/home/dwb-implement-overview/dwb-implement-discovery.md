---
description: Data Workbenchの導入時に、マーケティング環境に適したビジネスの質問を収集し、説明します。
title: Data Workbenchの検出と要件
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Data Workbenchの検出と要件{#data-workbench-discovery-and-requirements}

Data Workbenchの導入時に、マーケティング環境に適したビジネスの質問を収集し、説明します。

この節では、Data Workbench(DWB)でソリューションを作成するために必要な質問とタスクに関する入力を収集し、これらの質問を正確かつ明確に、技術に依存しない方法で、ビジネス用語とAdobe Analytics Premiumソリューションの参照を提供します。 この節では、これらの目標と関連する要件について説明します。

## 第1段階：主なビジネス目標 {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

次の表に、お客様の基盤を特定し、DWB実装の構築を分析するよう求めるプロンプトを示します。

* お客様の基盤について
* 特定のビジネス事例を理解する（例えば、セルフサービスや他のデータチャネル/オフラインデータソースの効果）

**顧客ベースについて**

お客様がサイトを利用する理由、直面する課題、DWBが貴社のビジネスモデルに基づいてどのように役立つかを把握する。 例えば、顧客を測定、監視、分析し、他の製品やサービスをクロス販売する方法や、アクティブなユーザー、アカウントの浸透率、その他の目標のリストを取得する方法を示します。

| ID | ビジネスの質問/要件 | 優先度 | フェーズ | 依存関係 |
|---|---|---|---|---|
| 1a | 特定のビジネスの質問1 | 高/中/低 | 1 | 共通キー。他のキーに依存します。 |
| 1b | 特定のビジネスの質問2 | 高 | 1 | 任意の依存関係 |

解析構築

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">Workspace分析データソース</td> 
   <td colname="col2"> ワークスペース名の追加 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ワークスペースのディメンションと指標が必要 </p> </td> 
   <td colname="col2"> <p>ディメンションの指定： </p> <p>指標の特定： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 必要なワークスペースフィルター、フラグ、ツール </td> 
   <td colname="col2"> <p>セグメントの特定： </p> <p>ツールの特定： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> この分析からどのようなアクションが得られますか。 </td> 
   <td colname="col2"> 特定のDWBワークスペースを使用して、タスクとコンテンツを理解します。 </td> 
  </tr> 
 </tbody> 
</table>

## 第2段階：特定のビジネス事例について {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

他のデータソースやチャネルを理解し、ビジネス事例との関連を学びます。

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> ビジネスの質問/要件 </th> 
   <th colname="col3" class="entry"> 優先度 </th> 
   <th colname="col04" class="entry"> フェーズ </th> 
   <th colname="col4" class="entry"> 依存関係 </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> 特定のビジネス要件1 </td> 
   <td colname="col3"> <p>高/中/低 </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>共通キー。他のキーに依存し、アカウントのフラグ/識別子など。 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>特定のビジネス要件2 </p> </td> 
   <td colname="col3"> 高/中/低 </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>任意の依存関係 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**解析構造**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">Workspace分析データソース
     </td> 
   <td colname="col2">
     ワークスペース名の例 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ワークスペースのディメンションと指標が必要 </p> </td> 
   <td colname="col2"> <p>ディメンション：必要なディメンションを定義します。 </p> <p>指標：必要な指標を定義します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 必要なワークスペースフィルター、フラグ、ツール </td> 
   <td colname="col2"> <p>セグメント：顧客セグメントを特定します。 </p> <p>ツール：必要なツールを選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> この分析からどのようなアクションが得られますか。 </td> 
   <td colname="col2"> このワークスペースから理解すべきこと </td> 
  </tr> 
 </tbody> 
</table>

**データソース**

| データソース | 優先度 | データの受信頻度 |
|---|---|---|
| サイト1名レポートスイート(RSID) | 1 | 1 時間ごと |
| サイト2名（存在する場合）(RSID) | 1 | 1 時間ごと |
| データソース1（該当する場合） | 2 | 毎日? |
| データソース2（該当する場合） | 3 | 毎日? |
