---
description: 拡張ディメンションの作成手順を紹介するとともに、データセット構築の変換段階での作成用に定義可能な拡張ディメンションのタイプについて説明します。
solution: Analytics
title: 拡張ディメンション
topic: Data workbench
uuid: 465682c2-5b08-4b94-817f-ff7b405142af
translation-type: tm+mt
source-git-commit: d892186621e7acb9504254496b038efc3e9fd8ec

---


# 拡張ディメンション{#extended-dimensions}

拡張ディメンションの作成手順を紹介するとともに、データセット構築の変換段階での作成用に定義可能な拡張ディメンションのタイプについて説明します。

Insight サーバーによって使用されるディメンションには、派生ディメンションというカテゴリーに属するものもあります。その名前からわかるように、派生ディメンションは、既存の拡張ディメンションまたは拡張指標から作成されます。You do not define derived dimensions within a [!DNL Transformation Dataset Configuration] file as you do extended dimensions. Instead, you define them as individual [!DNL .dim] files within an inherited profile or a data set profile.

派生ディメンションの作成手順について詳しくは、[拡張ディメンション](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/profile-mgr/c-dvrd-dim.html)を参照してください。
