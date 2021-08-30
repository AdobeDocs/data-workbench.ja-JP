---
description: 管理者は、カスタムグループのアクセス制御の管理を部分的にワークステーションユーザーに任せることができます。
title: グループメンバーアクセスのユーザー管理
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 70%

---

# グループメンバーアクセスのユーザー管理{#user-administration-of-group-member-access}

管理者は、カスタムグループのアクセス制御の管理を部分的にワークステーションユーザーに任せることができます。

**グループメンバーアクセスの自己管理**&#x200B;は、カスタムグループ内のメンバーを追加および削除する権限を管理者以外のユーザーに付与するものです。管理者は、**User List** ファイルを作成し、新しいグループメンバー用の [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) ファイル内でグループアクセスを設定します。

**サーバーマネージャーのアクセス**

**[!DNL User List]**&#x200B;ファイルの設定と&#x200B;**[!DNL Communications.cfg]**&#x200B;ファイルとの同期は、**サーバーマネージャー**&#x200B;ワークスペースでおこないます。

1. ワークトップで、「**管理者**」タブ／「**データセットとプロファイル**」タブをクリックします。

1. **サーバーマネージャー**&#x200B;ワークスペースを開きます。
1. ダイヤグラム内の &lt;*your server name*> を右クリックし、「**ファイル**」を選択します。

   サーバーファイルは、*File*、*`<server name>`*、*Temp*&#x200B;という列を持つテーブルで開きます。

1. **サーバ** ーファイルのサーバー列を右クリックし、「ローカル化」(Make Localby)を選択し **[!DNL Access Control]** ま **[!DNL Components/Communications.cfg)]**&#x200B;す。

   **Temp** 列に白いチェックマークが表示されます。Temp フォルダー内で編集を行うことができます。次に、チェックマークを右クリックして、「**サーバーに保存**」を選択します（サーバーと同期が行われると、チェックマークが赤に変わります）。

## User List.cfg ファイルの作成 {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

管理者は、**[!DNL Access Control]**&#x200B;フォルダーに&#x200B;**[!DNL User List.cfg]**&#x200B;ファイルを作成する必要があります。

1. **Temp**&#x200B;列の「**アクセス制御**」行を右クリックし、**開く** / **フォルダー**&#x200B;を選択します。![](assets/6_4_workstation_groups_3.png)

   **Temp** フォルダー内の Access Control フォルダーが開き、**[!DNL Access Control.cfg]** ファイルだけが表示されます。

1. このフォルダーに別のテキストファイルを追加し、**[!DNL User List.cfg]**（**[!DNL Access Control.cfg]**&#x200B;の横）という名前を付けます。

1. **[!DNL User List.cfg]**&#x200B;ファイルに次のパラメーターを追加します。

User List ファイルには **AccessGroup** オブジェクトのベクターを含める必要があり、各 **AccessGroup** オブジェクトには名前と **Members** という文字列ベクターが必要です。

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

次に、このファイルを編集し、ユーザーをワークステーションビューの**[!DNL User List.cfg]**ファイルに追加できます。

![](assets/6_4_workstation_groups_4.png)

**[!DNL User List.cfg]**&#x200B;ファイルに追加する最も基本的なパラメータを以下に示します。 これでワークステーションビューに Members を追加できます。

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>手動で編集する&#x200B;**[!DNL .cfg]**&#x200B;ファイルと同様に、タブの代わりにスペースを使用し、空白と構文に十分注意してください。 このファイルに誤りがあると、*Adobe Insight Server* は User List ファイルを無視します。

各 **Access Group** の **Name** フィールドは、[!DNL Access Control.cfg] ファイル内で参照されます。

>[!NOTE]
>
>**CN:**&#x200B;や&#x200B;**OU:**&#x200B;などのディレクトリサービスプレフィックスを持つ有効なメンバーのみが使用でき、ワイルドカード文字(*)を含めることはできません。

## Communications.cfg ファイルの設定 {#section-9d6f05ba81c14f15be63e361533459e8}

管理者は、まず&#x200B;**[!DNL Components]>[!DNL Communications.cfg]**&#x200B;ファイルを開き、**[!DNL Access Control User List File]**&#x200B;という名前の新しいキーを追加することで、この機能を有効にします。 このキーの文字列値は、この新しいファイルが配置されるパスです。

1. サーバーファイルから「**Components**」をクリックし、サーバー列のチェックマークを右クリックします。「**ローカル化**」をクリックします。

   **Temp** 列に白いチェックマークが表示されます。

1. **Temp** 列のチェックマークを右クリックし、**開く**／**ワークステーションで**&#x200B;を選択します。

1. **Communication.cfg** ファイル内で **component** を右クリックし、「**カスタムキーを追加**」を選択します。 ![](assets/6_4_workstation_groups.png)

1. 「**名前**」に「*Access Control User List File*」と入力し、「**タイプ**」に *String* を設定します。

   >[!NOTE]
   新しいリストファイルをパスとして作成することはできません。 これを修正するには、ファイルを保存し、エディター（メモ帳）で開いて、「String」を「Path」に変更します。

   変更前：

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <string>: Access Control\\User List.cfg
   ```

   変更後：

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <Path>: Access Control\\User List.cfg
   ```

1. **[!DNL Communications.cfg]** ファイルを保存し、（必要に応じて）サーバーに保存します。これによってサーバー内のコンポーネントが再起動するので、**[!DNL Communications.cfg]** ファイルの解析を妨げる可能性があるミスをしないようにしてください。
1. システムに処理サーバーが含まれている場合は、**[!DNL Components for Processing Servers.cfg]**&#x200B;ファイルの設定ファイルを変更します。
1. **[!DNL Communications.cfg]**&#x200B;を右クリックし、サーバに保存します。

Data Workbench 管理者は、目的のユーザーに User List ファイルへのアクセス権があり、そのユーザーがグループを管理できることを確認できるようになりました。ユーザーは、User List ファイルを開き、編集し、必要に応じて CN または OU メンバーを追加および削除できます。

## Access Control.cfg ファイルの同期 {#section-ca6da453dfb4432bb40b86ef15ede872}

次に、管理者は、**[!DNL Access Control.cfg]** を編集して、User List ** ファイルで定義されているグループへの参照を挿入することができます。

グループへの参照は、その他のメンバーと同様に挿入しますが、以下の構文に従う必要があります。

```
$(Group Name)
```

「Group Name」は、User List ファイルで定義されているもの（空白を含む）と一致しています。  ![](assets/6_4_workstation_groups_2.png)

この時点で、Data Workbench 管理者は、選択されたグループユーザーに User List ファイルへのアクセス権があることを確認できます。選択されたユーザーは、**[!DNL User List.cfg]** ファイルを開き、編集し、必要に応じて CN または OU メンバーを追加および削除できます。
