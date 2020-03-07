---
description: レポートポータルで正しく表示されるレポートを生成するには、レポートセットを特定の方法で設定する必要があります。
solution: Analytics
title: レポートポータルのユーザインターフェイスのカスタマイズ
topic: Data workbench
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# レポートポータルのユーザインターフェイスのカスタマイズ{#customize-the-report-portal-user-interface}

レポートポータルで正しく表示されるレポートを生成するには、レポートセットを特定の方法で設定する必要があります。

のユーザーインターフェ [!DNL Report Portal] イスは、出力ディレクトリに表示され、ファイルに一覧表示される各レポートセットフォルダーのタブと、表示するファイルに追加する必要のある組み込みタブを表示するように設計さ [!DNL profiles.xml][!DNL Admin][!DNL TopNavigation.xml] れています。 組み込みタブの表示について詳しくは、「ユ [!DNL Admin] ーザーのタ [ブへの出力フォルダーのリンク」を参照してください。](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [レポートセットがレポートポータルと互換性があることを確認する…](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [出力フォルダーをユーザーのタブにリンクする…](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## レポートセットとレポートポータルの互換性の確認 {#section-2b141e5d198a4bbea455699126c24706}

レポートセットは、のスケジュール済みジョブを定義しま [!DNL Report]す。 次の2つの項目で構成されます。

* レポートとして生成するワークスペースのコレクションを定 [!DNL Report] 義するフォルダーです。
* 設定ファイル( [!DNL Report.cfg])。

特に、このファイルは、レ [!DNL Report.cfg] ポートを生 [!DNL Report] 成するタイミングと出力ファイルの保存場所を指定します。 レポートセットは、Data Workbenchサーバー上のReportsフォルダーにあります。 プロファイルには、任意の数のレポートセットを表示できます。

との互換性を確保するた [!DNL Report Portal]めに、レポートセットは次の要件を満たす必要があります。

* レポートセットの出力ディレクトリには、設定済みのファイルが含まれている必要が [!DNL profiles.xml] あります。
* 各レポートセットには、「*ReportSetName* Summary」という最上位レベルのレポートが含まれている必要があります。この場合、 *ReportSetNameは* 、レポートセットの名前と一致します。 例えば、次の図は、「ホ [!DNL Profile Manager] ーム」と「トラフィック」の2つのレポートセットを示しています。各レポートセットでは、それぞれ概要レポート(およ [!DNL Home Summary.vw] び)が [!DNL Traffic Summary.vw]定義されます。

![](assets/rptPort_scrn_RptSets.png)

では、 [!DNL Report Portal]サマリレポートがレポートセットのタブに表示されます。 サマリレポートには、選択した任意のワークスペース、ウィンドウまたはビジュアライゼーションを含めることができます。

* サマリレポートは、レポートセットの最上位フォルダ内の唯一のレポートである必要があります。 その他のすべてのレポートは、サブフォルダに配置する必要があります。 他のレポートを最上位フォルダに配置した場合、ポータルでは表示できません。

## ユーザーインターフェイスのタブへの出力フォルダのリンク {#section-3f6bc47d37ed448e871f4f685f46acee}

表示するタブを指定するには、各 [!DNL Report Portal] プロファイルのファイルを設定す [!DNL TopNavigation.xml] る必要があります。 このファイルは、特定のプロファイルのユーザーインターフェイスでタブとして表示されるレポートセットと、それらのタブの順序を決定します。 ファ [!DNL TopNavigation.xml] イルは\*PortalName*\PortalFiles\Core\TopNav\*profileName*フォルダーにあります。

**TopNavigation.xmlファイルを編集するには**

1. IISが実行されているマシン上で、メモ帳などのテキ [!DNL TopNavigation.xml] ストエディターでファイルを開きます。
1. 次の例のよう `<TopNav>` に、出力を表示するレポートセットの名前と順序が定義されるよ [!DNL Report Portal] うに要素のリストを編集します。

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
   >タブ [!DNL Admin] は、追加機能を提供する組み込みタブです。 ファイルに含めない場合、このタ [!DNL TopNavigation.xml] ブは表示されず、機能は使用できません。

1. \*PortalName*\PortalFiles\Core\TopNav\ folderディレクトリに、次のプロファイル用のフォルダを作成します。
1. 最初のプロフ [!DNL TopNavigation.xml] ァイルフォルダーからファイルをコピーし、新しいフォルダーに貼り付けます。
1. Edit the [!DNL TopNavigation.xml] as necessary, then save the file.
1. ポータルで使用可能なその他すべてのプロファイルに対して、手順3 ～ 5を繰り返します。

