---
description: 内部プロファイルや他の継承プロファイルから設定ファイルを継承したくない場合（つまり、そのファイル内の命令をデータセットの構築中に無視したい場合）で、なおかつ、そのファイルに変更を加えることは避けたいという場合は、空の（ゼロバイトの）ファイルを同じ名前で作成し、そのファイルを別のプロファイルに保存するようにします。
solution: Analytics
title: データセット設定ファイルの非表示
topic: Data workbench
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データセット設定ファイルの非表示{#hiding-dataset-configuration-files}

内部プロファイルや他の継承プロファイルから設定ファイルを継承したくない場合（つまり、そのファイル内の命令をデータセットの構築中に無視したい場合）で、なおかつ、そのファイルに変更を加えることは避けたいという場合は、空の（ゼロバイトの）ファイルを同じ名前で作成し、そのファイルを別のプロファイルに保存するようにします。

**ゼロバイトのデータセット設定ファイルを作成するには**

1. In the [!DNL Profile Manager], open the necessary folders and subfolders to locate the file that you want to zero-byte.
1. Right-click the check mark next to the name of the file and click **[!UICONTROL Make Local]**.
1. メモ帳などのテキストエディターでローカルファイルを開き、その内容を削除します。
1. ファイルを保存して閉じます。
1. In the [!DNL Profile Manager], save the zero-byte file to a profile to the right of the profile in which the original file resides. （元のファイルよりもゼロバイトのファイルが優先されるようにするため）。

   In the [!DNL Profile Manager], a hyphen (-), instead of a check mark, in a column identifies the zero-byte file as shown in the example below.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

データセットを再処理すると、元のファイルで定義されていたデータセットのコンポーネントはなくなっています。

>[!NOTE]
>
>ビジュアライゼーションまたは指標定義で使用される拡張ディメンションを定義する設定ファイルを0バイトにすると、Data Workbenchはそのビジュアライゼーションまたは指標に対してそれぞれエラーを生成します。

ゼロバイトのファイルを使用して、指標、ディメンションまたはフィルターをプロファイル内の別の場所に移動したり、メニューアイテムを非表示にしたりすることもできます。詳しくは、『*Data Workbench ユーザーガイド*』を参照してください。
