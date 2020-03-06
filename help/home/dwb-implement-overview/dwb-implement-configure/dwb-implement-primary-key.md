---
description: この節では、Data Workbenchデータセットの主キー（追跡ID）を作成して、スキーマの設計と実装を行う方法について説明します。
title: データ処理 — 主キーの作成
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データ処理 — 主キーの作成{#data-processing-building-primary-key}

この節では、Data Workbenchデータセットの主キー（追跡ID）を作成して、スキーマの設計と実装を行う方法について説明します。

## 追跡IDについて {#section-24683031044a4af49988655ccb9a45fd}

（デコーダーを使用して）DWBでデータを読み取ってデコードした後、最初の手順は追跡IDとタイムスタンプを定義することです。 追跡IDは、顧客レコードを一意に識別する識別子です。 電子メールID、ソーシャルセキュリティ番号、cookie IDなど、フィード内の任意のフィールドを指定できます。 追跡IDとして使用されるフィールドは、検出セッション中にクライアントによって決定されます。 追跡IDとタイムスタンプは必須のフィールドで、各レコードに対して定義する必要があります。

通常、オンラインデータの場合、Cookie ID( *x-visid_high* と* x-visid_low*の組み合わせ)が一意の顧客識別のデフォルトのメカニズムとして使用されますが、これはクライアントの要件に応じて変更できます。 リクエスト（またはイベント）が発生する日時は、 *x-timestampです*。 DWB内のすべてのレコードは、追跡ID別にグループ化され *、タイムスタンプ* で並べ替えられます。 The Required Field [!DNL Definitions.cfg] file is a Log Processing Dataset Include file that defines the required fields : *x-trackingid* and *x-timestamp*.

注意：*x-trackingid *in DWBは組み込みフィールドで、この名前は他のフィールドには使用できません。

**例1**:Cookie *IDを使用した* x-trackingid（オンラインデータのみを使用する場合）の作成

Cookie IDを使用して*x-trackingid *をDWBに作成するには、Hash関数を使用して *x-trackingid* ( [!DNL foundation.cfg] x-trackingid [!DNL foundation.cfg][!DNL Dataset > log processing] )をファイル内に作成します（ではトラッキングIDを定義するのがベストプラクティスですが、フォルダーの下の他の設定ファイルで定義できます）。

![](assets/dwb_impl_primary_key1.png)

**例2**:電子メ *ールIDを使用した* x-trackingidの作成（オンラインとオフラインの両方のデータが使用可能な場合）

オフラインとオンラインの両方のデータが使用可能であると仮定し（この例）、電子メールIDは両方のデータソースで使用できます。 電子メールIDは顧客を一意に識別するので、 *x-trackingidの作成に使用されます*。

次に示すように、Hash関数を使用し *てtrackingId* を作成します。

![](assets/dwb_impl_primary_key2.png)

