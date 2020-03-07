---
description: ファイルをプロファイルから削除する権限がない、またはファイルを恒久的には削除したくない場合、空の（0 バイト）ファイルを使用してファイルを非表示にできます。
solution: Analytics
title: ファイルを空にして非表示にする（0バイト）
topic: Data workbench
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ファイルを空にして非表示にする（0バイト）{#hide-a-file-by-emptying-it-zero-byte}

ファイルをプロファイルから削除する権限がない、またはファイルを恒久的には削除したくない場合、空の（0 バイト）ファイルを使用してファイルを非表示にできます。

In the [!DNL Profile Manager], a hyphen (-), instead of a check mark, in a column identifies a zero-byte file.

![](assets/vis_ProfMgr_Zero-byte.png)

Unlike the other methods of hiding files (such as [!DNL order.txt], the Show parameter, and the Hidden parameter), Data Workbench treats zero-byted files as non-existent. 例えば、ビジュアライゼーションまたは指標定義で使用されているディメンションを0バイトにすると、Data Workbenchはそのビジュアライゼーションまたは指標に対してそれぞれエラーを生成します。

この機能は、以下を行いたい場合など、多くの理由で役立ちます。

* **ファイルの削除に必要なプロファイル権限を必要とせずに** 、Data Workbenchでファイルを使用不可にします。
* 元の場所からのファイルの削除に必要なプロファイル権限なしで、別の場所に&#x200B;**指標、ディメンションまたはフィルターを移動します**。
* **メニュー項目を非表示にします** 例えば、ファイル内 [!DNL Base] でプロファイルが [!DNL Metric Legend] 定義されていると [!DNL Metric.vw] します。 指標を追加／指標サブメニューに表示する 3 つの指標の凡例を会社が作成したとします。[!DNL Base] プロファイルの [!DNL Metric.vw] ファイルを 0 バイトにして、新しいサブメニューと 3 つの新しい指標の凡例のみを表示するようにできます。

**ファイルを非表示にするには**

1. In the [!DNL Profile Manager], open the necessary folders and subfolders to locate the file that you want to zero-byte.
1. Right-click the check mark next to the name of the file and click **[!UICONTROL Make Local]**.
1. ローカルファイルを開き、内容を削除します。
1. ファイルを保存して閉じます。

