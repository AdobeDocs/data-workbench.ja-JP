---
description: Webサイトのマーケティングには、サードパーティWebサイト上の画像または他のリッチメディアファイル（Webサーバーから提供）の形式での広告の配置が含まれる場合があります。
title: 広告インプレッションの測定
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# 広告インプレッションの測定{#measuring-advertisement-impression}

Webサイトのマーケティングには、サードパーティWebサイト上の画像または他のリッチメディアファイル（Webサーバーから提供）の形式での広告の配置が含まれる場合があります。

そのような場合は、ブラウザー上での広告のインプレッションと、Webサイト上で広告のターゲットURLに対する後続のクリックスルー（発生した場合）の両方を測定できます。

イメージ形式の広告の場合、クエリ文字列に[!DNL Log=1]を追加すると、イメージリクエストが行われ、広告のインプレッションが[!DNL Sensor]によってキャプチャされ、分析目的で取り込まれます。

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_ic= | インプレッションキャンペーンを示す値 | v_ic=&quot;キャンペーン1&quot; |
| v_ica= | インプレッションキャンペーンアセットを示す値 | v_ica=&quot;72890ab&quot; |
| v_icr= | インプレッションキャンペーン転送者を示す値 | v_icr=&quot;http://money.cnn.com/markets/ |

イメージリクエストに[!DNL Log=1]を追加する以外に、Webサイト内のターゲットページの広告の先頭にIDを追加して、クリックスルーにつながった広告を追跡し、その広告の特定のキャンペーンに戻るクリックスルーを追跡する必要があります。

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=http://money.cnn.com/markets/”>
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
   <td colname="col3"> v_c="キャンペーン1" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> クリックスルーキャンペーンアセットを示す値 </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> クリックスルーキャンペーン転送者を示す値 </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>市場/ </p> </td> 
  </tr> 
 </tbody> 
</table>
