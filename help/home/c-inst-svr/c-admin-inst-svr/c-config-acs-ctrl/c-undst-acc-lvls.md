---
description: アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可されるマシン上のURIを表します。
solution: Analytics
title: アクセスレベルについて
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 4%

---


# アクセスレベルについて{#understanding-access-levels}

アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可されるマシン上のURIを表します。

次のガイドラインに従って、組織のユーザーに必要なアクセスレベルを定義します。

* 末尾にスラッシュ文字のない特定のURIは、そのURIへのアクセスのみを制限します。 例えば、 [!DNL /Components/Communications.cfg] は [!DNL Communications.cfg]ファイルへのアクセスのみを提供します。

* ディレクトリを指定する末尾のスラッシュ(/)は、その文字列で始まるURIにグループメンバーがアクセスできるようにします。 例えば、/プロファイル/はプロファイルディレクトリ全体へのアクセスを提供します。
* 末尾のドル記号($)は、ディレクトリであっても、完全なURIへのアクセスのみが制限されます。 例えば、/プロファイル/$は、メインプロファイルディレクトリを読み取るアクセスを提供しますが、そのディレクトリ内のファイルは読み取りません。

   特定のファイルにアクセスするために、末尾の$を使用する必要はありません。

   例えば、 [!DNL /Components/Communications.cfg] および同じアクセス権を [!DNL /Components/Communications.cfg$] 提供します。

* パーセント記号(%)をCN(Common Name)と共に使用してアクセスを許可できます。 例えば、/Users/%CN%/と指定すると、ユーザーのSSL証明書共通名に一致するユーザーディレクトリにアクセスでき [!DNL Insight] ます。 この構文は、1つのURIで1回だけ使用できます。

事前定義済みのアクセス制御グループ内のURIは、次のように設定されています。

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> グループ名 </th> 
   <th colname="col2" class="entry"> 読み取り専用アクセス </th> 
   <th colname="col3" class="entry"> 読み取り/書き込みアクセス </th> 
   <th colname="col4" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>管理者 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>すべての <span class="keyword"> Insightサーバー</span> ディレクトリに対する読み取りおよび書き込みアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>センサー </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Sensorが <span class="wintitle"> Insightサーバーとの通信に使用する2つのファイルに対する読み取りと書き込みのアクセス権を付与します</span><span class="keyword"></span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー </p> </td> 
   <td colname="col2"> <p>/プロファイル/ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Insight <span class="keyword"></span> ユーザーのSSL証明書共通名と一致するUserディレクトリに対する読み取りおよび書き込みアクセス権限です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パワーユーザー </p> </td> 
   <td colname="col2"> <p>/プロファイル/$ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> <p>/プロファイル/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>パワー・ユーザーは、プロファイル・ディレクトリに書き込む機能が追加され、ユーザーと同じアクセス権が許可されます。 これらのユーザーは、プロファイルを編集し、新しく定義したワークスペースを配布する場合など、他の <span class="keyword"> Insight</span> ユーザーに対して、変更を自動的に更新できるようにすることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>クラスタサーバ </p> </td> 
   <td colname="col2"> <p>/サーバー処理のコンポーネント/ </p> <p>/Addresses/ </p> <p>/プロファイル/ </p> <p>/Lookups/ </p> <p>/アクセス制御/ </p> <p>/Bin/ </p> <p>/ログ/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>クラスターディレクトリへの読み取りと書き込みアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートサーバー </p> </td> 
   <td colname="col2"> <p>/プロファイル/$ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> <p>/プロファイル/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>レポートコンピューターは、パワーユーザーと同じアクセス権を持ち、ReportStatus.vsp <span class="filepath"></span> ファイルに書き込む機能が追加されました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**アクセス制御を設定するには**

アクセス制御グループを定義する場合は、このコンピューターへのアクセスを必要とするすべてのSystem Administrators、Users、Cluster Server、Report Serverユーザーを含める必要があり [!DNL Insight Server] ます。 共通名や組織などのIPアドレスまたはSSL証明書情報を使用してアクセスを許可できます。

>[!NOTE]
>
>フ [!DNL Access Control.cfg] ァイルがで変更されると、既存のすべての接続 [!DNL Insight Server]が終了し、再接続を強制されます。 接続は、更新された [!DNL Access Control.cfg] ファイルの権限に対してチェックされます。 サーバーマネージャーインターフェイスで、接続が終了し、他のすべてのサーバーと共に再接続を強制されるので、 [!DNL Insight Server] アイコンが一時的に赤に変わり、次に緑に変わります。

1. 「 [!DNL Admin] >」 [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。

1. 設定するアイコンを右クリック [!DNL Insight Server] し、をクリックし **[!UICONTROL Files]**&#x200B;ます。

1. In the [!DNL Server Files Manager], click **[!UICONTROL Access Control]** to view its contents. [!DNL Access Control.cfg] ファイルは、このディレクトリ内に格納されています。

1. Right-click the check mark in the *server name* column for [!DNL Access Control.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Access Control.cfg].

1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. In the [!DNL Access Control.cfg] window, click **[!UICONTROL Access Control Groups]** to view its contents.

   ![](assets/access_ctrl_cfg.png)

1. 新しいアクセス制御グループを追加するには：

   1. 右クリック **[!UICONTROL Access Control Groups]** し、「>」をクリックし **[!UICONTROL Add new]** ま **[!UICONTROL Group]**&#x200B;す。

   1. 右クリック **[!UICONTROL Members]** し、「>」をクリックし **[!UICONTROL Add new]** ま **[!UICONTROL Member]**&#x200B;す。

      デフォルトのグループのメンバーは事前定義されていません。 デフォルトでは、管理者アクセスは127.0.0.1（ローカルホスト）に、 [!DNL Sensor] アクセスはIP:*に付与されます。 その他のアクセス制御グループメンバーはすべて定義する必要があります。

   1. パラメーターを設定します。

1. 既存のアクセス制御・グループに新しいメンバーを追加する手順は、次のとおりです。

   1. 適切なアクセス制御グループ **[!UICONTROL Members]** の下で右クリックし、 **[!UICONTROL Add new]** /をクリックし **[!UICONTROL Member]**&#x200B;ます。

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and then clicking **[!UICONTROL Save]**.

1. ローカルに加えた変更を [!DNL Insight Server] マシンに保存するには、で、 [!DNL Server Files Manager]列のチェックマークを右クリックし、 [!DNL Access Control.cfg] で [!DNL Temp] &lt; **[!UICONTROL Save to]*****[!UICONTROL server name]***>をクリックします。

