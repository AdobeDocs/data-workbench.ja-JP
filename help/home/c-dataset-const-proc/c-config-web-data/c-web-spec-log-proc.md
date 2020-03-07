---
description: Site 用プロファイルに付属のログ処理データセットインクルードファイルで定義する Web 固有の設定について取り上げます。
solution: Analytics
title: ログ処理に関する Web 固有の設定
topic: Data workbench
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# ログ処理に関する Web 固有の設定{#web-specific-settings-for-log-processing}

Site 用プロファイルに付属のログ処理データセットインクルードファイルで定義する Web 固有の設定について取り上げます。

これらの設定によって定義されたフィルタリングは、ログエントリがデコーダーから送出されて変換が適用された後、[!DNL Log Entry Condition] によって評価される前に適用されます。

* [HTTP ステータスのフィルタリング](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [ロボットのフィルタリング](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## HTTP ステータスのフィルタリング {#section-ac66acdcb6aa467d81c3721199e540fd}

sc-status コードが 400 以上のログエントリは、[!DNL Site] の導入環境の設定によって、データセットから除外することができます。リクエストに成功した場合、そのステータスコードは 400 より小さくなります。Your default implementation includes a [!DNL Log Processing Dataset Include] file in which HTTP status filtering is configured.

**HTTP ステータスのフィルタリング設定を編集するには**

1. データセットプ [!DNL Profile Manager] ロファイル内でを開き、ファイルを開 [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg] きます。

   >[!NOTE]
   >
   >If you have customized your implementation of [!DNL Site], the file in which these configuration settings exist may differ from the location described.

1. このファイルのパラメーターの値を確認し、必要に応じて編集します。以下の例を参考にしてください。

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   条件について詳しくは、「 [!DNL Range] 条件」を参照して [ください](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。

1. Save the [!DNL HTTP Status Filter.cfg] file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

## ロボットのフィルタリング {#section-7f43681dfbc64b969619cb88f97d5ad5}

[!DNL Site] の導入環境の設定でルックアップファイルを使用し、既知のロボットや自動テストツールによって生成されたログエントリ、さらには、内部ユーザーの IP アドレスによって生成されたログエントリをデータセットから除外することができます。デフォルトの実装には、ロボットのフ [!DNL Log Processing Dataset Include] ィルタリングが設定されたファイルが含まれます。

**ロボットのフィルタリング設定を編集するには**

1. データセットプ [!DNL Profile Manager] ロファイル内でを開き、ファイルを開 [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg] きます。

   >[!NOTE]
   >
   >If you have customized your implementation of [!DNL Site], the file in which these configuration settings exist may differ from the location described.

1. ファイルのパラメーターを確認し、必要に応じて編集します。次の例を参考にしてください。

   ![](assets/cfg_WebParameters_RobotFilter.png)

   このファイル内の [!DNL NotRobotCondition] には、次の 3 つのパラメーターが定義されています。

   * **Case Insensitive（ロボットのフィルタリングで大文字と小文字を区別しない）：** true または false。true の場合、ロボットのフィルタリングでアルファベットの大文字と小文字が区別されません。
   * **Robot Lookup File, Baseline：**&#x200B;ロボットであることが確認されており、データセットから除外すべきブラウザーユーザーエージェントをリストしたテキストファイルのパスとファイル名。基本的なロボットルックアップファイルがアドビから提供されています。パスを指定しなかった場合、Data Workbench サーバーのインストールディレクトリ内にある Lookups ディレクトリからこのファイルが検索されます。
   * **Robot Lookup File, Extended：**&#x200B;導入環境に固有のロボット（ブラウザーユーザーエージェントまたは IP アドレス）をリストしたオプションのテキストファイルのパスとファイル名。このリストには、内部のモニタリングロボットや自動テストツールのほか、データセットから除外すべき内部ユーザーの IP アドレスを含めることができます。パスを指定しなかった場合、Data Workbench サーバーのインストールディレクトリ内にある Lookups ディレクトリからこのファイルが検索されます。
   ログエントリのブラウザーユーザーエージェントがどちらのルックアップファイルにもリストされていなかった場合、そのログエントリは、実在する訪問者によって生成されたものと見なされ、データセットから除外されません。

   >[!NOTE]
   >
   >ロボットルックアップファイル内での照合では、サブ文字列を使用してc-ipとcs(user-agent)のログフィールドと比較します。 検索文字列が「$」で始まっている場合、テスト対象となる文字列の先頭部分と一致している必要があります。同様に、検索文字列が「$」で終わっている場合、テスト対象となる文字列の末尾部分と一致している必要があります。検索文字列の最初と最後の両方に「$」が存在する場合、ログエントリが除外されるためには、その検索文字列と完全に一致していることが必要です。例えば、クラス C ブロックのすべての IP アドレスがテストの対象であれば、「$231.78.123.」などの文字列を使用して、文字列の先頭部分とのマッチングを強制する必要があります。この場合、231.78.123.0 ～ 231.78.123.255 のアドレスと一致することになります。

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

   アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

   >[!NOTE]
   >
   >データセットの構築に使用される基になるログエントリが変更されない（データセットの構築と更新に使用される変換とディメンションが変更された場合でも）ことが重要な場合は、Robot Lookup File、Baseline、Robot Lookup File、Extendedをバージョン管理する必要があります。 デフォルトのロボットルックアップファイルが更新されると、そのファイル内のエントリが追加されたり削除されたりすることで、既に構築済みのレポートデータセットが意図せず変化してしまいますが、これらのファイルにバージョン番号を設定すれば、そのようなことを確実に防ぐことができます。

