---
description: ページオーバーレイは Site アプリケーションでのみ設定できますが、他のアプリケーション用にも設定可能です。
title: ページオーバーレイの設定
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
exl-id: 4e0dfce8-def2-49f3-93e8-41d82922fb88
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 64%

---

# ページオーバーレイの設定{#configure-a-page-overlay}

ページオーバーレイは Site アプリケーションでのみ設定できますが、他のアプリケーション用にも設定可能です。

別のアプリケーション用のページオーバーレイの設定については、Adobe Consulting Services にお問い合わせください。

ページオーバーレイのビジュアライゼーションは、HTML リンク分析のためのツールです。特定のページのオーバーレイを要求すると、Data Workbenchは、Web ブラウザーに表示される実際のページのスナップショットを作成し、定義した正規表現のリストに従って、リンクを表すHTMLコードを解析します。 選択されたページ上のリンクごとに、data workbench は最初の一致が見つかるまでリストを下方向に探し、正規表現パターンの一致を見つけようと試みます。一致が見つかった場合、そのリンクはページオーバーレイでハイライト表示されます。

ページオーバーレイを含むワークスペースに色凡例を追加すると、ページオーバーレイにはデータのみが表示されます。

>[!NOTE]
>
>ページオーバーレイの設定は慎重に行う必要があり、リンクが不適切にデータにマッピングされると、誤った結果を生み出す可能性があります。 特定のサイトのページオーバーレイの設定に伴う作業は、そのサイトのページの HTML コード内でリンクがどのように表されるかによって異なります。

本来、ページオーバーレイは、「クリックする場所」を表示するメンタルモデルをユーザーに示します。ビジュアライゼーションの背後にあるデータがこのモデルに一致しない場合、混同が生じる可能性が高くなります。

[!DNL Site] では、リンクは次の URI ディメンションまたは次のリンクディメンションの要素を表すことが一般的ですが、分析に対して意味を持つ任意のディメンションにリンクをマッピングできます。他のアプリケーション用のページオーバーレイの設定については、Adobe Consulting Services にお問い合わせください。

>[!NOTE]
>
>ページオーバーレイにページディメンションを使用することはお勧めしません。 ユーザーは Page（ページ）ディメンションの要素名を変更できるので、その結果、ページオーバーレイ機能が依存するリンク構文も変更されます。

[!DNL Site] 用のページオーバーレイを設定するには、次の 2 つのファイルを編集する必要があります。

* **[!DNL Page Overlay.vw]:** このファイルは、ページオーバーレイのビジュアライゼーションを作成するためのテンプレートファイルです。ページオーバーレイを設定するプロファイル内に、少なくとも 1 つのテンプレートファイルが必要です。
* **[!DNL Page Overlay Link Templates.cfg]:** ページオーバーレイのビジュアライゼーションがページを読み込むと、ページ内のリンクとその宛先が自動的に識別されます。これらのリンクをデータ内の要素に関連付けるには、このファイルに一連の正規表現を定義する必要があります。

   ディメンションの要素と照合する複数の正規表現を定義できます。表現を定義する順序が重要です。特定のページのオーバーレイを要求すると、Data Workbenchは、Web ブラウザーに表示される実際のページのスナップショットを作成し、定義した正規表現のリストに従って、リンクを表すHTMLコードを解析します。 選択されたページ上のリンクごとに、data workbench は最初の一致が見つかるまでリストを下方向に探し、正規表現パターンの一致を見つけようと試みます。ディメンション要素に最初に一致した表現が使用されます。したがって、最も限定的な照合パターンを最初に、あまり限定的でない表現が後になるように、正規表現をリストする方法が最適です。一致が見つかった場合、そのリンクはページオーバーレイのビジュアライゼーションでハイライト表示されます。

**Site** 用のページオーバーレイを設定するには

1. I

   [!DNL Profile Manager] で、**[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]** に移動します。

   >[!NOTE]
   >
   >Dimension要素ディレクトリには、ディメンション要素を右クリックしたときに表示されるコンテキストメニュー項目が含まれます。 例えば、URI テーブルを開いてから、URI 要素を選択します。URI を右クリックすると、ページオーバーレイが表示されます。

1. URI フォルダーで、[!DNL Page Overlay.vw] ファイルの横のチェックマークを右クリックし、**[!UICONTROL Make Local]** をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** をクリックします。
1. ドメイン（および必要に応じてブラウザーの高さ）を指定します。

   ```
   window = simpleBorderWindow:
     client = scrollWindow:
       client = PageOverlay:
         URI Template = string: https://%Domain%%Element%
         URI Parameters = map:
           Domain = string: domain name
           Element = ref: Element/Name
         Dim = ref: wdata/model/dim/URI
         Dim Element = ref: Element/Name
         Level = ref: wdata/model/dim/Page View
         Group = ref: wdata/model/dim/Session
         Browser Height = int: browser height
     pos = v3d: (518, 202, 0)
     size = v3d: (810, 610, 0)
     titleBar = editor:
       size = v3d: (61, 19, 0)
       text = string:
   ```

1. ファイルを保存します。
1. この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、[!DNL Profile Manager] で、[!DNL User] 列の [!DNL .vw] ファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL working profile name]*** をクリックします。

   >[!NOTE]
   >
   >他のサイトやサブドメイン用に、追加のテンプレートファイルを作成できます。 作成した各テンプレートが [!DNL Page Overlay menu] に表示されます。

1. [!DNL Profile Manager] の Context フォルダーで、[!DNL Page Overlay Link Templates.cfg] ファイルの横のチェックマークを右クリックし、**[!UICONTROL Make Local]** をクリックします。

   このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]** をクリックします。
1. **[!UICONTROL Link Templates]** を右クリックし、**[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]** をクリックします。
1. 必要に応じて、LinkRegex ベクトルのパラメーターを編集します。

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> パラメーター </th>
   <th colname="col2" class="entry"> 入力する情報 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>ディメンション </p> </td>
   <td colname="col2"> <p>リンクが表すディメンション（通常は次の URI ディメンション）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>式 </p> </td>
   <td colname="col2"> <p>Dimension の次の要素を探すため、HTML リンクの関連部分の選択に使用される正規表現。正規表現は完全一致でなければなりません。また、目的の出力パターンを丸括弧でグループ化します。正規表現について詳しくは、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Output Pattern </p> </td>
   <td colname="col2"> <p>Dimension パラメーターから得られる要素の抽出に使用される正規表現の出力パターン。 </p> </td>
  </tr>
 </tbody>
</table>

以下のファイル例は、3 つの正規表現を示しています。

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. ファイルを保存するには、ウィンドウ上部の **[!UICONTROL (modified)]** を右クリックし、**[!UICONTROL Save]** をクリックします。
1. この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、[!DNL User] 列の [!DNL Page Overlay Link Templates.cfg] のチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL working profile name]**>* をクリックします。
