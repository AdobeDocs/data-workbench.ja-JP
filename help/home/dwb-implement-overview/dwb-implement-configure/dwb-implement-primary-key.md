---
description: この節では、プライマリの設計と実装用のData Workbenchデータセットのスキーマキー（トラッキング ID）を作成する方法について説明します。
title: データ処理 - プライマリキーの作成
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
exl-id: 9937038f-d011-4946-8a5b-cc724b611ae5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# データ処理 - プライマリキーの作成{#data-processing-building-primary-key}

{{eol}}

この節では、プライマリの設計と実装用のData Workbenchデータセットのスキーマキー（トラッキング ID）を作成する方法について説明します。

## トラッキング ID について {#section-24683031044a4af49988655ccb9a45fd}

（デコーダーを使用して）DWB でデータを読み取り、デコードした後、最初の手順はトラッキング ID とタイムスタンプを定義することです。 トラッキング ID は、顧客レコードを一意に識別する識別子です。 電子メール ID、ソーシャルセキュリティ番号、Cookie ID など、フィード内の任意のフィールドを指定できます。 トラッキング ID として使用するフィールドは、検出セッション中にクライアントによって決定されます。 「トラッキング ID 」と「タイムスタンプ」は必須フィールドで、各レコードに対して定義する必要があります。

通常、オンラインデータの場合は Cookie ID( *x-visid_high* および* x-visid_low*) は、一意の顧客 ID のデフォルトのメカニズムとして使用されますが、クライアントの要件に従って変更できます。 リクエスト（またはイベント）が発生する日時は、 *x-timestamp*. DWB 内のすべてのレコードは、 *trackingid* タイムスタンプで並べ替えられました。 必須フィールド [!DNL Definitions.cfg] ファイルは、必須フィールドを定義するログ処理データセットインクルードファイルです。 *x-trackingid* および *x-timestamp*.

注意：DWB 内の*x-trackingid *は組み込みフィールドです。この名前は他のフィールドには使用しないでください。

**例 1**:作成中 *x-trackingid* cookie ID の使用（オンラインデータのみを使用する場合）

Cookie ID を使用して DWB で x-trackingid を作成するには、Hash 関数を使用して *x-trackingid* 内 [!DNL foundation.cfg] ファイル ( [!DNL foundation.cfg] ただし、以下の他の設定ファイルで定義できます。 [!DNL Dataset > log processing] フォルダー ) を次のように表示します。

![](assets/dwb_impl_primary_key1.png)

**例 2**:作成中 *x-trackingid* 電子メール ID の使用（オンラインとオフラインの両方のデータが利用可能な場合）

オフラインとオンラインの両方のデータが使用可能で（この例では）、電子メール ID が両方のデータソースで使用できるとします。 これは顧客を一意に識別する電子メール ID なので、 *x-trackingid*.

Hash 関数を使用して *trackingId* 例：

![](assets/dwb_impl_primary_key2.png)
