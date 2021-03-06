---
description: 拡張ディメンションの作成手順を紹介するとともに、データセット構築の変換段階での作成用に定義可能な拡張ディメンションのタイプについて説明します。
title: 拡張ディメンション
uuid: 465682c2-5b08-4b94-817f-ff7b405142af
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 70%

---


# 拡張ディメンション{#extended-dimensions}

拡張ディメンションの作成手順を紹介するとともに、データセット構築の変換段階での作成用に定義可能な拡張ディメンションのタイプについて説明します。

Insight サーバーによって使用されるディメンションには、派生ディメンションというカテゴリーに属するものもあります。その名前からわかるように、派生ディメンションは、既存の拡張ディメンションまたは拡張指標から作成されます。拡張ディメンションとは異なり、[!DNL Transformation Dataset Configuration]ファイル内で派生ディメンションを定義することはできません。 代わりに、継承されたプロファイルまたはデータセットプロファイル内の個々の[!DNL .dim]ファイルとして定義します。

派生ディメンションの作成手順について詳しくは、[拡張ディメンション](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/profile-mgr/c-dvrd-dim.html)を参照してください。
