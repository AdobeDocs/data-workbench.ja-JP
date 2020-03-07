---
description: ワークトップを使用すると、特定のワークスペースがData Workbenchサーバー上にあるか、ローカルマシン上にあるか、またはその両方に存在するかに関わらず、各ワークスペースの保存場所を簡単に判断できます。
solution: Analytics
title: ファイルのバージョン管理
topic: Data workbench
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ファイルのバージョン管理{#file-versioning}

ワークトップを使用すると、特定のワークスペースがData Workbenchサーバー上にあるか、ローカルマシン上にあるか、またはその両方に存在するかに関わらず、各ワークスペースの保存場所を簡単に判断できます。

## Identifying file versions {#section-d555c96b016344f19b356c12213dd2a9}

**サーバー**

サーバーワークスペースは、接続されたData Workbenchサーバーに保存され、このプロファイルとタブにアクセスできるすべてのユーザーが使用できます。 サーバーワークスペースは、1 つのサムネールとして表示されます。

![](assets/wsp_thumb_server.png)

サーバーワークスペースは、デフォルトでは、接続されているData Workbenchサーバー上のWorkspacesフォルダー内の適切なサブフォルダーに保存されます。

**ローカル**

ローカルワークスペースは、サーバーワークスペースのローカルバージョンです。ローカルワークスペースは、重なり合う 2 つのサムネールとして表示されます。最初は上側のサムネールがグローで囲まれています。これは最新の変更がサーバーワークスペースに対してローカルに行われたことを示します。このグローは時間とともに消えます。

![](assets/wsp_thumb_local.png)

ローカルワークスペースは、デフォルトでは、Data Workbench(ま [!DNL User\working profile name\Workspaces\tab] たはInsight)のインストールディレクトリ内のnameフォルダーに保存されます。

>[!NOTE]
>
>サーバーワークスペースのローカルバージョンがある場合は、サーバーバージョンに戻してから、サーバーワークスペースの更新バージョンをダウンロードする必要があります。 To revert back to the server version without local changes, right-click the thumbnail of the local workspace and click **[!UICONTROL Revert to server version]**.

**ユーザー**

ユーザーワークスペースは、ローカルマシン上で作成され、ローカルマシン上にのみ存在するワークスペースです。ユーザーワークスペースは、背後に空白のワークスペースの輪郭が点線で描かれた単一のサムネールとして表示され、接続されているData Workbenchサーバー上にソースワークスペースがないことを示します。

![](assets/wsp_thumb_user.png)

ユーザーワークスペースは、デフォルトでは、Insightのインストールディレクトリ内のUser\*working profile name*\Workspaces\*tab name*フォルダーに保存されます。
