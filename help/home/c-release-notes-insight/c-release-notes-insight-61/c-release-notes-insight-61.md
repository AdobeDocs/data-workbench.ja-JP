---
description: Data Workbench 6.1 のリリースノートには、新機能、アップグレード要件、バグの修正および既知の問題が含まれています。
title: Data Workbench 6.1 のリリースノート
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
exl-id: ed37a00f-b4cd-428e-abb7-7c52d5cfd2f9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 87%

---

# Data Workbench 6.1 のリリースノート{#data-workbench-release-notes}

Data Workbench 6.1 のリリースノートには、新機能、アップグレード要件、バグの修正および既知の問題が含まれています。

## 新機能 {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.1 には、次の新機能が含まれています。

| 機能 | 説明 |
|--- |--- |
| 64-bit Windows のアップグレード | アップグレード後の Data Workbench のサーバー、レポートサーバーおよびクライアントコンポーネントは、64-bit Windows オペレーティングシステム上でのみ動作します。 |
| 傾向スコアリング | オーディエンスをスコアリングすると、顧客のロイヤルティを特定し、販売をコンバージョンしたり、ストーリーやキャンペーンに対して何らかのアクションを起こしたりする可能性が高い顧客を統計的に把握することができます。傾向スコアリングには、モデルを表示し、選択した指標の変化する相関を示す次のビジュアライゼーションが含まれるようになりました。<ul><li>モデルビューアでは、傾向スコアリングで生成されたロジスティック回帰モデルを調べ、（定数項を含む）各入力変数の係数の重みとその統計的な誤差範囲が表示されます。 </li><li>リフトチャートとゲインチャートは、スコアリング対象データモデルの潜在的な増加を評価する場合に使用します。</li><li>混同行列は、実際のポジティブ（AP）、実際のネガティブ（AN）、予測されたポジティブ （PP）、予測されたネガティブ（PN）の組み合わせによる 4 カウントを付与します。</li> <li>v6.1 以降では、ディメンション、またはディメンションと指標の 2 種類に基づいた傾向スコアリングを保存する保存オプションが追加されました。</li><li>Ctrl + Alt キーを押しながら、エレメントを傾向スコアリングおよびクラスタービルダーにドラッグ＆ドロップして追加できるようになりました。以前は、テーブルエレメントを追加するには、テーブルから「エレメント」ボックスにドラッグする必要がありました。</li></ul> |
| Data Workbench での中国語の使用 | Data Workbench では、現在、クライアントアプリケーションで簡体字中国語をサポートしています。また、Data Workbenchでは、Input Method Editor(IME)を、国際言語の2番目のテキスト入力プロセスとしてサポートしています。 |
| 数学関数 | 指標、数学変換およびワークシートのセルに数学関数を追加して、データセットに対してより複雑な計算を実行できるようになりました。 |
| 統計コールアウト | テーブルで指標列に対して統計の概要コールアウトが提供されるようになりました。コールアウトには、列の平均値、標準偏差値、最小値、最大値、平方偏差および合計数を表示できます。コールアウトは、任意の選択および評価に組み込むことができます。 |
| 相関行列フィルター | 相関行列に追加されたバイナリフィルターを使用すると、相関している指標のどちらかまたは両方の値を制限して、比較対象を絞り込むことができます。また、Ctrl + Alt キーを押しながら、エレメントを評価対象の行列の列または行にドラッグすることで、ディメンションテーブルからディメンションエレメントを追加できるようにもなりました。 |
| ファンネルビジュアライゼーションでのフォールアウトラベルの非表示 | ファンネルビジュアライゼーションで、タイトルを右クリックし、「フォールアウトを非表示」を選択すると、フォールアウトラベルの表示と非表示に切り替えることができます。 |

## テーブルの列の並べ替え{#sorting-table-columns}

テーブルの列をアルファベット順または序数別に並べ替えることができます。

Dimensionテーブル内の要素をより適切に選択するには、**[!UICONTROL Sort]**&#x200B;メニューオプションを選択して、最初の列をアルファベット順または序数別に並べ替えます。

列を序数別に並べ替えた場合は、# 文字が表示されます（デフォルト）。

**「並べ替え」オプションの選択**

並べ替えオプションを序数とアルファベットの間で変更するには、右クリックして&#x200B;**[!UICONTROL Sort]**&#x200B;を選択します。 順序を逆にするには、矢印をクリックします。

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>他の列は、その列の名前をクリックすると、序数別に並べ替えることができます。

## ファンネルでのフォールアウトラベルの非表示

ファネルビジュアライゼーションでフォールアウトラベルの開閉を切り替えることができます。

ファネルビジュアライゼーションでは、顧客がどこでマーケティングキャンペーンを中止したかや、Web サイトやチャネル間キャンペーンのインタラクト中にどこで定義済みのコンバージョンパスから離れたかを特定することができます。ファンネルビジュアライゼーションの左側には、訪問や訪問者の結果が表示されます。右側には、指定されたパスを中止した顧客の「フォールアウト」が表示されます。

![](assets/c_funnel_hide_fallout.png)

**[!UICONTROL Funnel]**&#x200B;ビジュアライゼーションでは、タイトルを右クリックし、メニューから「**[!UICONTROL Hide Fallout]**」を選択して、フォールアウトラベルを非表示にできます。

## 既知の問題 {#section-ff2180c6871c413480e15fa915c253b9}

* ワークスペースをインポートすると、インポートが成功した場合でも、エラーメッセージが表示されます。

   回避策：「OK」をクリックして、エラーを無視します。ワークスペースは、正常にインポートされます。

**簡体字中国語のローカリゼーションに関する問題**

* スコアリングビジュアライゼーションでターゲットを設定しているときに「送信」をクリックした後に表示されるダイアログのタイトルとメッセージが読めません。

   回避策：なし。
* ワークシートのビジュアライゼーションで折り返しを使用しても、ローカライズされた語句が正しく折り返されません。文字列に余計な文字が追加されます。

   回避策：なし。
* インストールディレクトリの名前に英語以外の文字が含まれている場合に、[!DNL Insight.exe] を起動することができません。

   回避策：デフォルトの名前のままにするか、フォルダーパスに英文字のみを使用して名前を変更して、実行可能ファイルを起動します。
