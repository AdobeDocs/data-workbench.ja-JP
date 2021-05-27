---
description: アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可するマシン上のURIを示します。
title: アクセスレベルについて
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 4%

---

# アクセスレベルについて{#understanding-access-levels}

アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可するマシン上のURIを示します。

次のガイドラインに従って、組織のユーザーに必要なアクセスレベルを定義します。

* 末尾にスラッシュを含まない特定のURIは、そのURIへのアクセスのみを制限します。 例えば、[!DNL /Components/Communications.cfg]は[!DNL Communications.cfg]ファイルへのアクセスのみを提供します。

* ディレクトリを指定する末尾のスラッシュ(/)は、その文字列で始まる任意のURIにグループメンバーがアクセスできるようにします。 例えば、 /Profiles/はProfilesディレクトリ全体へのアクセスを提供します。
* 末尾のドル記号($)は、ディレクトリであっても、正確なURIに対してのみアクセスを制限します。 例えば、 /Profiles/$は、メインのProfilesディレクトリを読み取るアクセス権を提供しますが、そのディレクトリ内のファイルを読み取るアクセス権は付与しません。

   特定のファイルにアクセスする場合、末尾に$を使用する必要はありません。

   例えば、[!DNL /Components/Communications.cfg]と[!DNL /Components/Communications.cfg$]は同じアクセスを提供します。

* パーセント記号(%)は、CN(Common Name)と共に使用してアクセスを許可できます。 例えば、/Users/%CN%/は、[!DNL Insight]ユーザーのSSL証明書共通名と一致するユーザーディレクトリへのアクセスを許可します。 この構文は、URIで1回だけ使用できます。

事前定義済みのアクセス制御グループのURIは、次のように設定されています。

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
   <td colname="col4"> <p>すべての<span class="keyword"> Insightサーバー</span>ディレクトリに対する読み取り/書き込みアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>センサー </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p><span class="wintitle"> Sensor</span>が<span class="keyword"> Insightサーバー</span>との通信に使用する2つのファイルへの読み取りおよび書き込みアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー </p> </td> 
   <td colname="col2"> <p>/プロファイル/ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/アドレス/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p><span class="keyword"> Insight</span>ユーザーのSSL証明書共通名と一致するUserディレクトリへの読み取りおよび書き込みアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パワーユーザー </p> </td> 
   <td colname="col2"> <p>/プロファイル/$ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/アドレス/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> <p>/プロファイル/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>パワーユーザーは、ユーザーと同じアクセス権を持ち、プロファイルディレクトリに書き込む機能が追加されました。 これらのユーザーは、新しく定義したワークスペースを配布する場合など、他の<span class="keyword"> Insight</span>ユーザーに対して、プロファイルを編集し、変更を自動的に更新できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>クラスタサーバ </p> </td> 
   <td colname="col2"> <p>/処理サーバーのコンポーネント/ </p> <p>/アドレス/ </p> <p>/プロファイル/ </p> <p>/Lookups/ </p> <p>/アクセス制御/ </p> <p>/bin/ </p> <p>/ログ/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>クラスターディレクトリへの読み取り/書き込みアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートサーバー </p> </td> 
   <td colname="col2"> <p>/プロファイル/$ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/アドレス/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> <p>/プロファイル/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>レポートマシンは、パワーユーザーと同じアクセスが許可され、<span class="filepath"> ReportStatus.vsp</span>ファイルに書き込む機能が追加されました。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**アクセス制御を構成するには**

アクセス制御グループを定義する場合は、この[!DNL Insight Server]コンピューターへのアクセスを必要とするSystem Administrators、ユーザー、クラスターサーバー、およびReport Serverユーザーをすべて含める必要があります。 IPアドレスや、共通名や組織などのSSL証明書情報を使用してアクセス権を付与できます。

>[!NOTE]
>
>[!DNL Access Control.cfg]ファイルが[!DNL Insight Server]上で変更されると、既存の接続はすべて終了し、強制的に再接続されます。 接続は、更新された[!DNL Access Control.cfg]ファイルの権限と照合されます。 サーバーマネージャーインターフェイスで、[!DNL Insight Server]アイコンが一時的に赤くなり、接続が終了し、他のすべてのサーバーと一緒に再接続する必要があるので、再び緑に変わります。

1. [!DNL Admin] > [!DNL Dataset and Profile]タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして「サーバーマネージャー」ワークスペースを開きます。

1. 設定する[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Files]**」をクリックします。

1. [!DNL Server Files Manager]で、**[!UICONTROL Access Control]**&#x200B;をクリックして内容を表示します。 [!DNL Access Control.cfg] ファイルは、このディレクトリ内に格納されています。

1. *[!DNL Access Control.cfg]のサーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Access Control.cfg]の[!DNL Temp]列にチェックマークが表示されます。

1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Workstation]**&#x200B;をクリックします。

1. [!DNL Access Control.cfg]ウィンドウで、「**[!UICONTROL Access Control Groups]**」をクリックして内容を表示します。

   ![](assets/access_ctrl_cfg.png)

1. 新しいアクセス制御グループを追加するには：

   1. **[!UICONTROL Access Control Groups]**&#x200B;を右クリックし、**[!UICONTROL Add new]** / **[!UICONTROL Group]**&#x200B;をクリックします。

   1. **[!UICONTROL Members]**&#x200B;を右クリックし、**[!UICONTROL Add new]** / **[!UICONTROL Member]**&#x200B;をクリックします。

      デフォルトのグループのメンバーは事前に定義されていません。 デフォルトでは、管理者アクセスは127.0.0.1（ローカルホスト）に、[!DNL Sensor]アクセスはIP:*に付与されます。 その他のアクセス制御グループメンバーはすべて定義する必要があります。

   1. パラメーターを入力します。

1. 既存のアクセス制御グループに新しいメンバーを追加する手順は、次のとおりです。

   1. 適切なアクセス制御グループの下の&#x200B;**[!UICONTROL Members]**&#x200B;を右クリックし、**[!UICONTROL Add new]** / **[!UICONTROL Member]**&#x200B;をクリックします。

1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックして、ファイルを保存します。

1. ローカルでおこなった[!DNL Insight Server]マシンに対する変更を保存するには、[!DNL Server Files Manager]で[!DNL Temp]列の[!DNL Access Control.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***&#x200B;をクリックします。
