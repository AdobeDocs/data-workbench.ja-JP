---
description: パスブラウザーは、アプリケーションとデータセットに対して意味を持つベースディメンション、グループディメンション、レベルディメンションおよび指標の任意の組み合わせを使用するように設定できます。
title: パスブラウザーの設定
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 65%

---

# パスブラウザーの設定{#configure-a-path-browser}

パスブラウザーは、アプリケーションとデータセットに対して意味を持つベースディメンション、グループディメンション、レベルディメンションおよび指標の任意の組み合わせを使用するように設定できます。

パスブラウザーを設定すると、他のパスブラウザーと共に[!DNL Add Visualization]メニューに表示されます。

1. [!DNL Profile Manager]の&#x200B;**[!UICONTROL Menu]**&#x200B;をクリックし、**[!UICONTROL Add Visualization]**&#x200B;と&#x200B;**[!UICONTROL Path Browser]**&#x200B;をクリックします。

   パスブラウザーディレクトリには、少なくとも1つの[!DNL *.vw]ファイルが存在します。

1. 目的のファイルのチェックマークを右クリックし、「**[!UICONTROL Make Local]**」をクリックします。
1. [!DNL User]列のファイルのチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Notepad]**&#x200B;をクリックします。
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
>パスブラウザーのベースディメンション、グループディメンション、レベルディメンションおよび指標について詳しくは、[パスブラウザー](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b)を参照してください。

1. メモ帳で、**[!UICONTROL File]**/**[!UICONTROL Save As]**&#x200B;をクリックして、グループディメンションに基づいて新しい名前でファイルを保存します。つまり、*グループディメンション名*.vwという名前で保存します。

   ファイルは、パスブラウザーディレクトリに保存してください。

   >[!NOTE]
   >
   >パスブラウザーを[!DNL *.vw]ファイルとして保存するには、[!DNL Save As]ウィンドウで、保存するファイルの種類を「すべてのファイル」に設定します。

1. （オプション）作業プロファイルのすべてのユーザーが変更を利用できるようにするには、[!DNL Profile Manager]で、[!DNL User]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL working profile name]**>*&#x200B;をクリックします。
