---
description: この節では、指標を作成する方法について説明します。Data Workbench
title: 指標のセットアップ
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
exl-id: a60c08d3-f708-43be-a14f-8b7f129f3ee5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 38%

---

# 指標のセットアップ{#metrics-setup}

{{eol}}

この節では、指標を作成する方法について説明します。Data Workbench

## 指標について {#section-f0412e851fcb4ac9886dca4003d42cec}

指標は、表示回数、注文件数、実行された呼び出し数、売上高など、顧客の行動に関する量的な情報です。 指標はレポートの基盤であり、データの関係性を確認して把握する助けになります。

指標のDimensionでは、指標のカウントを特定のレベル別にグループ化できます。 また、指標カウントを特定のレベルでグループ化することもできます。

## 新しい指標の作成 {#section-60a413899d1b4707965e06fb5ef7fc4e}

以下の手順に従って、新しい指標を作成します。

1. クリック **ツール** > **指標エディター**.

1. 指標エディターで、新しい指標名と数式を入力します。 ![](assets/dwb_impl_metrics1.png)

1. 指標フォルダーに保存します。 ![](assets/dwb_impl_metrics2.png)

## 派生指標の作成と編集 {#section-ebdcd3ec652f485e90e001d694eab6d0}

指標エディターを使用して、名前、数式、形式で新しい指標を定義し、指標エディターを [!DNL User\profile_name\Metrics] 後で使用するためのフォルダー。

1. **管理者／プロファイル**&#x200B;メニューオプションを使用するか、指標を作成するフォルダーの User 列を右クリックし、**作成／新しい指標**&#x200B;をクリックして、新しい指標エディターを開きます。指標エディターが表示されます。

1. 内 *名前* パラメーターに、新しい指標の名前を入力します。

   >[!NOTE]
   >
   >スペース（ ）は使用できますが、アンダースコア（_）は使用できません。また、以下の記号は使用できません。 + - &#42; /

   ![](assets/dwb_impl_metrics3.png)

1. 内 *数式* パラメーターを入力し、新しい指標の式を入力します。

   >[!NOTE]
   >
   >フィルターは角括弧内で定義する必要があります [ ] を式に含めます。 その他の指標式の構文ルールについては、 [指標式の構文を参照してください。](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   次の表は、拡張指標の式の例を示しています。 ![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   >
   >適切な式を入力すると、プレビュー行に新しい指標の値が表示されます。 式にエラーがある場合は、プレビュー行にエラーメッセージが表示されます。

1. 右クリックして「 」を選択します。 **保存**. 指標を保存すると、新しい指標を表すファイルがコンピューターの DWB に作成されます *インストールディレクトリ\User\profile name\Metrics* フォルダー。

## 既存の派生指標の編集 {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. プロファイルマネージャーまたは 指標マネージャーの profile name 列で、編集する指標ファイルのチェックマークを右クリックし、「**ローカル化**」をクリックします。
1. User 列の指標ファイルのチェックマークを右クリックし、 **開く** 」を選択します。

   >[!NOTE]
   >
   >また、ビジュアライゼーション内の指標関連領域を右クリックして指標エディターを開き、指標メニューを表示することもできます。

1. **指標エディター**&#x200B;で、*新しい派生指標の作成*&#x200B;の手順 2 ～ 4 を使用して、必要に応じて指標定義を編集し、保存します。

   編集した指標をプロファイルのすべてのユーザーが使用できるようにする場合は、プロファイルマネージャーを使用して、作成した指標を作業プロファイルに公開する必要があります。 

サポートが必要な場合は、ドキュメントを参照してください。

[指標式の構文](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[派生指標の作成と編集](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
