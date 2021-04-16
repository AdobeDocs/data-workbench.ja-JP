---
description: Data Workbench のディメンションメニューに表示したくない拡張ディメンションは、Hidden パラメーターまたは Show パラメーターを使用して非表示にすることができます。
title: 拡張ディメンションの非表示
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 79%

---

# 拡張ディメンションの非表示{#hiding-extended-dimensions}

Data Workbench のディメンションメニューに表示したくない拡張ディメンションは、Hidden パラメーターまたは Show パラメーターを使用して非表示にすることができます。

いずれかのパラメーターに適切な設定を入力すると、そのディメンションは、Data Workbench のメニューに名前が表示されなくなるものの、プロファイルには依然として存在しており、引き続き使用することができます。Data Workbench のユーザーは、[!DNL Insight.cfg] ファイルの Unhide All パラメーターを true に設定することで、一時的にディメンションの非表示を解除することができます。

Unhide All パラメーターについて詳しくは、『*Data Workbench ユーザーガイド*』で、Data Workbench の設定パラメーターに関する付録を参照してください。

Hidden パラメーターと Show パラメーターを使用して拡張ディメンションを非表示にする方法について、以下の節で説明します。

* [Hidden パラメーターを使用した拡張ディメンションの非表示](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Show パラメーターを使用した拡張ディメンションの非表示](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Hidden パラメーターを使用した拡張ディメンションの非表示  {#section-7167a6f6241a4bc78f2f322e048d65cf}

Hiddenパラメーターは、[!DNL Transformation Dataset Configuration]ファイルで拡張ディメンションを定義する際に使用できるオプションのパラメーターです。

1. 非表示にする拡張ディメンションが定義されている[!DNL Transformation Dataset Configuration]ファイルを開きます。 「[既存のデータセットインクルードファイルの編集](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)」を参照してください。

1. 設定ウィンドウで目的のディメンションの Hidden パラメーターを探し、「*true*」と入力します。
1. ファイルをローカルに保存したうえで、サーバー上の適切なプロファイルに保存します。詳しくは、 [既存のデータセットインクルードファイルの編集](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

拡張ディメンションは、データセットの再変換後、Data Workbench のディメンションメニューに表示されなくなります。Hidden パラメーターについて詳しくは、 [拡張ディメンション](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Hidden パラメーターの設定を変更した場合、その変更を反映するには、データセットを再変換する必要があります。

## Show パラメーターを使用した拡張ディメンションの非表示  {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Showパラメーターは、[!DNL Transformation Dataset Configuration]ファイルで拡張ディメンションを定義するために使用できるパラメーターの1つではありません。 代わりに、パラメーターは、作成する派生ディメンションの[!DNL .dim]ファイルで定義されます。 そのため、Show パラメーターを使用して拡張ディメンションを非表示にするにはまず、以下の手順に従って、拡張ディメンションをベースに派生ディメンションを作成する必要があります。

1. メモ帳などのテキストエディターを使用して、&lt;*dimension name*>.dim という名前で空のファイルを作成します。ファイル名は、非表示にするディメンションと同じ名前であることが必要です。例えば、Next Page ディメンションを非表示にする場合、[!DNL Next Page.dim] というファイルを作成します。

1. このファイルに次のテキストを追加します。

   * entity = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. プロファイルの Dimensions ディレクトリにファイルを保存します。必要に応じてサブディレクトリにファイルを保存できます。

Show パラメーターを使用して拡張ディメンションを非表示にするときは、データセットを再変換しなくても、変更が反映されます。プロファイルのローカルバージョンでディメンションの表示/非表示を切り替えるか(つまり、[!DNL .dim]ファイルをUserプロファイルーに保存する)、または[!DNL .dim]ファイルをサーバーに保存しての他のユーザーが使用できます。

指標やフィルターを非表示にするときにも、Show パラメーターを使用できます。詳しくは、『*Data Workbench ユーザーガイド*』の「インターフェイスと分析機能の設定」という章を参照してください。
