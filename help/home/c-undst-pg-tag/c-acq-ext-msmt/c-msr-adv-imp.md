---
description: Webサイトのマーケティングには、サードパーティWebサイト上の画像または（Webサーバーから提供される）他のリッチメディアファイルの形式での広告の配置が含まれる場合があります。
solution: Analytics
title: 広告インプレッションの測定
topic: Data workbench
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 広告インプレッションの測定{#measuring-advertisement-impression}

Webサイトのマーケティングには、サードパーティWebサイト上の画像または（Webサーバーから提供される）他のリッチメディアファイルの形式での広告の配置が含まれる場合があります。

このような場合は、ブラウザーでの広告のインプレッションと、Webサイト上での広告のターゲットURLに対する後続のクリックスルー（存在する場合）の両方を測定できます。

イメージの形式の広告の場合、クエリ文字列 [!DNL Log=1] に追加すると、イメージリクエストが生成され、広告のインプレッションが分析のためにによって取 [!DNL Sensor] り込まれます。

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_ic= | インプレッションキャンペーンを示す値 | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | インプレッションキャンペーンアセットを示す値 | v_ica=&quot;72890ab&quot; |
| v_icr= | インプレッションキャンペーンリファラーを示す値 | v_icr=&quot;http://money.cnn.com/markets/ |

イメージリクエスト [!DNL Log=1] に追加する以外に、広告からWebサイト内のターゲットページへのURLに識別子を追加して、クリックスルーにつながった広告を追跡し、その広告の特定のキャンペーンへのクリックスルーを追跡します。

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
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>市場/ </p> </td> 
  </tr> 
 </tbody> 
</table>

