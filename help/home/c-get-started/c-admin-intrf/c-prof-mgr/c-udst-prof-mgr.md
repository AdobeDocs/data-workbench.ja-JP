---
description: 実装に含まれるフォルダー名およびファイル名は、プロファイルマネージャーの左側に表示されます。
solution: Analytics
title: プロファイルマネージャー
topic: Data workbench
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# プロファイルマネージャー{#profile-manager}

実装に含まれるフォルダー名およびファイル名は、プロファイルマネージャーの左側に表示されます。

The profiles that make up your application are displayed as the individual columns in the [!DNL Profile Manager]. これらのプロファイルには、複数の継承されたプロファイルと単一の作業プロファイルが含まれます。

>[!NOTE]
>
>作業プロファイル（データセットプロファイルまたは役割に固有のプロファイル）は、Data Workbenchを開いたときに読み込むプロファイルです。

チェックマーク（およびその色）は、各ファイルが存在するData WorkbenchサーバーおよびData Workbenchコンピューター上のプロファイルフォルダー、ファイルの複数のコピーが存在するかどうか、およびこれらの複数のコピーの変更日時が同じかどうかを示します。 これらのファイルは、プロファイルのダウンロード中に、Data WorkbenchサーバーとData Workbenchコンピューターの間で同期されます。

Following is a sample [!DNL Profile Manager] for a HBX implementation:

![](assets/client-prof.png)

メニュー [!DNL Profile Manager] から、他の任意のマネージャー（またはなど）を開き、の特 [!DNL Dimensions Manager] 定の部分のみを表 [!DNL Reports Manager]示することができま [!DNL Profile Manager]す。 また、新しいプロファイルマネージャーを作成することもできます。詳しくは、「[新しいプロファイルマネージャーの作成](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3)」を参照してください。

ファイル名の横にある、特定の列のチェックマークは、その名前のファイルがその列（プロファイル）で命名されたフォルダーに存在することを示します。As you move to the right in the [!DNL Profile Manager], the files take precedence over those to the left, that is, each inherited profile builds on the profiles to its left in the [!DNL Profile Manager]. 例えば、同じ名前のファイルが、[!DNL Base] プロファイル（列）と [!DNL User] プロファイル（列）の同じ場所にある場合、[!DNL User] プロファイルのファイルではなく、[!DNL Base] プロファイルのファイルが使用されます。

## プロファイルの検索 {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

With Data Workbench 5.5, a search field has been added to find required profiles in the [!DNL Profile Manager].

![](assets/client-prof2.png)

The following types of columns appear in the [!DNL Profile Manager]:

* *継承されたプロファイル名*&#x200B;の列には、各プロファイルフォルダーに存在するファイルに対してチェックマークが入ります。継承されたプロファイルには、アドビにより提供される内部プロファイルと、お客様が作成および維持する、会社に特有または役割に特有のプロファイルがあります。上記の例では、内部プロファイルに Base、Traffic、Value、Marketing などがあります。内部 [!DNL Base] プロファイルには、Adobe アプリケーションの実行に必要な基本の構成要素と設定情報が含まれ、すべての実装に提供されます。他の内部プロファイルには、Web トラフィック、マーケティングなど、特定の種類の情報に関連した要素（ワークスペース、指標、派生ディメンションなど）が含まれます。Adobe では、お客様が分析しているデータの種類と業種に対して、適切なプロファイルのみを提供しています。

   >[!NOTE]
   >
   >デフォルトでは、内部プロファイル（アドビが提供するプロファイル）は変更できません。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。新しいアプリケーションを構築している場合で、内部プロファイルを変更する必要があるときは、[!DNL Insight.cfg] ファイルの Modify Internal Profiles パラメーターを変更する必要があります。詳しくは、 [Insight設定パラメーター](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) （英語のみ）を参照してください。 実際に変更する前に Adobe Consulting Services にお問い合わせください。

* *作業プロファイル名*&#x200B;の列（常に最後から 2 番目の列）には、現在の作業プロファイルのフォルダーに存在するファイルに対してチェックマークが入ります。上記の例では、作業プロファイルは Dataset です。作業プロファイルは、データセットプロファイルまたは役割に特有のプロファイルです。このフォルダーのファイルは、継承されたすべてのプロファイルフォルダーにある同じ名前のファイルよりも優先されます。
* The [!DNL User] column, which is always the last column, contains check marks for files and folders that reside as local files in the User\*profile name* folder. Userフォルダーのディレクトリ構造は作業プロファイルのディレクトリ構造と同じで、各User\*profile name*フォルダーには、その特定のプロファイルのワークスペース、指標、ディメンションおよび設定ファイルのローカルコピーが含まれます。 これらのローカルコピーは、継承されたプロファイルまたは作業プロファイルのフォルダーにある同じ名前のファイルよりも優先されます。The files in the [!DNL User] column were either created and saved to only the User\*profile name* folder, or they reside in an internal or working profile as well as in the User\*profile name* folder. 各フォルダーのファイルは、同一の場合と同一でない場合があり、その変更日時も同一の場合と同一でない場合があります。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * To avoid changing your dataset only locally, the Data Workbench server ignores the local copies of the [!DNL profile.cfg] file and any files in the Dataset or Export folders in the User\*profile name* folder. 無視されたファイルは、[!DNL User] 列の赤い背景で識別できます。コンテキストメニューでは、「ユーザーディレクトリでは無視されます」という警告が表示されます。これらのファイルのローカルコピーに対して行った変更を実装するには、Data Workbenchサーバーと同期できるように、作業プロファイルに保存する必要があります。 作業プロファイルにファイルを保存する手順については、「作業プロファイルへ [のファイルの公開」を参照してください](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。
      >    
      >    
   * 列の中にチェックマークではなく、ハイフン（-）がある場合は、空（0 バイト）のファイルを示しています。Data Workbenchは、0バイトのファイルを存在しないものとして扱うので、これらのファイルを使用して、左側のプロファイルに含まれるファイルを非表示にできます。 See [Hiding Files Using Empty (Zero-byte) Files](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## ファイルのバージョンの確認 {#section-225d732246b94cbe87acdfa9c881d6af}

As mentioned in the previous section, the check marks in the [!DNL Profile Manager] are color-coded so that you can easily identify where a file resides and whether the multiple copies of a file were modified at different times.

ファイルまたは折りたたんだディレクトリは、その左にあるファイルやディレクトリと完全に同一である場合、その列（プロファイル）のファイルやディレクトリと同じ色のチェックマークになります。左にあるどのファイルやディレクトリとも異なる場合、または、そのファイルやディレクトリが [!DNL User] 列にのみ存在する場合は、チェックマークが白になります。

![](assets/vis_ProfMgr_LocalFiles.png)

The [!DNL Profile Manager] shown in the example above indicates the following:

* A white check mark for the [!DNL A New Metric.metric] file appears only in the [!DNL User] column, which indicates that you have only a local copy of that file—it has not been published (or uploaded) to the Data Workbench server for other Data Workbench users to access.

* Check marks for the [!DNL Average Score.metric] file name appear in the Movies and [!DNL User] columns. [!DNL User] 列のチェックマークは、Movies 列のチェックマークと同じ色です。これはファイルのローカルコピーの変更日時が Movies フォルダーのファイルと同じであることを示しています。

* Check marks for the [!DNL Average Score Error.metric] file name appear in the Movies and [!DNL User] columns. [!DNL User] 列のチェックマークは白です。これはファイルのローカルコピーの変更日時が Movies フォルダーのファイルと異なることを示しています。

