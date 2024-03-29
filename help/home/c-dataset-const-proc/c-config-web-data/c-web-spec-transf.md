---
description: Site 用プロファイルに付属の変換データセットインクルードファイルで定義する Web 固有の設定について取り上げます。
title: 変換に関する Web 固有の設定
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 62%

---

# 変換に関する Web 固有の設定{#web-specific-settings-for-transformation}

{{eol}}

Site 用プロファイルに付属の変換データセットインクルードファイルで定義する Web 固有の設定について取り上げます。

これらの設定によって定義された条件、ディメンション、パラメーターは、データセット構築の変換段階で作成されます。

* [Page View Condition](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [URI ディメンション](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Referrer ディメンション](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [セッションのパラメーター](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Page View Condition {#section-cc2807a12a88492f8b64a43234a1f835}

[!DNL Page View Condition] は、訪問者のページビュー履歴に関して収集されるデータに、特定のログエントリ（ページリクエスト）を含めるかどうかを判断する条件演算です。[!DNL Page View Condition] を満たしたログエントリは、Page View 可算ディメンションのエレメントとして追加されます。ログエントリが [!DNL Page View Condition] を満たさなかった場合でも、他のディメンションからは、引き続きそのデータフィールドにアクセスすることができます。[!DNL Page View Condition] の条件判定の結果は、Page View ディメンションに加え、次のディメンションに影響を及ぼす可能性があります。

* **[!DNL URI]および [!DNL Page]:** これらのディメンションは、 [!DNL Page View Condition]. 指定されたページが [!DNL Page View Condition,] URI ディメンションやページディメンションには含まれません。

* **[!DNL Visitor Page Views]および [!DNL Session Page Views]:** 訪問者ページビュー数ディメンションとセッションページビュー数ディメンションは、それぞれ、特定のセッションに対して訪問者が閲覧したページ数または特定のセッションで閲覧したページ数です。 次の項目で除外されたページ： [!DNL Page View Condition] はこの数に含まれていません。

* **セッション番号：** この [!DNL Page View Condition] は、セッション番号ディメンションに間接的に影響します。 セッション番号ディメンションは、 [!DNL Page View Condition];したがって、考えると [!DNL Session Number] ～に関連して [!DNL Page Views]に含めると、ページビューのないセッションを含めることができます。

のデフォルトの実装 [!DNL Site] を含む [!DNL Transformation Dataset Include] ページビュー可算ディメンションと関連する [!DNL Page View Condition] が定義されている。

可算ディメンションについて詳しくは、 [拡張Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Page View Condition の設定を編集するには**

1. を開きます。 [!DNL Profile Manager] データセットプロファイル内で、 [!DNL Dataset\Transformation\Traffic\Page View.cfg] ファイル。

   >[!NOTE]
   >
   >の実装をカスタマイズしている場合 [!DNL Site]に設定すると、これらの設定が存在するファイルが、説明した場所と異なる場合があります。

1. のパラメーターの値を確認または編集する [!DNL Page View Condition] 必要に応じて。 以下の例を参考にしてください。このファイルでは、 [!DNL Page View Condition] が [!DNL Copy] 変換。 このファイルには、Page View 可算ディメンションも定義されていることに注目してください。

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >可算ディメンションについて詳しくは、 [拡張Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). 詳しくは、 [!DNL Copy] 変換については、 [データ変換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. 右クリックしてファイルを保存 **[!UICONTROL (modified)]** ウィンドウの上部で、「 **[!UICONTROL Save]**.

1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

## URI ディメンション {#section-348f7e9099d049d197a7cdcbc8a6c234}

[!DNL Site] を利用する場合、閲覧された Web サイトページの URI ステムをエレメントに持つ URI ディメンションを定義する必要があります。デフォルトの実装には、 [!DNL Transformation Dataset Include] URI シンプルディメンションを定義するファイル。

シンプルディメンションについて詳しくは、 [拡張Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**URI ディメンションの設定を編集するには**

1. を開きます。 [!DNL Profile Manager] データセットプロファイル内で、 [!DNL Dataset\Transformation\Traffic\URI.cfg] ファイル。

   >[!NOTE]
   >
   >の実装をカスタマイズしている場合 [!DNL Site]に設定すると、これらの設定が存在するファイルが、説明した場所と異なる場合があります。

1. このファイルのパラメーターの値を確認し、必要に応じて編集します。以下の例を参考にしてください。

![](assets/cfg_WebParameters_URI.png)

この URI ディメンションの設定には、次の 2 つのパラメーターが含まれています。

* **Case Sensitive：** true または false。true の場合、アルファベットの大文字と小文字を区別して、ページを一意に特定します。デフォルト値は true です。
* **Maximum Elements：** URI ディメンションのエレメント（つまり URI）の最大数。デフォルト値は 32768 です。

   >[!NOTE]
   >
   >この値を変更すると、パフォーマンスに重大な問題が発生する可能性があります。 変更が必要な場合は必ずアドビまでご相談ください。

* 保存する [!DNL URI.cfg] ファイルを右クリック **[!UICONTROL (modified)]** ウィンドウの上部で、「 **[!UICONTROL Save]**.

* ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

## Referrer ディメンション {#section-8a97ec34d18b4814b5f95495ac4f8638}

[!DNL Site] を利用する場合、Referrer ディメンションを定義する必要があります。Referrer ディメンションの構成エレメントは、すべてのセッションの最初に出現するログエントリのリファラーの第 2 レベルドメインです。デフォルトの実装には、 [!DNL Transformation Dataset Include] ファイルに含まれます。

シンプルディメンションについて詳しくは、 [拡張Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Referrer ディメンションの設定を編集するには**

1. を開きます。 [!DNL Profile Manager] データセットプロファイル内で、 [!DNL Dataset\Transformation\Traffic\Referrer.cfg] ファイル。

   >[!NOTE]
   >
   >の実装をカスタマイズしている場合 [!DNL Site]に設定すると、これらの設定が存在するファイルが、説明した場所と異なる場合があります。

1. このファイルのパラメーターの値を確認し、必要に応じて編集します。以下の例を参考にしてください。

   ![](assets/cfg_WebParameters_Referrer.png)

   この Referrer ディメンションの設定には、Referrer ディメンションのエレメント（リファラー）の最大数を指定する Maximum Elements パラメーターが存在します。デフォルト値は 32768 です。

   >[!NOTE]
   >
   >上記の例では、 [!DNL Maximum Elements] パラメータが 0 に設定されている。 このパラメーターを 0 に設定した場合、Data Workbench サーバーの内部的なデフォルト値である 32768 が使用されます。

1. 保存する [!DNL Referrer.cfg] ファイルを右クリック **[!UICONTROL (modified)]** ウィンドウの上部で、「 **[!UICONTROL Save]**.

1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

## セッションのパラメーター {#section-0a209b0c504041a5801f7f71a963c8b1}

[!DNL Site] を利用する場合、Web サイトにおける訪問者のセッションの境界を定義するパラメーターを指定できます。これらのパラメーターは、 [!DNL Transformation Dataset Include] ファイルを [!DNL Site] 実装。

次のパラメーターは、のメンバーにできる点で一意です [!DNL Transformation Dataset Include] ファイルの [!DNL Parameters] ベクトルを指定するか、個々のパラメーターとして [!DNL Transformation.cfg]ファイル。 パラメーターは 1 回しか定義できないので、これらのパラメーターは [!DNL Transformation.cfg] ファイルに定義するか、データセットインクルードファイルの [!DNL Parameters] ベクトルに定義するか、のどちらかとなります。両方のファイルに定義することはできません。**Maximum Session Duration と Session Timeout**

Maximum Session Duration と Session Timeout は、訪問者のセッション期間を定義する文字列パラメーターです。セッション期間は、これらのパラメーターに、Internal Domains パラメーターを加味して決定されます。

Maximum Session Duration は、セッションの最長期間を指定します。この期間を超えると、新しいセッションが開始されます。コンテンツが自動的に最新の情報に更新されるよう設定されている Web ページで、際限なく長いセッションが作成されるのを防ぐことが、その目的です。クリックのリファラーが、Internal Domains パラメーターのいずれかのエントリに設定された場合、このタイムアウトを使用してセッションの終了が定義されます。セッション期間は、そこで行われたクリック数に関係なく、指定された Maximum Session Duration が上限となります。推奨値は 48 時間です。

Session Timeout は、特定の訪問者について、1 セッションの終了（新しいセッションの開始）と見なすログエントリ間の経過時間を指定します。つまり、ユーザーの活動期間を定義するための標準的なタイムアウトを表します。このパラメーターの推奨値は 30 分です。クリックのリファラーが、Internal Domains パラメーターのいずれのリファラーにも設定されなかった場合、このタイムアウトを使用してセッションが定義されます。ログエントリの cs(referrer-domain) がいずれかの内部ドメインに該当した場合、現在のログエントリを既存のセッションに含めるか、新たに開始したセッションに含めるかは、Maximum Session Duration によって決定されます。

サイトを閲覧している途中、訪問者が電話に出るために、Session Timeout を超える期間、コンピューターから離れる状況を考えてみましょう。席に戻ってきた時点ですぐに、先ほど読みかけのところから閲覧を続行するものとします。訪問者はサイトを離脱しておらず、ブラウザーを終了したわけでもないので、次にクリックしたときの cs(referrer-domain) は内部ドメインと一致します。この訪問者の元のセッションは、Maximum Session Duration の設定に達しない限り、アクティブなままです。このサイトのドメインが内部ドメインとしてリストされており、なおかつ最大タイムアウトに達していなければ、この訪問者が行った対話操作は、2 つの別個のセッションとしてではなく、単一のセッションと見なされます。一方、訪問者がコンピューターに戻って、次にクリックしたときのリファラーが外部（またはブランク）のドメインであった場合は、新しいセッションが開始されます。

>[!NOTE]
>
>この [!DNL Sessionize] 変換の [!DNL Timeout Condition] は、訪問者のセッションの長さの決定にも役立ちます。 Session Timeout と Maximum Session Duration が該当しない場合、新しいセッションの開始と見なすべきログエントリであるかどうかは、[!DNL Timeout Condition] をチェックして判断されます。詳しくは、 [データ変換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Maximum Session Duration パラメーターと Session Timeout パラメーターを編集するには**

を使用して [!DNL Site]の場合、デフォルトの実装には次のようなものが含まれています [!DNL Transformation Dataset Include] ファイル内で、これらのパラメーターの名前と推奨値が指定されています。

1. を開きます。 [!DNL Profile Manager] データセットプロファイル内で、 [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >の実装をカスタマイズしている場合 [!DNL Site]に値を指定しない場合、これらのパラメーターを定義するファイルが、説明した場所と異なる場合があります。

1. パラメーターの値を必要に応じて編集します。必ず適切な単位（分、時など）を指定してください。

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. 保存する [!DNL Session Parameters.cfg] ファイルを右クリック **[!UICONTROL (modified)]** をクリックし、 **[!UICONTROL Save]**.

1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列、「 **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

**[!DNL Internal Domains]**

[!DNL Internal Domains] は、特定の Web サイトに属するものとして扱うべきドメインレベルのホスト（内部リファラー）をリストするベクトルパラメーターです。これらのホストは、リファラーディメンション（一連の外部リファラー情報）から除外されます。内部ドメインとしてリストされているいずれかの文字列と cs(referrer-domain) が一致した場合、Session Timeout は無視され、Maximum Session Duration を使用してセッション期間が決定されます。

セッションのタイムアウト時間を超えて同じ会社の複数の関連ドメインを訪問者が行き来したときの新しいセッションの開始は、Internal Domains パラメーターを使用して回避することもできます。例えば、ある会社がその一部のサイトを、ログの記録対象となるドメイン（[!DNL xyz.com]）とならないドメイン（[!DNL xyz-unlogged.com]）の 2 つに分割しているとします。2 つのドメイン間を自由に行き来できるようにこれらのサイトが統合されている場合、訪問者が [!DNL xyz-unlogged.com] ドメインから [!DNL xyz.com] ドメインに戻ってくるたびに異なるセッションを生成するのは適切とはいえません。このような場合には、[!DNL xyz-unlogged.com] を内部ドメインとして登録すれば、トラフィックが 2 つのドメインの境界を越えても、Maximum Session Duration 設定に達しない限り、複数のセッションに分割されることはありません。

**内部ドメインを追加するには**

を使用して [!DNL Site]の場合、デフォルトの実装には [!DNL Transformation Dataset Include] ファイルを参照してください。 対象となるパラメーターは、このファイルの中で指定します。必要な作業は、追加したい内部ドメインを入力してファイルを保存するだけです。

1. を開きます。 [!DNL Profile Manager] データセットプロファイル内で、 [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >の実装をカスタマイズしている場合 [!DNL Site]の場合、Internal Domains パラメーターが定義されているファイルが、説明されている場所と異なる場合があります。

1. 右クリック **[!UICONTROL Value]** 」と入力し、「 **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. 必要に応じて値を編集します。

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. 保存する [!DNL Internal Domains.cfg] ファイルを右クリック **[!UICONTROL (modified)]** をクリックし、 **[!UICONTROL Save]**.

1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。
