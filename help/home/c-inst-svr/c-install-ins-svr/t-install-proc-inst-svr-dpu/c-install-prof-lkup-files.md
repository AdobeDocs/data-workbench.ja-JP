---
description: Adobeが特定のアプリケーション用に開発したプロファイルと参照ファイルは、データセットの分析を可能にする指標、ディメンション、ワークスペースを提供する内部プロファイルです。
title: プロファイルと参照ファイルのインストール
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 5%

---

# プロファイルと参照ファイルのインストール{#installing-profiles-and-lookup-files}

{{eol}}

Adobeが特定のアプリケーション用に開発したプロファイルと参照ファイルは、データセットの分析を可能にする指標、ディメンション、ワークスペースを提供する内部プロファイルです。

Adobeが提供するその他すべての内部プロファイルと同様に、これらのプロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

Adobeは、アプリケーションのプロファイルと参照ファイルを [!DNL .zip] ファイル。 各 zip ファイルの名前は、そのファイルに含まれるアプリケーションのプロファイルと参照ファイルに対して付けられます。 ( 例： [!DNL Site52.zip] には、Site v5.2 用のプロファイルファイルファイルが含まれています )。 この [!DNL .zip] ファイルに 2 つのフォルダ ( [!DNL Lookups] および [!DNL Profiles]) をクリックします。

>[!NOTE]
>
>アプリケーションのプロファイルと参照ファイルを含むインストールファイルがまだない場合は、まず、Adobeの FTP サイトからそれらをダウンロードしてから、

プロファイルとその参照ファイルは、 [!DNL Insight Server] データセットプロファイルを処理して実行するマシン。 を実行している場合、 [!DNL Insight Server] クラスターを使用する場合は、マスターサーバーにファイルをインストールする必要があります。 データセットプロファイルについて詳しくは、 *データセット設定ガイド*.

**アプリケーションアプリケーション用のプロファイルをAdobeするには**

1. を開きます。 [!DNL Profiles] フォルダーを [!DNL .zip] ファイルがAdobeで提供された。

1. 内のすべてのフォルダーをコピーします。 [!DNL Profiles] フォルダーを [!DNL .zip] ファイルを [!DNL Profiles] の [!DNL Insight Server] インストールディレクトリ。 [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]>* フォルダー [!DNL Insight Server] を次の例に示します。 実際のプロファイル名は異なる場合があります。

   ![](assets/win_installprofiles.png)

1. 次に移動： [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* をインストールしたディレクトリ内のフォルダー [!DNL Insight Server] と [!DNL profile.cfg] ファイルを格納します。

   >[!NOTE]
   >
   >初めてプロファイルをインストールする場合は、提供されたサンプルプロファイルをデータセットプロファイルとして使用できます。 次の [!DNL profile.cfg] ファイル ( [!DNL profile.cfg.offline]) は、 [!DNL Profiles\Sample] の [!DNL Insight Server] インストールディレクトリ。

1. を開きます。 [!DNL profile.cfg] ファイルを作成し、メモ帳などのテキストエディターを使用して次の操作を行います。

   1. Directories ベクトルに内部プロファイルのエントリを追加します。 プロファイル名は、 [!DNL Profiles] フォルダーを [!DNL Insight Server] マシン。

   1. 必要に応じてディレクトリの数を更新します。
   1. 次に示すように、このファイルの「共通名」行にサーバーの共通名を追加します。

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
      >この *serverCommonName* を [!DNL profile.cfg] file は、 [!DNL Insight Server] データセットプロファイルを処理および実行するマシン。 更新手順 [!DNL profile.cfg] データセットプロファイルを [!DNL Insight Server] クラスター、詳しくは、 [Insight サーバークラスター](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. ファイルを保存します。必ずファイルを [!DNL profile.cfg] 別の名前が付けられている場合は、

**Adobe・アプリケーションの参照ファイルをインストールするには**

1. を開きます。 [!DNL Lookups] フォルダーを [!DNL .zip] ファイルがAdobeで提供された。

1. 内のすべてのフォルダーをコピーします。 [!DNL Lookups] フォルダーを [!DNL .zip] ファイルを [!DNL Lookups] の [!DNL Insight Server] インストールディレクトリ。 [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]>* フォルダー [!DNL Insight Server] を次の例に示します。 実際のプロファイル名は異なる場合があります。

   ![](assets/win_installLookups.png)
