---
description: クエリー文字列のグループ化を使用すると、大量のフィールドを統合することができます。
title: クエリ文字列のグループ化
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
exl-id: 4052cf7e-abdf-4e16-9f42-521c4e719786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 84%

---

# クエリ文字列のグループ化{#query-string-grouping}

{{eol}}

クエリー文字列のグループ化を使用すると、大量のフィールドを統合することができます。

クエリー文字列のグループ化は、各プロファイルに固有のものですが、この例に示すように変換でうまく機能します。

1. カスタム設定ファイル ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]) をクリックし、変換タイプを追加する *BuildNameValuePair* をパラメーターとして使用します。

   ```
   2 = BuildNameValuePair:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to build)
             Name = string: Custom Events 
             Output = string: x-event-list       
   ```

1. カスタム設定ファイル（[!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]）を追加し、変換タイプ *ExtractNameValuePairs* をパラメーターとして追加して、使用するフィールドに圧縮されたデータを展開するための新しいファイルを作成します。

   ```
   2 = ExtractNameValuePairs:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Field = string: x-event-list 
         Name = string: Custom Events 
         Output Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to extract) 
             Name = string: Custom Events 
             Output = string: x-event-list   
   ```

## 他の用途 {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

カスタム eVar、prop および変数に多くの項目がある場合、ログの処理中に名前と値のペアを構築して、レポート上で項目をグルーピングすることができます。例えば、名前と値のペアを結合したフィールドを作成して、[!DNL tempDB] ファイルのサイズを小さくすることができます。

![](assets/query_string_grouping.png)
