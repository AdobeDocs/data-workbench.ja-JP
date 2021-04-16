---
description: アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可されるマシン上のURIを表します。
title: アクセスレベルについて
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 4%

---

# アクセスレベルについて{#understanding-access-levels}

アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可されるマシン上のURIを表します。

次のガイドラインに従って、組織のユーザーに必要なアクセスレベルを定義します。

* 末尾にスラッシュ文字のない特定のURIは、そのURIへのアクセスのみを制限します。 例えば、[!DNL /Components/Communications.cfg]は[!DNL Communications.cfg]ファイルへのアクセスのみを提供します。

* ディレクトリを指定する末尾のスラッシュ(/)は、その文字列で始まるURIにグループメンバーがアクセスできるようにします。 例えば、/プロファイル/はプロファイルディレクトリ全体へのアクセスを提供します。
* 末尾のドル記号($)は、ディレクトリであっても、完全なURIへのアクセスのみが制限されます。 例えば、/プロファイル/$は、メインプロファイルディレクトリを読み取るアクセスを提供しますが、そのディレクトリ内のファイルは読み取りません。

   特定のファイルにアクセスするために、末尾の$を使用する必要はありません。

   例えば、[!DNL /Components/Communications.cfg]と[!DNL /Components/Communications.cfg$]は同じアクセスを提供します。

* パーセント記号(%)をCN(Common Name)と共に使用してアクセスを許可できます。 例えば、/Users/%CN%/と指定すると、[!DNL Insight]ユーザーのSSL証明書共通名に一致するユーザーディレクトリにアクセスできます。 この構文は、1つのURIで1回だけ使用できます。

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
   <td colname="col4"> <p>すべての<span class="keyword"> Insight Server</span>ディレクトリへの読み取りと書き込みのアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>センサー </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p><span class="wintitle"> Sensor</span>が<span class="keyword"> Insight Server</span>との通信に使用する2つのファイルに対する読み取りと書き込みのアクセス権を付与します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー </p> </td> 
   <td colname="col2"> <p>/プロファイル/ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p><span class="keyword"> Insight</span>ユーザーのSSL証明書共通名と一致するユーザーディレクトリへの読み取りおよび書き込みアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パワーユーザー </p> </td> 
   <td colname="col2"> <p>/プロファイル/$ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> <p>/プロファイル/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>パワー・ユーザーは、プロファイル・ディレクトリに書き込む機能が追加され、ユーザーと同じアクセス権が許可されます。 これらのユーザーは、新しく定義したプロファイルを配布する場合など、他の<span class="keyword"> Insight</span>ユーザーに対して、ワークスペースを編集し、変更を自動的に更新できます。 </p> </td> 
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
   <td colname="col4"> <p>レポートコンピューターはパワーユーザーと同じアクセスが許可され、<span class="filepath"> ReportStatus.vsp</span>ファイルに書き込む機能が追加されました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**アクセス制御を設定するには**

アクセス制御グループを定義する場合は、この[!DNL Insight Server]コンピューターへのアクセスを必要とするSystem Administrators、Users、Cluster Server、Report Serverのユーザーをすべて含める必要があります。 共通名や組織などのIPアドレスまたはSSL証明書情報を使用してアクセスを許可できます。

>[!NOTE]
>
>[!DNL Insight Server]上の[!DNL Access Control.cfg]ファイルが変更されると、既存の接続はすべて終了され、再接続を強制されます。 接続は、更新された[!DNL Access Control.cfg]ファイルの権限に対してチェックされます。 サーバーマネージャーインターフェイスでは、接続が終了し、他のすべてのサーバーとの再接続を強制されるので、[!DNL Insight Server]アイコンが一時的に赤に変わり、次に緑に変わります。

1. 「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。

1. 設定する[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Files]**」をクリックします。

1. [!DNL Server Files Manager]の&#x200B;**[!UICONTROL Access Control]**&#x200B;をクリックして、内容を表示します。 [!DNL Access Control.cfg] ファイルは、このディレクトリ内に格納されています。

1. [!DNL Access Control.cfg]の&#x200B;*サーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Access Control.cfg]の[!DNL Temp]列にチェックマークが表示されます。

1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Workstation]**&#x200B;をクリックします。

1. [!DNL Access Control.cfg]ウィンドウで、**[!UICONTROL Access Control Groups]**&#x200B;をクリックして内容を表示します。

   ![](assets/access_ctrl_cfg.png)

1. 新しいアクセス制御グループを追加するには：

   1. **[!UICONTROL Access Control Groups]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Group]**&#x200B;をクリックします。

   1. **[!UICONTROL Members]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Member]**&#x200B;をクリックします。

      デフォルトのグループのメンバーは事前定義されていません。 デフォルトでは、管理者アクセスは127.0.0.1（ローカルホスト）に、[!DNL Sensor]アクセスはIP:*に付与されます。 その他のアクセス制御グループメンバーはすべて定義する必要があります。

   1. パラメーターを設定します。

1. 既存のアクセス制御・グループに新しいメンバーを追加する手順は、次のとおりです。

   1. 適切なアクセス制御グループの&#x200B;**[!UICONTROL Members]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Member]**&#x200B;をクリックします。

1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックしてファイルを保存します。

1. ローカルに適用した変更を[!DNL Insight Server]マシンに保存するには、[!DNL Server Files Manager]で、[!DNL Temp]列の[!DNL Access Control.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]** ***[!UICONTROL server name]***&#x200B;をクリックします。
