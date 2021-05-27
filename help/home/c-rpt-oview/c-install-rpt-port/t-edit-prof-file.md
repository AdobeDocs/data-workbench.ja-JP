---
description: Report Portalで使用可能にするプロファイルを指定するには、profiles.xmlファイルを設定する必要があります。
title: Profiles.xml ファイルの編集
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%

---

# Profiles.xml ファイルの編集{#edit-the-profiles-xml-file}

Report Portalで使用可能にするプロファイルを指定するには、profiles.xmlファイルを設定する必要があります。

[!DNL profiles.xml]ファイルは、出力用に指定したフォルダーに存在します。 デフォルトでは、\*PortalName*\PortalFiles\Output folderフォルダー内にあります。

**profiles.xmlファイルにプロファイル名を追加するには**

1. IISを実行しているマシン上で、メモ帳などのテキストエディターで[!DNL profiles.xml]ファイルを開きます。
1. 次の例に示すように、ポータル内の各[!DNL Profile]にプロファイル要素とタグを追加します。

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
