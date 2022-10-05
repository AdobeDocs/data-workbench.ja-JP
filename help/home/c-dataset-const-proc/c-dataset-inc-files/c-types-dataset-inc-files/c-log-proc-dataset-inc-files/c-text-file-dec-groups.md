---
description: ログファイルをログソースとして処理するためには、ログエントリからデータフィールドを抽出するデコーダーをログ処理データセットインクルードファイル内で定義する必要があります。
title: テキストファイルデコーダーグループ
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
exl-id: e9f6e02e-7150-455f-96f0-f34d98cc31b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 68%

---

# テキストファイルデコーダーグループ{#text-file-decoder-groups}

{{eol}}

ログファイルをログソースとして処理するためには、ログエントリからデータフィールドを抽出するデコーダーをログ処理データセットインクルードファイル内で定義する必要があります。

ログファイルログソースに使用するテキストファイルデコーダーグループを定義するには、ログファイルの構造と内容、抽出するデータ、データが格納されているフィールドに関する知識が必要となります。デコーダーに関して指定できるパラメーターの基本的な事柄はこの節で説明していますが、デコーダーの使用方法は、ソースデータを含んでいるログファイルによって異なります。

ログファイルログソースの形式の要件について詳しくは、 [ログファイル](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e). テキストファイルデコーダーの定義に関して不明な点がありましたらアドビにお問い合わせください。

テキストファイルデコーダーグループには、次のデコーダーを含めることができます。

* [正規表現デコーダー](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [区切り文字デコーダー](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## 正規表現デコーダー {#section-67aca2c1f008404da7f845a64abec97c}

正規表現デコーダーは、ログファイルのログエントリに含まれる複雑な文字列パターンを識別し、データフィールドとして抽出します。デコーダーごとのフィールドの数は、正規表現で捕捉するサブパターンの数と一致している必要があります。対象となる行の n 番目に捕捉するサブパターンと一致する部分は、その行の n 番目のフィールドに割り当てられます。

**テキストファイルデコーダーグループに正規表現デコーダーを追加するには**

1. を開きます。 [!DNL Log Processing Dataset Include] の説明に従ってファイルを作成します。 [既存のデータセットインクルードファイルの編集](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) テキストファイルデコーダーグループを追加します。 テーブルエントリを参照 [デコーダーグループ](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. 右クリック **[!UICONTROL Decoders]** 新しく作成したデコーダーグループで、 **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. 次の情報を指定します。

   * **Fields：**&#x200B;ログファイル内のフィールドの一覧。ここで定義したフィールドのいずれかをデータセット構築の変換段階に渡す場合、それらのフィールドを [!DNL Log Processing Dataset Include] ファイルに含まれています。 カスタムフィールドの名前は、先頭に「x-」を付ける必要があります。

   * **Name：**（省略可）デコーダーの識別子。
   * **Regular Expression：**&#x200B;ファイル内の各行から必要なフィールドを抽出するために使用します。

1. グループに追加する他のデコーダーについても手順 4 と手順 5 を繰り返します。
1. 次の手順で [!DNL Log Processing Dataset Include] ファイル、右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列。 クリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。

アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

>[!NOTE]
>
>特定のログファイルには、複数の正規表現デコーダーを含めることができます。 この場合、デコーダーを定義する順序が重要となります。ログファイル内の行と一致する最初のデコーダーが、その行のデコードに使用されます。

以下に示したのは、正規表現デコーダーを使用して、タブ区切りのテキストファイルから一連のフィールドデータを抽出する例です。同じ結果は、タブ区切り文字デコーダーを定義することによっても得られます。

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

正規表現デコーダー（用語と構文を含む）について詳しくは、 [正規表現](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

## 区切り文字デコーダー {#section-7e0a23decdbc4c75ae750a42446997a6}

区切り文字デコーダーは、各フィールドが単一の文字で区切られたログファイルをデコードするものです。フィールドの数は、区切り文字ファイル内の列数と対応している必要はありますが、必ずしもすべてのフィールドを指定する必要はありません。フィールドを省略した場合、ログファイルには必要な列であっても、デコーダーはそのフィールドを無視します。

**テキストファイルデコーダーグループに区切り文字デコーダーを追加するには**

1. を開きます。 [!DNL Log Processing Dataset Include] の説明に従ってファイルを作成します。 [既存のデータセットインクルードファイルの編集](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) テキストファイルデコーダーグループを追加します。 テーブルエントリを参照 [デコーダーグループ](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. 右クリック **[!UICONTROL Decoders]** 新しく作成したデコーダーグループで、 **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. 次の情報を指定します。

   * **Fields：**&#x200B;ログファイル内のフィールドの一覧。ここで定義したフィールドのいずれかをデータセット構築の変換段階に渡す場合、それらのフィールドを [!DNL Log Processing Dataset Include] ファイルに含まれています。 カスタムフィールドの名前は、先頭に「x-」を付ける必要があります。

   * **Delimiter：**&#x200B;出力ファイル内のフィールドの区切りに使用する文字。

1. グループに追加する他のデコーダーについても手順 4 と手順 5 を繰り返します。
1. 次の手順で [!DNL Log Processing Dataset Include] ファイル、右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]をクリックし、 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*（ profile name は、データセットインクルードファイルが属するデータセットプロファイルまたは継承プロファイルの名前です）。

>[!NOTE]
>
>アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

以下に示したのは、区切り文字デコーダーを使用して、映画に関するデータを含んだコンマ区切り形式のテキストファイルから一連のフィールドデータを抽出する例です。

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)
