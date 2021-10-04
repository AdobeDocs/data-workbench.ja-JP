---
description: Data Workbench6.3 のサーバーコンポーネントをアップグレードしています。
title: DWB サーバーの 6.2 から 6.3 へのアップグレード
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
exl-id: 5106d9a3-179a-49f1-915a-c03b36ed5257
source-git-commit: b21da6d12175fa8570b1b366049baa9c8e8ea862
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 56%

---

# DWB サーバーのアップグレード：6.2 から 6.3 へ{#dwb-server-upgrade-to}

Data Workbench6.3 のサーバーコンポーネントをアップグレードしています。

**サーバーのアップグレード**

[!DNL Base] パッケージで提供されるデフォルトのファイルよりも優先されるカスタマイズ済みのプロファイルがある場合は、これらのカスタマイズ済みのファイルを更新する必要があります。

* **Meta.cfg ファイルを更新します** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]ファイルシステムユニット（FSU サーバー）用に更新されたパスワードの暗号化を設定し、名前と値のペアの変換用のエントリを追加して、 [クエリー文字列のグループ化](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0)を利用します。

   1. FSU 上の [!DNL meta.cfg] ファイルを開きます。
   1. **[!UICONTROL Proxy Password]** のデータ型を、*ワークステーションの設定* セクションで、「 [!DNL string"] 」から「 [!DNL EncryptedString] 」に変更します。

      ```
        Proxy User Name = string:
        Proxy Password = EncryptedString:   (
        from Proxy Password = String)
        Use Address File = bool: true
      ```

   1. 新しい名前と値のペアの変換を有効にする新しいエントリ *BuildNameValuePair* と *ExtractNameValuePairs* を追加します。

      ワークスペースを開き、**管理者**／**プロファイルマネージャー**&#x200B;を右クリックします。

      **コンテキスト**&#x200B;の下で、**Base** 列の **meta.cfg** ファイルをクリックし、「**ローカル化**」をクリックします。User テーブル列で右クリックし、**開く**／**ワークステーションで**&#x200B;を選択します。

      ![](assets/meta_cfg.png)

      * 新しいウィンドウで、**metadata** をクリックし、acceptable children テンプレートを追加します。

         ![](assets/meta_cfg_child.png)

      * **transformation** を開き、新しいテンプレートを追加します。

         ![](assets/meta_cfg_template.png)

* **高速結合の強化のための更新**。Data Workbench での変換速度の向上を利用するために、次の設定ファイルに対してパラメーターの追加または値の変更を行います。

   * **Communications.cfg** (  [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:
          URI = string: /SourceListServer/
          Listing Interval = int: 10 (
      <new>)
      ```

   * **Disk Files.cfg** ( および [!DNL E:\Server\Components] にあ [!DNL E:\Server\Components for Processing Servers]る )

      ```
      Disk Cache Size (MB) = double: 1024
      <(from double: 256)>
      Disk Cache Read Limit (MB) = double: 768
      <(new)>
      ```

   * **Log Processing Mode.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

      ```
      <(changed)
      Batch Bytes = int: 268435456
      Cloud Bytes = int: 268435456
      Real Time FIFO Bytes = int: 268435456
      ```

      ```
      (
      <new>)
      Cache Bytes = int: 32000000
      Fast Input Decision Ratio = double: 200
      Fast Input FIFO Bytes = int: 268435456
      FIFO Hash Mask = int: 16383
      Fast Merge Buffer Bytes = int: 536870912
      Slow Merge Buffer Bytes = int: 268435456
      Fast Merge Fan In = int: 64
      Key Cache Size Logarithm = int: 21
      Max Seeks = int: 512
      Output Old Buffer Bytes = int: 536870912
      Overflow FIFO Bytes = int: 67108864
      Paused = bool: false
      ```
   >[!NOTE]
   >
   >高速結合の強化を利用するには、各 DPU に RAM が少なくとも 8 GB あることを確認してください。

* **Adobe Target と DWB の統合の更新**。新しい書き出しファイル [!DNL ExportIntegration.exe] は、Insight サーバー上の既存の [!DNL TnTSend.exe] ファイル (`E:\Server\Scripts\TnTSend.exe`) を置き換えます。 この新しいエクスポートファイルは、[Adobe Target](https://www.adobe.com/marketing/target.html) の統合と、新しいマスターマーケティングプロファイル（MMP）および [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html) との連携の両方に対応しています。

   Adobe Target のエクスポートのために、次のコマンドを更新する必要があります。

   `Command = string: TnTSend.exe`

    を   

   ```
   <filepath>
   Command = string: ExportIntegration.exe
   </filepath>
   ```

   >[!NOTE]
   >
   >これは、バージョン 6.3 より前に作成されたエクスポートにのみ影響します。

   また、古いエクスポートプロセスを使用する場合は、次を試すこともできます。

   * ワークステーションで新しい Target エクスポートを作成します。
   * [!DNL Server/Profiles/`<your profile>`/Export.] にある古い Test and Target エクスポートを変更します。

* **Adobe SC プロファイルの更新。** ファイルを変更す [!DNL Exclude Hit.cfg] るには、関連するファイルでフィールドを宣言する必要が [!DNL Decoding Instructions.cfg] あります。

   >[!NOTE]
   >
   >Adobeの SC プロファイルにカスタマイズされた [!DNL Decoding Instructions.cfg] ファイルが含まれている場合は、カスタマイズしたファイルに [!DNL DelimitedDecoder] パラメーターを含める必要があります。

   ```
   0 = DelimitedDecoder:
      Delimiter = string: \t
      Fields = vector: x items
      …
         5 = string:
   Changed to:
   
   5 = string: x-hit_source
   ```

   [!DNL DelimitedDecoder] フィールドを追加すると、機能の更新を利用し、これらの更新が原因で発生する可能性があるログ処理の問題を回避することができます。
