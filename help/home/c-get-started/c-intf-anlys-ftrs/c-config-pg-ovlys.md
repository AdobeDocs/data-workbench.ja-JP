---
description: ページオーバーレイは Site アプリケーションでのみ設定できますが、他のアプリケーション用にも設定可能です。
solution: Analytics
title: ページオーバーレイの設定
topic: Data workbench
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configure a page overlay{#configure-a-page-overlay}

ページオーバーレイは Site アプリケーションでのみ設定できますが、他のアプリケーション用にも設定可能です。

別のアプリケーション用のページオーバーレイの設定については、Adobe Consulting Services にお問い合わせください。

ページオーバーレイのビジュアライゼーションは、HTML リンク分析のためのツールです。特定のページのオーバーレイをリクエストすると、Data Workbenchは、Webブラウザーに表示される実際のページのスナップショットを取り、定義した正規表現のリストに従って、リンクを表すHTMLコードを解析します。 選択されたページ上のリンクごとに、data workbench は最初の一致が見つかるまでリストを下方向に探し、正規表現パターンの一致を見つけようと試みます。一致が見つかった場合、そのリンクはページオーバーレイでハイライト表示されます。

ページオーバーレイを含むワークスペースに色凡例を追加すると、ページオーバーレイにはデータのみが表示されます。

>[!NOTE]
>
>ページオーバーレイの設定は慎重に行う必要があり、リンクが不適切にデータにマッピングされている場合、誤った結果が生じる可能性があります。 特定のサイトのページオーバーレイの設定に伴う作業は、そのサイトのページの HTML コード内でリンクがどのように表されるかによって異なります。

本来、ページオーバーレイは、「クリックする場所」を表示するメンタルモデルをユーザーに示します。ビジュアライゼーションの背後にあるデータがこのモデルに一致しない場合、混同が生じる可能性が高くなります。

[!DNL Site] では、リンクは次の URI ディメンションまたは次のリンクディメンションの要素を表すことが一般的ですが、分析に対して意味を持つ任意のディメンションにリンクをマッピングできます。他のアプリケーション用のページオーバーレイの設定については、Adobe Consulting Services にお問い合わせください。

>[!NOTE]
>
>ページオーバーレイに対するページディメンションの使用はお勧めしません。 ユーザーは Page（ページ）ディメンションの要素名を変更できるので、その結果、ページオーバーレイ機能が依存するリンク構文も変更されます。

[!DNL Site] 用のページオーバーレイを設定するには、次の 2 つのファイルを編集する必要があります。

* **[!DNL Page Overlay.vw]:**このファイルは、ページオーバーレイのビジュアライゼーションを作成するためのテンプレートファイルです。 ページオーバーレイを設定するプロファイル内に、少なくとも 1 つのテンプレートファイルが必要です。
* **[!DNL Page Overlay Link Templates.cfg]:**ページオーバーレイビジュアライゼーションは、ページを読み込むと、ページ内のリンクとそのリンク先を自動的に識別します。 これらのリンクをデータ内の要素に関連付けるには、このファイルに一連の正規表現を定義する必要があります。

   ディメンションの要素と照合する複数の正規表現を定義できます。表現を定義する順序が重要です。特定のページのオーバーレイをリクエストすると、Data Workbenchは、Webブラウザーに表示される実際のページのスナップショットを取り、定義した正規表現のリストに従って、リンクを表すHTMLコードを解析します。 選択されたページ上のリンクごとに、data workbench は最初の一致が見つかるまでリストを下方向に探し、正規表現パターンの一致を見つけようと試みます。ディメンション要素に最初に一致した表現が使用されます。したがって、最も限定的な照合パターンを最初に、あまり限定的でない表現が後になるように、正規表現をリストする方法が最適です。一致が見つかった場合、そのリンクはページオーバーレイのビジュアライゼーションでハイライト表示されます。

**Site** 用のページオーバーレイを設定するには

1. I

   で、// [!DNL Profile Manager]に移 **[!UICONTROL Context]** 動し **[!UICONTROL Dimension Element]** ます **[!UICONTROL URI]**。

   >[!NOTE]
   >
   >ディメンション要素ディレクトリには、ディメンション要素を右クリックすると表示されるコンテキストメニュー項目が含まれます。 例えば、URI テーブルを開いてから、URI 要素を選択します。URI を右クリックすると、ページオーバーレイが表示されます。

1. In the URI folder, right-click the check mark next to the [!DNL Page Overlay.vw] file and click **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL in Notepad]**&#x200B;す。
1. ドメイン（および必要に応じてブラウザーの高さ）を指定します。

   ```
   window = simpleBorderWindow: 
     client = scrollWindow: 
       client = PageOverlay: 
         URI Template = string: http://%Domain%%Element%
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
1. To make this change available to all users of the working profile, in the [!DNL Profile Manager], right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >他のサイトやサブドメイン用の追加のテンプレートファイルを作成できます。 作成した各テンプレートがに表示されま [!DNL Page Overlay menu]す。

1. のContextフォルダで、ファ [!DNL Profile Manager]イルの横のチェックマークを右クリックし、を [!DNL Page Overlay Link Templates.cfg] クリックしま **[!UICONTROL Make Local]**&#x200B;す。

   このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL from the workbench]**&#x200B;す。
1. 右クリックし、/ **[!UICONTROL Link Templates]** をクリ **[!UICONTROL Add new]** ックしま **[!UICONTROL Regular Expression]**&#x200B;す。
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
   <td colname="col1"> <p>Dimension </p> </td> 
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

1. To save the file, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. To make this change available to all users of the working profile, right-click the check mark for [!DNL Page Overlay Link Templates.cfg] in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
