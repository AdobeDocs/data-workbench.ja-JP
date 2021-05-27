---
description: プロセスマップは、アプリケーションとデータセットに対して意味を持つベースディメンション、グループディメンション、レベルディメンションおよび指標の任意の組み合わせを使用するように設定できます。
title: プロセスマップの設定
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 63%

---

# プロセスマップの設定{#configure-a-process-map}

プロセスマップは、アプリケーションとデータセットに対して意味を持つベースディメンション、グループディメンション、レベルディメンションおよび指標の任意の組み合わせを使用するように設定できます。

設定したプロセスマップは、他のプロセスマップと共に[!DNL Add Visualization menu]に表示されます。

1. [!DNL Profile Manager]で「**[!UICONTROL Menu]**」をクリックし、「**[!UICONTROL Add Visualization]**」をクリックして、設定するプロセスマップのタイプ（2D指標マップ、2Dプロセスマップ、または3Dプロセスマップ）をクリックします。

   少なくとも1つの[!DNL *.vw]ファイルがディレクトリに存在します。

1. 目的のファイルのチェックマークを右クリックし、「**[!UICONTROL Make Local]**」をクリックします。
1. [!DNL User]列でファイルのチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Notepad]**&#x200B;をクリックします。
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
>プロセスマップのベースディメンション、グループディメンション、レベルディメンションおよび指標について詳しくは、「[プロセスマップ](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e)」を参照してください。

1. メモ帳で、 **[!UICONTROL File]** / **[!UICONTROL Save As]**&#x200B;をクリックして、ベースディメンションに基づいて新しい名前でファイルを保存します。つまり、 *ベースディメンション名*.vwです。

   （2D 指標マップを設定する場合は、指標マップの指標名に基づいた名前でファイルを保存します。つまり、「*Metric name for metric map*.vw」として保存します）。ファイルは、適切なプロセスマップディレクトリに保存してください。

   >[!NOTE]
   >
   >プロセスマップを[!DNL *.vw]ファイルとして保存するには、[!DNL Save As]ウィンドウで、「ファイルの種類として保存」を「すべてのファイル」に設定します。

1. （オプション）作業プロファイルのすべてのユーザーが変更を利用できるようにするには、[!DNL Profile Manager]で、[!DNL User]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL working profile name]***&#x200B;をクリックします。
