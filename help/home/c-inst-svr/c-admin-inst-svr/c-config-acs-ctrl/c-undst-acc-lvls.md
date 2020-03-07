---
description: アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可されるマシン上のURIを表します。
solution: Insight
title: アクセスレベルについて
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# アクセスレベルについて{#understanding-access-levels}

アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可されるマシン上のURIを表します。

組織のユーザーに必要なアクセスレベルを定義するには、次のガイドラインに従います。

* 末尾にスラッシュ文字のない特定のURIは、そのURIに対するアクセスのみを制限します。 例えば、はファイ [!DNL /Components/Communications.cfg] ルへのアクセスのみを [!DNL Communications.cfg]提供します。

* ディレクトリを指定する末尾のスラッシュ(/)は、その文字列で始まるURIにグループメンバーがアクセスできるようにします。 例えば、/Profiles/はProfilesディレクトリ全体へのアクセスを提供します。
* 末尾のドル記号($)は、ディレクトリであっても、完全なURIへのアクセスのみを制限します。 例えば、/Profiles/$は、メインのProfilesディレクトリを読み取るアクセス権を提供しますが、そのディレクトリ内のファイルは読み取りません。

   特定のファイルにアクセスする場合は、末尾の$を使用する必要はありません。

   例えば、同じアク [!DNL /Components/Communications.cfg] セスを [!DNL /Components/Communications.cfg$] 提供し、

* パーセント記号(%)をCN（共通名）と共に使用して、アクセスを許可できます。 例えば、/Users/%CN%/と指定すると、ユーザーのSSL証明書の共通名に一致するユーザーディレクトリにアクセスでき [!DNL Insight] ます。 この構文はURIで1回しか使用できないことに注意してください。

事前定義されたアクセス制御グループのURIは、次のように設定されています。

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
   <td colname="col4"> <p>すべての <span class="keyword"> Insight Serverディレクトリに対する読み取りと書き込みのアクセス権</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>センサー </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Sensorが <span class="wintitle"> Insight Serverとの通信に使用する2つのファイルに対する読み取り</span> /書き込みアクセス権 <span class="keyword"> を持ちます</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Users </p> </td> 
   <td colname="col2"> <p>/プロファイル/ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/アドレス/ </p> <p>/Users/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>InsightユーザーのSSL証明書の共通名に一致するUserディレクトリへの読み取りおよび書き込みアクセス権 <span class="keyword"> を持ち</span> ます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パワーユーザ </p> </td> 
   <td colname="col2"> <p>/プロファイル/$ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/アドレス/ </p> <p>/Users/$ </p> </td> 
   <td colname="col3"> <p>/プロファイル/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>パワーユーザーはユーザーと同じアクセス権を持ち、Profilesディレクトリに書き込む機能が追加されました。 これらのユーザーは、プロファイルを編集し、新しく定義したワークスペースの配布時など、他の <span class="keyword"> Insight</span> ユーザーに対して自動的に変更を更新できるようにすることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>クラスタサーバ </p> </td> 
   <td colname="col2"> <p>/処理サーバーのコンポーネント/ </p> <p>/アドレス/ </p> <p>/プロファイル/ </p> <p>/参照/ </p> <p>/アクセス制御/ </p> <p>/Bin/ </p> <p>/ログ/ </p> </td> 
   <td colname="col3"> <p>/クラスタ/ </p> </td> 
   <td colname="col4"> <p>クラスタディレクトリへの読み取りと書き込みのアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートサーバ </p> </td> 
   <td colname="col2"> <p>/プロファイル/$ </p> <p>/ステータス/ </p> <p>/Software/ </p> <p>/アドレス/ </p> <p>/Users/$ </p> </td> 
   <td colname="col3"> <p>/プロファイル/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>レポートコンピューターは、パワーユーザーと同じアクセス権を持ち、 <span class="filepath"> ReportStatus.vspファイルに書き込む機能が追加されました</span> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**アクセス制御を設定するには**

アクセス制御グループを定義する場合は、このコンピュータへのアクセスを必要とするすべてのシステム管理者、ユーザー、クラスターサーバー、およびレポートサーバーユーザーを含める必要が [!DNL Insight Server] あります。 IPアドレスまたはSSL証明書情報（共通名や組織など）を使用してアクセスを許可できます。

>[!NOTE]
>
>ファイルがオ [!DNL Access Control.cfg] ンに変更されると、 [!DNL Insight Server]既存の接続はすべて終了し、再接続を強制されます。 接続は、更新されたファイル内の権限に対してチェックさ [!DNL Access Control.cfg] れます。 サーバーマネージャーインターフェイスで、 [!DNL Insight Server] 接続が終了し、他のすべてのサーバーと共に再接続を強制されるので、アイコンが一時的に赤くなり、緑に戻ります。

1. 「>」タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サー **[!UICONTROL Servers Manager]** バーマネージャーワークスペースを開きます。

1. 設定するのアイコンを右ク [!DNL Insight Server] リックし、をクリックします **[!UICONTROL Files]**。

1. In the [!DNL Server Files Manager], click **[!UICONTROL Access Control]** to view its contents. [!DNL Access Control.cfg] ファイルは、このディレクトリ内に格納されています。

1. Right-click the check mark in the *server name* column for [!DNL Access Control.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Access Control.cfg].

1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. In the [!DNL Access Control.cfg] window, click **[!UICONTROL Access Control Groups]** to view its contents.

   ![](assets/access_ctrl_cfg.png)

1. 新しいアクセス制御グループを追加するには：

   1. 右クリックし、/ **[!UICONTROL Access Control Groups]** をクリ **[!UICONTROL Add new]** ックしま **[!UICONTROL Group]**&#x200B;す。

   1. 右クリックし、/ **[!UICONTROL Members]** をクリ **[!UICONTROL Add new]** ックしま **[!UICONTROL Member]**&#x200B;す。

      デフォルトのグループのメンバーは事前に定義されていません。 デフォルトでは、管理者アクセスは127.0.0.1（ローカルホスト）に、アクセスはIP:* [!DNL Sensor] に付与されています。 その他のアクセス制御グループメンバーはすべて定義する必要があります。

   1. パラメーターを設定します。

1. 既存のアクセス制御グループに新しいメンバーを追加するには：

   1. 適切なアクセス制御 **[!UICONTROL Members]** グループの下で右クリックし、/をク **[!UICONTROL Add new]** リックしま **[!UICONTROL Member]**&#x200B;す。

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and then clicking **[!UICONTROL Save]**.

1. ローカルに加えた変更をマシンに保 [!DNL Insight Server] 存するには、 [!DNL Server Files Manager]で列のチェックマークを右クリックし、 [!DNL Access Control.cfg] &lt; [!DNL Temp]**[!UICONTROL Save to]** >をクリッ ***[!UICONTROL server name]***&#x200B;クします。

