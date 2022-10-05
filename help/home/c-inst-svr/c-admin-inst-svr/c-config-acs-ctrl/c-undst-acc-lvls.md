---
description: アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可するマシン上の URI を表します。
title: アクセスレベルについて
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 4%

---

# アクセスレベルについて{#understanding-access-levels}

{{eol}}

アクセスレベルは、ユーザーのグループが読み取りまたは変更を許可するマシン上の URI を表します。

組織のユーザーに必要なアクセスレベルを定義するには、次のガイドラインに従います。

* 末尾にスラッシュ文字のない特定の URI は、その URI へのアクセスのみを制限します。 例： [!DNL /Components/Communications.cfg] は、 [!DNL Communications.cfg]ファイルのみ。

* ディレクトリを指定する末尾のスラッシュ (/) は、その文字列で始まる URI にグループメンバーがアクセスできるようにします。 例えば、 /Profiles/は Profiles ディレクトリ全体へのアクセスを提供します。
* 末尾のドル記号 ($) は、ディレクトリである場合でも、正確な URI へのアクセスのみを制限します。 例えば、 /Profiles/$は、メインの Profiles ディレクトリを読み取るアクセス権を提供しますが、そのディレクトリ内のファイルを読み取ることはできません。

   特定のファイルにアクセスする場合、末尾の$を使用する必要はありません。

   例： [!DNL /Components/Communications.cfg] および [!DNL /Components/Communications.cfg$] 同じアクセス権を提供します。

* パーセント記号 (%) は、CN(Common Name) と共に使用してアクセスを許可できます。 例えば、 /Users/%CN%/は、 [!DNL Insight] ユーザー。 この構文は、URI で 1 回だけ使用できます。

事前に定義されたアクセス制御グループの URI は、次のように設定されています。

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
   <td colname="col4"> <p>すべてに対する読み取り/書き込みアクセス <span class="keyword"> Insight サーバー</span> ディレクトリ。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>センサー </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>2 つのファイルに対する読み取り/書き込みアクセス権 <span class="wintitle"> センサー</span> ～とのコミュニケーションに用いる <span class="keyword"> Insight サーバー</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー </p> </td> 
   <td colname="col2"> <p>/プロファイル/ </p> <p>/ステータス/ </p> <p>/ソフトウェア/ </p> <p>/アドレス/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>SSL 証明書の共通名に一致する User ディレクトリへの読み取り/書き込みアクセス権 <span class="keyword"> Insight</span> ユーザー。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パワーユーザー </p> </td> 
   <td colname="col2"> <p>/プロファイル/$ </p> <p>/ステータス/ </p> <p>/ソフトウェア/ </p> <p>/アドレス/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> <p>/プロファイル/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>パワーユーザーは、ユーザーと同じアクセス権を持ち、プロファイルディレクトリに書き込む機能が追加されました。 これらのユーザーは、プロファイルを編集し、他のユーザーに対して変更を自動的に更新することができます <span class="keyword"> Insight</span> 新しく定義したワークスペースを配布する場合などのユーザー。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>クラスタサーバ </p> </td> 
   <td colname="col2"> <p>/処理サーバーのコンポーネント/ </p> <p>/アドレス/ </p> <p>/プロファイル/ </p> <p>/Lookups/ </p> <p>/アクセス制御/ </p> <p>/Bin/ </p> <p>/ログ/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Cluster ディレクトリへの読み取り/書き込みアクセス権。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートサーバー </p> </td> 
   <td colname="col2"> <p>/プロファイル/$ </p> <p>/ステータス/ </p> <p>/ソフトウェア/ </p> <p>/アドレス/ </p> <p>/ユーザー/$ </p> </td> 
   <td colname="col3"> <p>/プロファイル/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>レポートマシンは、パワーユーザーと同じアクセスを許可され、に書き込む機能が追加されました。 <span class="filepath"> ReportStatus.vsp</span> ファイル。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**アクセス制御を構成するには**

アクセス制御グループを定義する場合は、このアクセスを必要とするすべての System Administrators、ユーザー、クラスタサーバー、および Report Server ユーザーを含める必要があります [!DNL Insight Server] コンピュータ。 IP アドレスや、共通名や組織などの SSL 証明書情報を使用して、アクセス権を付与できます。

>[!NOTE]
>
>次の場合に [!DNL Access Control.cfg] ファイルの変更日： [!DNL Insight Server]に設定されていない場合、既存のすべての接続は終了され、強制的に再接続されます。 接続は、更新された [!DNL Access Control.cfg] ファイル。 サーバーマネージャーインターフェイスで、 [!DNL Insight Server] 接続が終了し、他のすべての接続と共に再接続が強制されるので、アイコンは一時的に赤に変わり、再び緑に変わります。

1. の [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。

1. 次のアイコンを右クリック： [!DNL Insight Server] を設定して、 **[!UICONTROL Files]**.

1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Access Control]** をクリックして、その内容を表示します。 [!DNL Access Control.cfg] ファイルは、このディレクトリ内に格納されています。

1. チェックマーク ( *サーバー名* 列 [!DNL Access Control.cfg] をクリックし、 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Access Control.cfg].

1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. 内 [!DNL Access Control.cfg] ウィンドウ、クリック **[!UICONTROL Access Control Groups]** をクリックして、その内容を表示します。

   ![](assets/access_ctrl_cfg.png)

1. 新しいアクセス制御グループを追加するには、次の手順に従います。

   1. 右クリック **[!UICONTROL Access Control Groups]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. 右クリック **[!UICONTROL Members]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      デフォルトのグループのメンバーは事前に定義されていません。 デフォルトでは、管理者アクセス権は 127.0.0.1（ローカルホスト）に付与され、 [!DNL Sensor] IP へのアクセス権が付与されます。&#42;. その他のすべてのアクセス制御グループメンバーを定義する必要があります。

   1. パラメーターを入力します。

1. 既存のアクセス制御グループに新しいメンバーを追加する手順は、次のとおりです。

   1. 右クリック **[!UICONTROL Members]** 適切なアクセス制御グループで、 **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. 右クリックしてファイルを保存 **[!UICONTROL (modified)]** をクリックし、 **[!UICONTROL Save]**.

1. ローカルで行った変更を [!DNL Insight Server] マシン、 [!DNL Server Files Manager]、次のチェックマークを右クリック： [!DNL Access Control.cfg] 内 [!DNL Temp] 列、「 **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]**>*.
