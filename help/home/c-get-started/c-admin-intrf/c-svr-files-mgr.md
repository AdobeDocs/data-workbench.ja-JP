---
description: サーバーファイルマネージャーを使用すると、Data Workbenchのインストールディレクトリ内のすべてのディレクトリとファイル（構成ファイルや参照ファイルを含む）にアクセスできるようになり、許可されたData Workbenchからサーバーコンピューターをリモートで管理できます。
title: サーバーファイルマネージャー
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 55%

---

# サーバーファイルマネージャー{#server-files-manager}

サーバーファイルマネージャーを使用すると、Data Workbenchのインストールディレクトリ内のすべてのディレクトリとファイル（構成ファイルや参照ファイルを含む）にアクセスできるようになり、許可されたData Workbenchからサーバーコンピューターをリモートで管理できます。

[!DNL Server Files Manager]には、[!DNL Admin]メニューを使用するだけでなく、[!DNL Servers Manager]内のData Workbenchサーバーコンピューターのノードを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックしてアクセスすることもできます。

![](assets/vis_FileManager.png)

>[!NOTE]
>
>選択したディレクトリを表示する新しいサーバーファイルマネージャーを作成できます。 [新しいサーバーファイルマネージャーの作成](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816)を参照してください。

[!DNL Server Files Manager]の左の列には、ファイル名とフォルダー名が一覧表示されます。 中央と右の列にあるチェックマークは、これらのディレクトリやファイルがファイル構造のどこに存在するかを示しています。

ファイルが製品のインストールディレクトリに存在する場合、*server name*(例えば、Data Workbenchサーバー)列にチェックマークが入ります。 ファイルがData Workbenchユーザーのコンピューター上の&#x200B;*Data Workbenchインストールディレクトリ*\Tempディレクトリに存在する場合、[!DNL Temp]列にはチェックマークが入ります。 チェックマークの色は、異なる場所にあるファイルが同時に変更されたかどうかを示しています。

* サーバー名の列の赤いチェックマークは、フォルダーまたはファイルがData Workbenchサーバーコンピューター上に存在することを示します。
* [!DNL Temp]列の赤いチェックマークは、ファイルまたはフォルダーのローカルコピーの変更日時が、Data Workbenchサーバーコンピューター上のファイルまたはフォルダーと同じであることを示します。
* [!DNL Temp]列の白いチェックマークは、*Data Workbenchのインストールディレクトリ*\Tempディレクトリ内のファイルまたはフォルダーの変更日時が、Data Workbenchサーバーコンピューター上のファイルまたはフォルダーとは異なることを示します。

次の図は、赤と白のチェックマークの[!DNL Server Files Manager]を示しています。

![](assets/vis_FileManager_RedWhiteChecks.png)

**を使用してディレクトリとファイルを管理するには[!DNL Server Files Manager]**

[!DNL Server Files Manager]を使用して、Data Workbench・サーバ・コンピュータ上のディレクトリやファイルを操作できます。

次の表に、[!DNL Server Files Manager]を使用して実行できるタスクを示します。

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 実行する作業... </th> 
   <th colname="col2" class="entry"> 手順... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>任意のディレクトリ内のファイルを表示するには </p> </td> 
   <td colname="col2"> <p>ディレクトリ名をクリックして、その内容を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディレクトリの内容を非表示にするには </p> </td> 
   <td colname="col2"> <p>ディレクトリ名をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディレクトリに関する詳細を表示するには </p> </td> 
   <td colname="col2"> <p>サーバー名の列か <span class="wintitle">Temp</span> 列でディレクトリの横のセルを右クリックします。次の情報が表示されます。 </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">パス. ディレクトリのパス。 </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">ディレクトリ：ディレクトリの名前。 </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">送信元. ディレクトリの場所（Remote または Temp）。 </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">日付（Temp 列のみ）：作成日またはローカルコピーの最新の改訂日。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイルに関する詳細を表示するには </p> </td> 
   <td colname="col2"> <p>サーバー名の列か <span class="wintitle">Temp</span> 列でファイルの横のチェックマークを右クリックします。次の情報が表示されます。 </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">パス. ファイルのパス。 </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">ファイル. ファイルの名前。 </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">送信元. ディレクトリの場所（Remote または Temp）。 </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">日付. ファイルの最新の改訂日。 </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">サイズ. ファイルのサイズ。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ローカルコンピューターにディレクトリをダウンロードするには </p> </td> 
   <td colname="col2"> <p><i>サーバー名</i>の列でこのディレクトリのチェックマークを右クリックし、「<span class="uicontrol">ローカルにディレクトリを作成</span>」をクリックします。このディレクトリのチェックマークが <span class="wintitle">Temp</span> 列に表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ローカルコンピューターにファイルをダウンロードするには </p> </td> 
   <td colname="col2"> <p><i>サーバー名</i>の列でこのファイルのチェックマークを右クリックし、「<span class="uicontrol">ローカル化</span>」をクリックします。このファイルのチェックマークが <span class="wintitle">Temp</span> 列に表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ローカルコンピューターにログファイルの最後の部分をダウンロードするには </p> </td> 
   <td colname="col2"> <p>ログファイル全体をダウンロードする必要をなくすには（特にエラーメッセージがファイルの最後に近いことを知っている場合）、サーバー名の列でファイルのチェックマークを右クリックし、「<span class="uicontrol">終端</span>」をクリックして、ダウンロードする部分のサイズを選択します。このファイルのチェックマークが <span class="wintitle">Temp</span> 列に表示されます。ローカルファイルには、ファイルの最後から、指定した量のデータだけが含まれます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディレクトリを開くには </p> </td> 
   <td colname="col2"> <p><span class="wintitle">Temp</span> 列でディレクトリのチェックマークを右クリックし、<span class="uicontrol">開く</span>／<span class="uicontrol">フォルダー</span>をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイルを開くには </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Temp</span>列でファイルのチェックマークを右クリックし、「<span class="uicontrol">開く</span>」をクリックしてから、「<span class="uicontrol">Data Workbench</span>」、「</span>」、「<span class="uicontrol">」、「<span class="uicontrol">フォルダー</span>」をクリックします。 </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディレクトリのローカルコピーをData Workbench・サーバに保存 </p> </td> 
   <td colname="col2"> <p><span class="wintitle">Temp</span> 列でディレクトリのチェックマークを右クリックし、<span class="uicontrol">ディレクトリを保存</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i> をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイルのローカルコピーをData Workbench・サーバに保存 </p> </td> 
   <td colname="col2"> <p><span class="wintitle">Temp</span> 列でファイルのチェックマークを右クリックし、<span class="uicontrol">保存先</span>／<i>&lt;<span class="uicontrol">profile name</span>&gt;</i> をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディレクトリまたはファイルのローカルコピーを削除する </p> </td> 
   <td colname="col2"> <p><span class="wintitle">Temp</span> 列でディレクトリまたはファイルのチェックマークを右クリックし、「<span class="uicontrol">削除</span>」をクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft Outlookでファイルを電子メールの添付ファイルとしてコピー&amp;ペーストする </p> </td> 
   <td colname="col2"> <p><span class="wintitle">Temp</span> 列でファイルのチェックマークを右クリックし、「<span class="uicontrol">コピー</span>」をクリックします。電子メールの本文中で Ctrl + v キーを押して、ファイルを添付します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
