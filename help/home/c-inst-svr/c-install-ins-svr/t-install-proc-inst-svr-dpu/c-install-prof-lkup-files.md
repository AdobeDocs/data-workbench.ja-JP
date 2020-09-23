---
description: Adobeが特定のアプリケーション用に開発したプロファイルとルックアップファイルは、データセットの分析を可能にする指標、ディメンション、ワークスペースを提供する内部プロファイルです。
solution: Analytics
title: プロファイルと参照ファイルのインストール
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 5%

---


# プロファイルと参照ファイルのインストール{#installing-profiles-and-lookup-files}

Adobeが特定のアプリケーション用に開発したプロファイルとルックアップファイルは、データセットの分析を可能にする指標、ディメンション、ワークスペースを提供する内部プロファイルです。

Adobeが提供する他のすべての内部プロファイルと同様に、これらのプロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

Adobeは、アプリケーションのプロファイルファイルと参照ファイルを [!DNL .zip] ファイルとして配布します。 各zipファイルには、そのファイルに含まれるプロファイルファイルと参照ファイルを持つアプリケーションの名前が付けられます。 (例えば、Site v5.2のプロファイルファイル [!DNL Site52.zip] が含まれている場合)。 この [!DNL .zip] ファイルには2つのフォルダー( [!DNL Lookups] および [!DNL Profiles])が含まれています。

>[!NOTE]
>
>アプリケーションのプロファイルと参照ファイルが含まれているインストールファイルがまだない場合は、まずAdobeのFTPサイトからダウンロードしてください。

データセットプロファイルを処理する [!DNL Insight Server] マシンにプロファイルとそのルックアップファイルをインストールし、実行する必要があります。 クラスターを実行している場合は、マスターサーバーにファイルをインストールする必要があり [!DNL Insight Server] ます。 For information about dataset profiles, see the *Dataset Configuration Guide*.

**Adobeアプリケーション用のプロファイルをインストールするには**

1. Adobeから提供された [!DNL Profiles] フ [!DNL .zip] ァイルからフォルダを開きます。

1. ファイル内のフォルダー内のすべてのフォルダーを、インストー [!DNL Profiles] ルディレクトリ内 [!DNL .zip] のフォルダーにコピーし [!DNL Profiles][!DNL Insight Server] ます。 次の例に示すように&#x200B; [!DNL ...\Profiles\]*、[!DNL internal profile name]&lt;* > [!DNL Insight Server] フォルダーを使用して終了します。 実際のプロファイル名は異なる場合があります。

   ![](assets/win_installprofiles.png)

1. インストールしたディレクトリ内の&#x200B; [!DNL Profiles\]*&lt;[!DNL dataset profile name]>* フォルダーに移動し [!DNL Insight Server] 、このディレクトリ内の [!DNL profile.cfg] ファイルを探します。

   >[!NOTE]
   >
   >初めてプロファイルをインストールする場合は、付属のサンプルプロファイルをデータセットプロファイルとして使用できます。 Sampleプロファイルの [!DNL profile.cfg] ファイル(名前は、など [!DNL profile.cfg.offline])は、インストールディレクトリ内の [!DNL Profiles\Sample][!DNL Insight Server] フォルダにあります。

1. メモ帳などのテキストエディターを使用して [!DNL profile.cfg] ファイルを開き、次の操作を行います。

   1. Directoriesベクトル内の追加内部プロファイルのエントリ。 プロファイル名は、コンピューター上のフォルダーにコピーしたディレクトリの名前に対応 [!DNL Profiles] し [!DNL Insight Server] ます。

   1. 必要に応じてディレクトリ数を更新します。
   1. 次追加に示すように、このファイルの「共通名」行に対するサーバーの共通名。

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
      >フ *ァイルの共通名に指定するserverCommonName* は、データセットプロファイルを処理して実行する [!DNL profile.cfg][!DNL Insight Server] マシンのサーバー共通名に対応しています。 データセットプロファイルがクラスター上で実行さ [!DNL profile.cfg] れるように更新する手順については、「 [!DNL Insight Server] Insight Server Clusters [](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)」を参照してください。

1. ファイルを保存します。ファイル名が変わっているかのように、必ずファイル [!DNL profile.cfg] を保存してください。

**Adobeアプリケーションの参照ファイルをインストールするには**

1. Adobeから提供された [!DNL Lookups] フ [!DNL .zip] ァイルからフォルダを開きます。

1. ファイル内のフォルダー内のすべてのフォルダーを、インストー [!DNL Lookups] ルディレクトリ内 [!DNL .zip] のフォルダーにコピーし [!DNL Lookups][!DNL Insight Server] ます。 次の例に示すように&#x200B; [!DNL ...\Lookups\]*、[!DNL internal profile name]&lt;* > [!DNL Insight Server] フォルダーを使用して終了します。 実際のプロファイル名は異なる場合があります。

   ![](assets/win_installLookups.png)

