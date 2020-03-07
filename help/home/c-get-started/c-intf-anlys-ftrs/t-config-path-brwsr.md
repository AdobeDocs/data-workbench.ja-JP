---
description: パスブラウザーは、アプリケーションとデータセットに対して意味を持つベースディメンション、グループディメンション、レベルディメンションおよび指標の任意の組み合わせを使用するように設定できます。
solution: Analytics
title: パスブラウザーの設定
topic: Data workbench
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# パスブラウザーの設定{#configure-a-path-browser}

パスブラウザーは、アプリケーションとデータセットに対して意味を持つベースディメンション、グループディメンション、レベルディメンションおよび指標の任意の組み合わせを使用するように設定できます。

After you configure a path browser, it is listed with other path browsers in the [!DNL Add Visualization] menu.

1. で、をク [!DNL Profile Manager]リックし、 **[!UICONTROL Menu]**&#x200B;とをクリック **[!UICONTROL Add Visualization]** します **[!UICONTROL Path Browser]**。

   At least one [!DNL *.vw] file resides in the Path Browser directory.

1. Right-click the check mark for the desired file and click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 次のサンプルのファイルと表を参考にして、ファイルのパラメーターを編集します。

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 入力する情報 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Base dimension name</i> </p> </td> 
   <td colname="col2"> <p>パスブラウザーにエレメントを表示するディメンションの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Group dimension name</i> </p> </td> 
   <td colname="col2"> <p>レベルディメンションのエレメントをパスブラウザーのパスにどのようにグループ化するかを決定するディメンションの名前。特に、パスブラウザー内の単一のパスに関連付けられたレベルディメンション要素は、グループディメンションの複数の要素にまたがることはできません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Level dimension name</i> </p> </td> 
   <td colname="col2"> <p>エレメントをパスブラウザーにドラッグするベースディメンションのレベル（親）の名前。1 つのベースディメンションの要素から次の要素へとパスをたどると、1 つのレベルディメンションの要素から次の要素へと移動することになります。ベースディメンションエレメントのパスを選択すると、レベルディメンションの対応するエレメントのデータも選択されます。選択範囲にはルートに関連付けられたレベルディメンションの要素が必ず含まれており、パスに要素を追加することによって絞り込みます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Metric name</i> </p> </td> 
   <td colname="col2"> <p>特定のエレメントの値がそのエレメントへのパスの厚みと比例して表示される指標の名前。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>For more information about the base dimension, group dimension, level dimension, and metric for a path browser, see [Path Browsers](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. In Notepad, click **[!UICONTROL File]** > **[!UICONTROL Save As]** to save the file with a new name based on the group dimension, that is, *Group dimension name*.vw.

   ファイルは、パスブラウザーディレクトリに保存してください。

   >[!NOTE]
   >
   >To make sure that your path browser is saved as a [!DNL *.vw] file, in the [!DNL Save As] window, set Save as type to All Files.

1. (Optional) To make the changes available to all users of the working profile, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
