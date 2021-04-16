---
description: レポートポータルで正しく表示されるレポートを生成するには、レポートセットを特定の方法で設定する必要があります。
title: Report Portal ユーザーインターフェイスのカスタマイズ
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Report Portal ユーザーインターフェイスのカスタマイズ{#customize-the-report-portal-user-interface}

レポートポータルで正しく表示されるレポートを生成するには、レポートセットを特定の方法で設定する必要があります。

[!DNL Report Portal]のユーザーインターフェイスは、出力ディレクトリに表示され、[!DNL profiles.xml]ファイルに一覧表示される各レポートセットフォルダーのタブと、表示する[!DNL TopNavigation.xml]ファイルに追加する必要のある組み込みの[!DNL Admin]タブを表示するように設計されています。 組み込みの「[!DNL Admin]」タブの表示について詳しくは、[ユーザーの「タブへの出力フォルダーのリンク」を参照してください。](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)。

![](assets/report_portal_home.png)

* [レポートセットがレポートポータルと互換性があることを確認する…](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [出力フォルダーをユーザーのタブにリンクする…](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## レポートセットとレポートポータルとの互換性の確認{#section-2b141e5d198a4bbea455699126c24706}

レポートセットは[!DNL Report]のスケジュール済みジョブを定義します。 2つの項目で構成されます。

* [!DNL Report]でレポートとして生成するワークスペースのコレクションを定義するフォルダー。
* 構成ファイル([!DNL Report.cfg])

特に、[!DNL Report.cfg]ファイルは[!DNL Report]にレポートを生成するタイミングと出力ファイルを保存する場所を指示します。 レポートセットは、Data WorkbenchサーバーのReportsフォルダーにあります。 プロファイルには、任意の数のレポートセットを表示できます。

[!DNL Report Portal]との互換性を確保するには、レポートセットが次の要件を満たしている必要があります。

* レポートセットの出力ディレクトリには、設定済みの[!DNL profiles.xml]ファイルが含まれている必要があります。
* 各レポートセットには、「*ReportSetName* Summary」という名前の最上位レベルのレポートが含まれている必要があります。ここで、*ReportSetName*&#x200B;は、レポートセットの名前と一致します。 例えば、次の[!DNL Profile Manager]は、「ホーム」と「トラフィック」の2つのレポートセットを示しています。 各レポートセットには、サマリレポート（ [!DNL Home Summary.vw]と[!DNL Traffic Summary.vw] ）が定義されています。

![](assets/rptPort_scrn_RptSets.png)

[!DNL Report Portal]には、サマリレポートがレポートセットのタブに表示されます。 サマリレポートには、任意のワークスペース、ウィンドウまたはビジュアライゼーションを選択できます。

* サマリレポートは、レポートセットの最上位フォルダー内にある唯一のレポートである必要があります。 その他のすべてのレポートは、サブフォルダに配置する必要があります。 その他のレポートを最上位フォルダに配置した場合、ポータル経由で表示することはできません。

## ユーザーインターフェイスのタブへの出力フォルダーのリンク{#section-3f6bc47d37ed448e871f4f685f46acee}

[!DNL Report Portal]に表示するタブを指定するには、各プロファイルに対して[!DNL TopNavigation.xml]ファイルを設定する必要があります。 このファイルは、特定のプロファイルのユーザーインターフェイスにタブとして表示されるレポートセットと、それらのタブの順序を決定します。 [!DNL TopNavigation.xml]ファイルは\*PortalName*\PortalFiles\Core\TopNav\*profileName*フォルダーにあります。

**TopNavigation.xmlファイルを編集するには**

1. IISが実行されているマシン上で、[!DNL TopNavigation.xml]ファイルをメモ帳などのテキストエディターで開きます。
1. `<TopNav>`要素のリストを編集して、[!DNL Report Portal]に出力を表示するレポートセットの名前と順序を定義します。次に例を示します。

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <TOPNAV_ELEMENTS>
   <TOPNAV>
       <NAME>Monthly Web</NAME>
     </TOPNAV>
     <TOPNAV>
       <NAME>Weekly Web</NAME>
     </TOPNAV>
   <TOPNAV> 
         <NAME>Admin</NAME> 
     </TOPNAV>
   </TOPNAV_ELEMENTS>
   ```

   >[!NOTE]
   >
   >[!DNL Admin]タブは追加機能を提供する組み込みタブです。 [!DNL TopNavigation.xml]ファイルに含めないと、このタブは表示されず、機能しません。

1. \*PortalName*\PortalFiles\Core\TopNav\ folderに、次のプロファイル用のフォルダを作成します。
1. 最初のフォルダーから[!DNL TopNavigation.xml]ファイルをコピーし、新しいプロファイルーに貼り付けます。
1. 必要に応じて[!DNL TopNavigation.xml]を編集し、ファイルを保存します。
1. ポータルで使用可能なその他すべてのプロファイルに対して手順3 ～ 5を繰り返します。
