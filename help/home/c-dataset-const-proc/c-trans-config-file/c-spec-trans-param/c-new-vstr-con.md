---
description: New Visitor Condition は、データセットへの組み入れ候補となる訪問者を判別するために使用される条件演算です。
solution: Analytics
title: New Visitor Condition
topic: Data workbench
uuid: e9733109-5bf3-47ce-974c-d68264291f19
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# New Visitor Condition{#new-visitor-condition}

New Visitor Condition は、データセットへの組み入れ候補となる訪問者を判別するために使用される条件演算です。

[!DNL New Visitor Condition] は、訪問者の（時系列順に並んだ）最初のログエントリを定義するものです。それ以降は、その訪問者のすべてのログエントリが、この条件を満たしているかどうかに関係なくデータセットに組み入れられるようになります。[!DNL New Visitor Condition] のためには、データが訪問者別および時系列順に並んでいる必要があるので、データセット構築の変換段階でしか適用できません。

次の例の [!DNL New Visitor Condition] では、電子メールキャンペーンに反応した訪問者のログエントリのみを含んだデータセットを作成しています。そのために、[!DNL NotEmptyCondition] テスト（[Not Empty](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8) を参照）と [!DNL x-campaign-email] フィールド（正規表現への入力として）が使用されています。その条件を満たした新しい訪問者が特定されると、以降、その訪問者のすべてのログエントリが収集されます。

![](assets/cfg_Transformation_NewVisitorCondition.png)

