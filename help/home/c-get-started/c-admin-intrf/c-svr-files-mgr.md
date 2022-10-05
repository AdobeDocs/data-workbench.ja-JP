---
description: サーバーファイルマネージャを使用すると、Data Workbenchのインストールディレクトリ内のすべてのディレクトリとファイル（構成ファイルや参照ファイルを含む）へのアクセスを提供し、許可されたData Workbenchからサーバーコンピュータをリモートで管理できます。
title: サーバーファイルマネージャー
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 55%

---

# サーバーファイルマネージャー{#server-files-manager}

{{eol}}

サーバーファイルマネージャを使用すると、Data Workbenchのインストールディレクトリ内のすべてのディレクトリとファイル（構成ファイルや参照ファイルを含む）へのアクセスを提供し、許可されたData Workbenchからサーバーコンピュータをリモートで管理できます。

次にアクセス： [!DNL Server Files Manager] の使用 [!DNL Admin] メニューを表示し、次の場所でData Workbench・サーバー・コンピュータのノードを右クリックします。 [!DNL Servers Manager] をクリックし、 **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>選択したディレクトリを表示する新しいサーバーファイルマネージャーを作成できます。 詳しくは、 [新しいサーバーファイルマネージャーの作成](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

の左の列 [!DNL Server Files Manager] ファイル名とフォルダ名の一覧を表示します。 中央と右の列にあるチェックマークは、これらのディレクトリやファイルがファイル構造のどこに存在するかを示しています。

ファイルが製品のインストールディレクトリにある場合、 *サーバー名* ( 例えば、Data Workbenchサーバー ) 列にはチェックマークが含まれます。 ファイルがData Workbench・ユーザーのコンピュータ上の *Data Workbenchインストールディレクトリ*\Temp ディレクトリ： [!DNL Temp] 列にはチェックマークが含まれます。 チェックマークの色は、異なる場所にあるファイルが同時に変更されたかどうかを示しています。

* サーバー名の列の赤いチェックマークは、フォルダーまたはファイルがData Workbenchサーバーコンピューター上に存在することを示します。
* 赤いチェックマークが [!DNL Temp] 列は、ファイルまたはフォルダのローカルコピーが、Data Workbench・サーバ・コンピュータ上のファイルまたはフォルダと同じ [ 変更日時 ] を持つことを示します。
* 白いチェックマーク [!DNL Temp] 列は、 *Data Workbenchインストールディレクトリ*\Temp ディレクトリに、Data Workbench・サーバ・コンピュータ上のファイルまたはフォルダとは異なる変更日時が指定されています。

次の図は、 [!DNL Server Files Manager] 赤と白の両方のチェックマークが付いています。

![](assets/vis_FileManager_RedWhiteChecks.png)

**を使用してディレクトリとファイルを管理するには[!DNL Server Files Manager]**

以下を使用して、 [!DNL Server Files Manager] を使用して、Data Workbench・サーバ・コンピュータ上のディレクトリとファイルを操作します。

次の表に、 [!DNL Server Files Manager]:

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
   <td colname="col2"> <p>ファイルのチェックマークを右クリックし、 <span class="wintitle"> Temp</span> 列、クリック <span class="uicontrol"> 開く</span>」、「 <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> メモ帳</span>または <span class="uicontrol"> フォルダー</span>. </p> </td> 
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
   <td colname="col1"> <p>ファイルを E メールの添付ファイルとしてMicrosoft Outlook にコピー&amp;ペーストします </p> </td> 
   <td colname="col2"> <p><span class="wintitle">Temp</span> 列でファイルのチェックマークを右クリックし、「<span class="uicontrol">コピー</span>」をクリックします。電子メールの本文中で Ctrl + v キーを押して、ファイルを添付します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
