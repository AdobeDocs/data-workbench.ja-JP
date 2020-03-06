---
description: レポートポータルで使用可能にするプロファイルを指定するには、profiles.xmlファイルを設定する必要があります。
solution: Analytics
title: Profiles.xmlファイルの編集
topic: Data workbench
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profiles.xmlファイルの編集{#edit-the-profiles-xml-file}

レポートポータルで使用可能にするプロファイルを指定するには、profiles.xmlファイルを設定する必要があります。

ファイ [!DNL profiles.xml] ルは、出力用に指定したフォルダーに存在します。 デフォルトでは、\*PortalName*\PortalFiles\Output folderディレクトリ内に存在します。

**profiles.xmlファイルにプロファイル名を追加するには**

1. IISが実行されているマシン上で、メモ帳などのテキ [!DNL profiles.xml] ストエディターでファイルを開きます。
1. 次の例のように、ポータルの各ユ [!DNL Profile] ーザーのプロファイル要素とタグを追加します。

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
