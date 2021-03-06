---
description: ロケールに合わせて正しく表示されるように時間ディメンションを設定します。
title: 時間ディメンションのローカライズ
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# 時間ディメンションのローカライズ{#localizing-time-dimensions}

ロケールに合わせて正しく表示されるように時間ディメンションを設定します。

You can configure the displayed format of time dimensions based on locale in the **[!DNL Standard Time Dimensions.cfg]** file (located by default at **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard Time Dimensions.cfg]**).

For example, in North America you can express the date May 3rd, 2015 as 5/3/15, or **`%m/%d/%y`**. However, in other parts of the world this could be interpreted as `%d/%m/%y`, or March 5th, 2015 due to an ambiguity in the values. このような状況を回避するため、管理者はロケール内のユーザーの期待に合うように表示形式を変更できます。

## 1. Override Default Time Dimensions in Standard Time Dimensions.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

この機能を有効にするには、管理者が既存の時間ディメンションを編集するか、パラメーターを追加して新しい時間ディメンションを作成して、デフォルト値をオーバーライドする必要があります。

時間ディメンションの変更例を以下に示します。

この例では、Week、Hour、Day、Month および Hour of Day の **Format** の値はデフォルトに設定されています。

>[!NOTE]
>
>これらの行を省略した場合、Data Workbenchの動作は変更されず、ディメンションはデフォルトを使用してコンパイルされます。

```
Transformation Include = TransformationInclude:  
  Extended Dimensions = vector: 1 items 
    0 = TimeDimensions:  
      Comments = Comment: 0 items 
      Dimensions = map:  
        Day = string: Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Hour of Day = string: Hour of Day 
        Month = string: Month 
        Week = string: Week 
      Hidden = bool: false 
      Input Time (1970 epoch) = string: x-unixtime 
      Week Format = string:  
  %m/%d/%y
      Hour Format = string:  
  %x %H:%M 
      Day Format = string:  
  %x
      Month Format = string:  
  %b '%y
      Hour Of Day Format = string:  
  %#H:%M
      Name = string: Visit Time 
      Parent = string: Visit 
      Week Start Day = string: Mon 
  Transformations = vector: 0 items
```

![](assets/6_4_time_format.png)

## 2. meta.cfg ファイルの設定 {#section-5e077d3298dd48fda7f7bb16af9ea00c}

さらに、パッケージ管理者は、以下のパラメーターとそのデフォルト値をプロファイルの **[!DNL meta.cfg]** ファイルに追加する必要があります。これによって、ワークステーションからの編集が可能になります。

設定済みの **[!DNL meta.cfg]** ファイルの抜粋を以下に示します。

```
dimensions = vector: 6 items 
  0 = Template: 
    ...
  ...
  5 = Template: 
    name = string: Time Dimensions 
    value = TimeDimensions: 
      Name = string:  
      Comments = Comment: 0 items 
      Hidden = bool: false 
       
  Week Format = string: %d/%m/%y 
       Hour Format = string: %x %H:%M 
       Day Format = string: %x 
       Month Format = string: %b '%y 
       Hour Of Day Format = string: %#H:%M</b> 
      Input Time (1970 epoch) = string:  
      Parent = string:  
      Week Start Day = string: Mon 
      Dimensions = map: 
        Hour of Day = string: Hour of Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Day = string: Day 
        Week = string: Week 
        Month = string: Month
```

ワークステーションの **[!DNL meta.cfg]** ファイルの例を以下に示します。

![](assets/dwb_time_format.png)

これで、管理者は、時間ディメンションが設定されているファイル（**など）を**&#x200B;ファイルマネージャー&#x200B;**[!DNL Standard Time Dimensions.cfg]**&#x200B;から開き、ワークステーションで編集することができます。
