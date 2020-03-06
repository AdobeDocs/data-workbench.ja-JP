---
description: アドビが特定のアプリケーション用に開発したプロファイルと参照ファイルは、データセットの分析を可能にする指標、ディメンションおよびワークスペースを提供する内部プロファイルです。
solution: Insight
title: プロファイルと参照ファイルのインストール
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# プロファイルと参照ファイルのインストール{#installing-profiles-and-lookup-files}

アドビが特定のアプリケーション用に開発したプロファイルと参照ファイルは、データセットの分析を可能にする指標、ディメンションおよびワークスペースを提供する内部プロファイルです。

アドビが提供する他のすべての内部プロファイルと同様に、これらのプロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

アドビでは、アプリケーションのプロファイルと参照ファイルをファイルとして配布 [!DNL .zip] しています。 各zipファイルには、そのファイルに含まれるプロファイルと参照ファイルを持つアプリケーションの名前が付けられます。 (例えば、にはSite v5.2 [!DNL Site52.zip] のプロファイルファイルが含まれています)。このファ [!DNL .zip] イルには2つのフォルダー(お [!DNL Lookups] よび [!DNL Profiles])が含まれます。

>[!NOTE]
>
>アプリケーションのプロファイルと参照ファイルを含むインストールファイルがまだない場合は、開始する前にアドビのFTPサイトからダウンロードしてください。

データセットプロファイルを処理し実行するコンピューターに、プロファ [!DNL Insight Server] イルとその参照ファイルをインストールする必要があります。 クラスターを実行している場 [!DNL Insight Server] 合は、マスターサーバーにファイルをインストールする必要があります。 For information about dataset profiles, see the *Dataset Configuration Guide*.

**アドビアプリケーション用のプロファイルをインストールするには**

1. アドビから [!DNL Profiles] 提供されたファ [!DNL .zip] イルからフォルダーを開きます。

1. ファイル内のフォルダー内のすべてのフ [!DNL Profiles] ォルダーを、イ [!DNL .zip] ンストールディレクトリ [!DNL Profiles] 内のフォルダーにコ [!DNL Insight Server] ピーします。 [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>フ*[!DNL Insight Server] ォルダーを作成します。 実際のプロファイル名は異なる場合があります。

   ![](assets/win_installprofiles.png)

1. インストールしたディレクトリ内の[!DNL Profiles\]*&lt;[!DNL dataset profile name]>* フォルダーに移動し、このディレク [!DNL Insight Server] トリ [!DNL profile.cfg] 内のファイルを探します。

   >[!NOTE]
   >
   >初めてプロファイルをインストールする場合は、提供されたSampleプロファイルをデータセットプロファイルとして使用できます。 Sampleプロファイルのフ [!DNL profile.cfg] ァイル（名前は、など）は、インスト [!DNL profile.cfg.offline]ールディレクトリ内のフォルダー内にあ [!DNL Profiles\Sample] ります(この名前は [!DNL Insight Server] 次のようになります)。

1. メモ帳など [!DNL profile.cfg] のテキストエディターを使用してファイルを開き、次の操作を行います。

   1. Directoriesベクトルに内部プロファイルのエントリを追加します。 プロファイル名は、コンピューター上のフォルダーにコピーしたディレク [!DNL Profiles] トリの名前に対応し [!DNL Insight Server] ます。

   1. 必要に応じて、ディレクトリの数を更新します。
   1. 次に示すように、このファイルの「共通名」行にサーバの共通名を追加します。

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
      >ファ *イル内の共通名に* 指定するserverCommonNameは、データセットプロファイルを処理し実行するマシンのサー [!DNL profile.cfg][!DNL Insight Server] バー共通名に対応しています。 データセットプロファイルをク [!DNL profile.cfg] ラスター上で実行するように更新する手順につい [!DNL Insight Server] ては、「 [Insight Server Clusters](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)」を参照してください。

1. ファイルを保存します。ファイル名が変わったかのように、必ずフ [!DNL profile.cfg] ァイルを保存してください。

**アドビアプリケーションの参照ファイルをインストールするには**

1. アドビから [!DNL Lookups] 提供されたファ [!DNL .zip] イルからフォルダーを開きます。

1. ファイル内のフォルダー内のすべてのフ [!DNL Lookups] ォルダーを、イ [!DNL .zip] ンストールディレクトリ [!DNL Lookups] 内のフォルダーにコ [!DNL Insight Server] ピーします。 [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>フ*[!DNL Insight Server] ォルダーを作成します。 実際のプロファイル名は異なる場合があります。

   ![](assets/win_installLookups.png)

