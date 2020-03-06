---
description: プロセスマップは、アプリケーションとデータセットに対して意味を持つベースディメンション、グループディメンション、レベルディメンションおよび指標の任意の組み合わせを使用するように設定できます。
solution: Analytics
title: プロセスマップの設定
topic: Data workbench
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# プロセスマップの設定{#configure-a-process-map}

プロセスマップは、アプリケーションとデータセットに対して意味を持つベースディメンション、グループディメンション、レベルディメンションおよび指標の任意の組み合わせを使用するように設定できます。

After you configure a process map, it is listed with other process maps in the [!DNL Add Visualization menu].

1. In the [!DNL Profile Manager], click **[!UICONTROL Menu]**, click **[!UICONTROL Add Visualization]**, then click the type of process map type that you want to configure (2D Metric Map, 2D Process Map, or 3D Process Map).

   At least one [!DNL *.vw] file resides in the directory.

1. Right-click the check mark for the desired file and click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 次のサンプルのファイルと表を参考にして、ファイルのパラメーターを編集します。

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 入力する情報 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Metric name</i> </p> </td> 
   <td colname="col2"> <p>特定のノードの値がそのノードのサイズと比例して表示される指標の名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Base dimension name</i> </p> </td> 
   <td colname="col2"> <p>エレメントがノードとしてプロセスマップに表示されるディメンションの名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Level dimension name</i> </p> </td> 
   <td colname="col2"> <p>エレメントをプロセスマップにドラッグするベースディメンションのレベル（親）の名前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Group dimension name</i> </p> </td> 
   <td colname="col2"> <p>レベルディメンションのエレメントをノード間の接続にどのようにグループ化するかを決定するディメンションの名前。2 つのノード間の接続は、グループディメンションの複数の要素にまたがることはできません。プロセスマップ内のノードに基づいて選択範囲を作成すると、そのノードを含むグループディメンションのすべての要素を選択することになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Metric name for metric map</i> </p> </td> 
   <td colname="col2"> <p>このパラメーターは、2D 指標マップにのみ適用されます。 </p> <p>値によってマップ上のノードの水平位置が決定される指標の名前。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>For more information about the base dimension, group dimension, level dimension, and metric for a process map, see [Process Maps](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. In Notepad, click **[!UICONTROL File]** > **[!UICONTROL Save As]** to save the file with a new name based on the base dimension, that is, *Base dimension name*.vw.

   （2D 指標マップを設定する場合は、指標マップの指標名に基づいた名前でファイルを保存します。つまり、「*Metric name for metric map*.vw」として保存します）。ファイルは、適切なプロセスマップディレクトリに保存してください。

   >[!NOTE]
   >
   >To make sure that your process map is saved as a [!DNL *.vw] file, in the [!DNL Save As] window, set Save as type to All Files.

1. (Optional) To make the changes available to all users of the working profile, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
