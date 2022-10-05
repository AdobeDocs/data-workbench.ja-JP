---
description: Report Portal を通じて適切に表示されるレポートを生成するには、レポートセットを特定の方法で設定する必要があります。
title: Report Portal ユーザーインターフェイスのカスタマイズ
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Report Portal ユーザーインターフェイスのカスタマイズ{#customize-the-report-portal-user-interface}

{{eol}}

Report Portal を通じて適切に表示されるレポートを生成するには、レポートセットを特定の方法で設定する必要があります。

のユーザーインターフェイス [!DNL Report Portal] は、出力ディレクトリに表示され、 [!DNL profiles.xml] ファイルに加えて、組み込みの [!DNL Admin] タブに追加する必要があります。 [!DNL TopNavigation.xml] 表示するファイル。 組み込みの [!DNL Admin] タブ、「 [ユーザー内のタブに出力フォルダーをリンク中…](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [レポートセットと Report Portal の互換性を確保しています…](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [ユーザー内のタブに出力フォルダーをリンク中…](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## レポートセットと Report Portal の互換性の確保 {#section-2b141e5d198a4bbea455699126c24706}

レポートセットは、次の予定ジョブを定義します： [!DNL Report]. 次の 2 つの項目で構成されます。

* 必要なワークスペースのコレクションを定義するフォルダー [!DNL Report] をレポートとして生成する場合。
* 設定ファイル ( [!DNL Report.cfg]) をクリックします。

特に [!DNL Report.cfg] ファイルの指示 [!DNL Report] レポートを生成するタイミングと出力ファイルの保存場所。 レポートセットは、Data Workbench サーバー上の Reports フォルダーに存在します。 プロファイルには、任意の数のレポートセットを表示できます。

との互換性を確保するには [!DNL Report Portal]を使用する場合、レポートセットは次の要件を満たしている必要があります。

* レポートセットの出力ディレクトリには、設定済みの [!DNL profiles.xml] ファイル。
* 各レポートセットには、「*ReportSetName* 概要」を参照してください。 *ReportSetName* はレポートセットの名前に一致します。 例えば、次のような場合です。 [!DNL Profile Manager] には、「ホーム」と「トラフィック」の 2 つのレポートセットが表示されます。 なお、各レポートセットでは、サマリレポート ( [!DNL Home Summary.vw] および [!DNL Traffic Summary.vw]、それぞれ )。

![](assets/rptPort_scrn_RptSets.png)

In [!DNL Report Portal]の場合、サマリレポートはレポートセットの「 」タブに表示されます。 サマリレポートには、選択した任意のワークスペース、ウィンドウ、ビジュアライゼーションを含めることができます。

* レポートセットの最上位フォルダにあるレポートは、サマリレポートのみにする必要があります。 その他のレポートはすべて、サブフォルダーに配置する必要があります。 他のレポートを最上位フォルダーに配置した場合、ポータルでは表示できません。

## ユーザインターフェイスのタブへの出力フォルダのリンク {#section-3f6bc47d37ed448e871f4f685f46acee}

必要なタブを指定するには [!DNL Report Portal] 表示するには、 [!DNL TopNavigation.xml] ファイルを作成します。 このファイルでは、特定のプロファイルのユーザーインターフェイスでタブとして表示されるレポートセットと、それらのタブの順序を決定します。 この [!DNL TopNavigation.xml] ファイルは\*PortalName*\PortalFiles\Core\TopNav\*profileName*フォルダー内にあります。

**TopNavigation.xml ファイルを編集するには**

1. IIS が実行されているマシンで、 [!DNL TopNavigation.xml] ファイルをメモ帳などのテキストエディターで作成します。
1. リストを編集 `<TopNav>` 要素を使用して、出力するレポートセットの名前と順序を定義します。 [!DNL Report Portal] を表示するには、次の例のようにします。

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
   >この [!DNL Admin] タブは追加機能を提供する組み込みのタブです。 この変数を [!DNL TopNavigation.xml] ファイルの場合、このタブは表示されず、機能は使用できません。

1. \*PortalName*\PortalFiles\Core\TopNav\ folderディレクトリに、次のプロファイル用のフォルダーを作成します。
1. を [!DNL TopNavigation.xml] ファイルを最初のプロファイルフォルダーから作成し、新しいフォルダーに貼り付けます。
1. を編集します。 [!DNL TopNavigation.xml] 必要に応じて、ファイルを保存します。
1. ポータルで使用可能なその他すべてのプロファイルに対して、手順 3 ～ 5 を繰り返します。
