---
description: Report Portal で使用可能にするプロファイルを指定するには、profiles.xml ファイルを設定する必要があります。
title: Profiles.xml ファイルの編集
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%

---

# Profiles.xml ファイルの編集{#edit-the-profiles-xml-file}

{{eol}}

Report Portal で使用可能にするプロファイルを指定するには、profiles.xml ファイルを設定する必要があります。

この [!DNL profiles.xml] ファイルは、出力用に指定したフォルダー内に存在します。 デフォルトでは、このファイルは\*PortalName*\PortalFiles\Output フォルダーに存在します。

**profiles.xml ファイルにプロファイル名を追加するには**

1. IIS が実行されているマシンで、 [!DNL profiles.xml] ファイルをメモ帳などのテキストエディターで作成します。
1. 各 [!DNL Profile] ポータル内で、次の例のように指定します。

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. ファイルを保存して閉じます。
