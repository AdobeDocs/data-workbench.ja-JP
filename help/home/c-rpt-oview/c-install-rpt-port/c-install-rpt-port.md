---
description: レポートポータルを使用するには、IISに一連のアプリケーションサーバーページ(ASP)をインストールし、設定する必要があります。
solution: Analytics
title: レポートポータルのインストール
topic: Data workbench
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# レポートポータルのインストール{#installing-the-report-portal}

レポートポータルを使用するには、IISに一連のアプリケーションサーバーページ(ASP)をインストールし、設定する必要があります。

**始める前に**

この章の手順では、のインストールと設定方法について説明しま [!DNL Report Portal]す。 これらの手順を実行するには、次の手順を実行する必要があります。

* Microsoft IISをインストールし、バージョンを確認する。
* レポートが表示されるレポートセットの名前を把握しま [!DNL Report Portal]す。
* これらのレポートセットの出力を保存す [!DNL Report Server] るディレクトリの場所を把握します。 IISアプリケーションサーバーがこのディレクトリにアクセスできることを確認します。

>[!NOTE]
>
>* を使用して表示するには、レ [!DNL Report Portal]ポートは特定の命名規則に従う必要があります。 また、レポートの保存先のディレクトリは、所定の構造に従う必要があります。 これらの要件の詳細については、「レポートセッ [トがレポートポータルと互換性があることを確認する」を参照してください。](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* レポートポータルのパスワードがAES-256ビットに準拠するようになりました。 Report Portal 2.0にアップグレードする場合は、users.mdbデータベースの「パスワードのフィールドサイズ」フィールドを50から150 **に増やします** 。 更新された暗号化でパスワードを受け取るには、フィールドサイズを増やす必要があります。
>* Report Portal 2.0にアップグレードする場合は、users.mdbデータベースの **Password** （パスワード）フィールドのフィールドサイズを50から150に増やします。 更新された暗号化でパスワードを受け取るには、フィールドサイズを増やす必要があります。
>* Report Portal には、ソルティングをサポートしている、より強力なハッシュアルゴリズムが導入されました。If you are upgrading to **Report Portal 2.1**, add a new Text field, *PasswordSalt* with field size of 20 characters in [!DNL users.mdb]database. このフィールドは、パスワードソルトを保存するのに必要です。
>



