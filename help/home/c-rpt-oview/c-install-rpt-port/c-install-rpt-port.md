---
description: Report Portal を使用するには、IIS に一連のアプリケーションサーバーページ (ASP) をインストールして設定する必要があります。
title: Report Portal のインストール
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 11%

---

# Report Portal のインストール{#installing-the-report-portal}

{{eol}}

Report Portal を使用するには、IIS に一連のアプリケーションサーバーページ (ASP) をインストールして設定する必要があります。

**始める前に**

この章の手順では、をインストールして設定する方法について説明します [!DNL Report Portal]. これらの手順を完了するには、次の操作を行う必要があります。

* Microsoft IIS がインストールされ、そのバージョンがわかっている。
* レポートが表示されるレポートセットの名前を把握する [!DNL Report Portal].
* ディレクトリの場所を把握し、 [!DNL Report Server] これらのレポートセットの出力を保存します。 IIS アプリケーションサーバーがこのディレクトリにアクセスできることを確認します。

>[!NOTE]
>
>* 次を使用して表示する： [!DNL Report Portal]を使用する場合、レポートは特定の命名規則に従う必要があります。 また、レポートの保存先ディレクトリは、所定の構造に従う必要があります。 これらの要件について詳しくは、 [レポートセットと Report Portal の互換性を確保しています…](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
>
>* Report Portal のパスワードが AES-256 ビットに準拠するようになりました。 Report Portal 2.0 にアップグレードする場合、 **users.mdb** データベース。 更新された暗号化でパスワードを受け入れるには、フィールドサイズを増やす必要があります。
>* Report Portal 2.0 にアップグレードする場合は、 **パスワード** users.mdb データベースの 50 ～ 150 のフィールド。 更新された暗号化でパスワードを受け入れるには、フィールドサイズを増やす必要があります。
>* Report Portal には、ソルティングをサポートしている、より強力なハッシュアルゴリズムが導入されました。にアップグレードする場合は、 **Report Portal 2.1**、新しいテキストフィールドを追加します。 *PasswordSalt* フィールドサイズが 20 文字の [!DNL users.mdb]データベース。 このフィールドは、パスワードソルトを保存するのに必要です。
>

