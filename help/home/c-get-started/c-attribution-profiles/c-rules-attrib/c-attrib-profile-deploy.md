---
description: アトリビューションプロファイルは、継承された、すぐに利用できるプロファイルです。Adobe SC プロファイおよび Analytics（SC／Insight）のデータフィードと組み合わせて、このプロファイルをデプロイすると、複数のデジタルチャネルに新しいアトリビューションモデルを迅速に公開できます。
title: アトリビューションプロファイルのデプロイ
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
exl-id: 287e1710-7e74-4904-b258-7b811ad484b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 68%

---

# アトリビューションプロファイルのデプロイ{#deploying-the-attribution-profile}

{{eol}}

アトリビューションプロファイルは、継承された、すぐに利用できるプロファイルです。Adobe SC プロファイおよび Analytics（SC／Insight）のデータフィードと組み合わせて、このプロファイルをデプロイすると、複数のデジタルチャネルに新しいアトリビューションモデルを迅速に公開できます。

プライマリサーバーにアトリビューションプロファイルを保存した後、[!DNL Profile] ディレクトリ内の現在のプロファイルにそのプロファイルを統合するために必要な手順が 2 つあります。（1）Profile.cfg ファイルを設定し、（2）必須フィールドを宣言します。

## Profile.cfg ファイルの設定 {#section-7531cb865d994207baba692a6fc842d7}

すべてのプロファイルと同様に、アトリビューションプロファイルは [!DNL profile.cfg] ファイルに追加する必要があります。アトリビューションプロファイルは Adobe SC プロファイルに依存するので、設定ファイルではアトリビューションプロファイルより前に Adobe SC プロファイルをリストする必要があります。

>[!NOTE]
>
>これらの手順では、データセットを再変換する必要があります。

1. カスタムプロファイルフォルダー内の [!DNL profile.cfg] ファイルを開きます（で開く） [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. 設定ファイルにアトリビューションプロファイルがリストされていない場合は、リストに追加します。 ![](assets/new_profile_cfg.png)

1. 次を確認します。 **[!UICONTROL Attribution]** 文字列が **[!UICONTROL Adobe SC]** プロファイル文字列。

1. 更新した [!DNL profile.cfg] ファイルを保存し、プロファイルマネージャーからサーバーに保存します。

## 必須フィールドの宣言 {#section-23d4273af0c34b7a85ae3430e2c9350e}

アトリビューションプロファイルは、事前に定義されたフィールドを受け取り、一連の変換を行って、拡張されたディメンションを通じて新しい便利な方法でそれらのフィールドを公開します。最も直近の値を提供するため、アトリビューションプロファイルは Adobe SC プロファイルで使用可能なフィールドに依存します。

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> デフォルトの変数 </th> 
   <th colname="col2" class="entry"> フィールド名とデコーダー位置（Adobe SC） </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> キャンペーン </td> 
   <td colname="col2"> <p>x-campaign、#199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> マーケティングチャネル </td> 
   <td colname="col2"> <p>x-va_closer_detail、#162 </p> <p>x-va_instance_event、#163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 注文イベント </td> 
   <td colname="col2"> <p>x-order、#206 </p> <p>x-purchaseid、#200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 売上高 </td> 
   <td colname="col2"> x-revenue、#205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 単位 </td> 
   <td colname="col2"> <p>x-units、#204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Adobe Analytics のデータソースを定義するために使用されるデコーダーグループ内でこれらのフィールドが宣言されていることを確認します。デフォルトのデコーダーグループは、 [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. これらのフィールドが **[!UICONTROL Fields]** セクション [!DNL SC Fields.cfg] ファイル。 このファイルは、以下の場所にあります。 [!DNL Dataset\Log Processing\SC Fields.cfg].

## アトリビューションの追加とトラブルシューティング {#section-168133a8a1a54e1281e532033878d246}

アトリビューションプロファイルに設定ファイルが追加されました。 [!DNL 0a_Marketing Channels.cfg]: [!DNL x-va_closer_detail] ～という新しい分野に入る [!DNL x-marketing-channel]、 [!DNL x-va_instance_event] フィールドは「1」に一致します。 両方 [!DNL x-va_closer_detail] および [!DNL x-va_instant_event] はデフォルトでデコードされ、バージョン 6.2 に更新した場合に使用可能なインストール済みパッケージでのデコードから渡されます。

「[!DNL x-marketing-channel]」フィールドは、マーケティングチャネルというシンプルディメンションで使用されます。

>[!IMPORTANT]
>
>現在使用中の未使用のフィールドを削除してプロファイルを変更した場合は、 [!DNL x-va_closer_detail] および [!DNL x-va_instance_event] フィールドはデコードされ、使用するために経由されます。

フィールドが見つからない場合は、詳細な状態を示す次のメッセージが表示されます。

```
<b>x-va_closer_detail</b> is not available
```

 または

```
<b>x-va_instance_event</b> is not available
```
