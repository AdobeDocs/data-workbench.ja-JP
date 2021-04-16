---
description: レポートポータルで使用するプロファイルを指定するには、プロファイル.xmlファイルを設定する必要があります。
title: Profiles.xml ファイルの編集
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%

---

# Profiles.xml ファイルの編集{#edit-the-profiles-xml-file}

レポートポータルで使用するプロファイルを指定するには、プロファイル.xmlファイルを設定する必要があります。

[!DNL profiles.xml]ファイルは、出力用に指定したフォルダーにあります。 デフォルトでは\*PortalName*\PortalFiles\Output folderにあります。

**プロファイル名をプロファイル.xmlファイルに追加するには**

1. IISが実行されているマシン上で、[!DNL profiles.xml]ファイルをメモ帳などのテキストエディターで開きます。
1. 次の追加例のように、ポータルの各[!DNL Profile]のプロファイル要素とタグを指定します。

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
