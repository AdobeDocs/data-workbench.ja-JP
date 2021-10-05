---
description: Web サイトのマーケティングには、サードパーティの Web サイト上の画像または他のリッチメディアファイル（Web サーバーから提供）の形式での広告の配置が含まれる場合があります。
title: 広告インプレッションの測定
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# 広告インプレッションの測定{#measuring-advertisement-impression}

Web サイトのマーケティングには、サードパーティの Web サイト上の画像または他のリッチメディアファイル（Web サーバーから提供）の形式での広告の配置が含まれる場合があります。

このような場合、ブラウザーでの広告のインプレッションと、後続のクリックスルー（存在する場合）の両方を、Web サイト上の広告のターゲット URL に対して測定できます。

画像形式の広告の場合、クエリ文字列に [!DNL Log=1] を追加すると、イメージリクエストが生成され、広告インプレッションが [!DNL Sensor] によってキャプチャされ、分析のために取得されます。

```
<!—REFERENCE IMPRESSION TAG->
<IMG SRC="https://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=https://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_ic= | インプレッションキャンペーンを示す値 | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | インプレッションキャンペーンアセットを示す値 | v_ica=&quot;72890ab&quot; |
| v_icr= | インプレッションキャンペーンリファラーを示す値 | v_icr=&quot;https://money.cnn.com/markets/ |

イメージリクエストに [!DNL Log=1] を追加する以外に、広告から Web サイト内のターゲットページへの URL に識別子を追加して、クリックスルーにつながった広告を追跡し、その広告の特定のキャンペーンに戻るクリックスルーを追跡する必要があります。

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=https://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 収集されたデータ </th>
   <th colname="col2" class="entry"> 説明 </th>
   <th colname="col3" class="entry"> 例 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> v_c= </td>
   <td colname="col2"> クリックスルーキャンペーンを示す値 </td>
   <td colname="col3"> v_c="CAMPAIGN1" </td>
  </tr>
  <tr>
   <td colname="col1"> v_ca= </td>
   <td colname="col2"> クリックスルーキャンペーンアセットを示す値 </td>
   <td colname="col3"> v_ca="72890ab" </td>
  </tr>
  <tr>
   <td colname="col1"> v_cr= </td>
   <td colname="col2"> クリックスルーキャンペーンリファラーを示す値 </td>
   <td colname="col3"> <p> <span class="filepath"> v_cr="https://money.cnn.com/</span> </p> <p>市場/ </p> </td>
  </tr>
 </tbody>
</table>
