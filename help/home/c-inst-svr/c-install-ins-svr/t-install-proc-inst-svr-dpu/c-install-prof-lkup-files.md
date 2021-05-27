---
description: Adobeが特定のアプリケーション用に開発したプロファイルと参照ファイルは、データセットの分析を可能にする指標、ディメンション、ワークスペースを提供する内部プロファイルです。
title: プロファイルと参照ファイルのインストール
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 5%

---

# プロファイルと参照ファイルのインストール{#installing-profiles-and-lookup-files}

Adobeが特定のアプリケーション用に開発したプロファイルと参照ファイルは、データセットの分析を可能にする指標、ディメンション、ワークスペースを提供する内部プロファイルです。

Adobeが提供するその他すべての内部プロファイルと同様に、これらのプロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

Adobeは、アプリケーションのプロファイルと参照ファイルを[!DNL .zip]ファイルとして配布します。 各zipファイルの名前は、そのプロファイルに含まれるプロファイルと参照ファイルのアプリケーションに対して付けられます。 （例えば、[!DNL Site52.zip]にはSite v5.2のプロファイルファイルファイルが含まれます）。 [!DNL .zip]ファイルには、2つのフォルダー（[!DNL Lookups]と[!DNL Profiles]）が含まれます。

>[!NOTE]
>
>アプリケーションのプロファイルと参照ファイルを含むインストールファイルがまだない場合は、開始する前にAdobeFTPサイトからダウンロードしてください。

データセットプロファイルを処理し実行する[!DNL Insight Server]マシンに、プロファイルとその参照ファイルをインストールする必要があります。 [!DNL Insight Server]クラスターを実行している場合は、マスターサーバーにファイルをインストールする必要があります。 データセットプロファイルについて詳しくは、『データセット設定ガイド&#x200B;*』を参照してください。*

**プロファイルアプリケーション用のAdobeをインストールするには**

1. Adobeから提供された[!DNL .zip]ファイルから[!DNL Profiles]フォルダーを開きます。

1. [!DNL .zip]ファイル内の[!DNL Profiles]フォルダー内のすべてのフォルダーを、[!DNL Insight Server]インストールディレクトリ内の[!DNL Profiles]フォルダーにコピーします。 次の例に示すように、 [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]>*&#x200B;フォルダーを[!DNL Insight Server]に配置します。 実際のプロファイル名は異なる場合があります。

   ![](assets/win_installprofiles.png)

1.  [!DNL Profiles\]*&lt; [!DNL dataset profile name]*&#x200B;フォルダー（[!DNL Insight Server]をインストールしたディレクトリ内）に移動し、このディレクトリ内の[!DNL profile.cfg]ファイルを探します。

   >[!NOTE]
   >
   >初めてプロファイルをインストールする場合は、提供されたサンプルプロファイルをデータセットプロファイルとして使用できます。 [!DNL Insight Server]インストールディレクトリの[!DNL Profiles\Sample]フォルダー内に、Sampleプロファイルの[!DNL profile.cfg]ファイル（[!DNL profile.cfg.offline]などの名前が付いている場合もあります）があります。

1. メモ帳などのテキストエディターを使用して[!DNL profile.cfg]ファイルを開き、次の操作を行います。

   1. 内部プロファイルのエントリをDirectoriesベクトルに追加します。 プロファイル名は、[!DNL Insight Server]マシンの[!DNL Profiles]フォルダーにコピーしたディレクトリの名前に対応します。

   1. 必要に応じてディレクトリ数を更新します。
   1. 次に示すように、このファイルのCommon Name行にサーバーの共通名を追加します。

      ```
      Profile = profileInfo: 
      Directories = vector: n+1 items
        0 = string: Base\\
        1 = string: internal profile name 1\\
        2 = string: internal profile name 2\\
      . . .
        n = string: internal profile name n\\
      Processing Servers = vector: 1 items
        0 = ProfileServerInfo: 
          Common Name = string: serverCommonName
          Server = string: 
      ```

      >[!NOTE]
      >
      >[!DNL profile.cfg]ファイルの共通名に指定する&#x200B;*serverCommonName*&#x200B;は、データセットプロファイルを処理および実行する[!DNL Insight Server]マシンのサーバー共通名に対応します。 [!DNL profile.cfg]を更新して[!DNL Insight Server]クラスターでデータセットプロファイルを実行する手順については、[Insightサーバークラスター](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)を参照してください。

1. ファイルを保存します。ファイルの名前が異なる場合は、必ず[!DNL profile.cfg]として保存してください。

**Adobe・アプリケーションの参照ファイルをインストールするには**

1. Adobeから提供された[!DNL .zip]ファイルから[!DNL Lookups]フォルダーを開きます。

1. [!DNL .zip]ファイル内の[!DNL Lookups]フォルダー内のすべてのフォルダーを、[!DNL Insight Server]インストールディレクトリ内の[!DNL Lookups]フォルダーにコピーします。 次の例に示すように、 [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]>*&#x200B;フォルダーを[!DNL Insight Server]に配置します。 実際のプロファイル名は異なる場合があります。

   ![](assets/win_installLookups.png)
