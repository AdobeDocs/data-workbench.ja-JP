---
description: Report Portalを使用するには、IISに一連のアプリケーションサーバーページ(ASP)をインストールして設定する必要があります。
title: Report Portal のインストール
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 11%

---

# Report Portal のインストール{#installing-the-report-portal}

Report Portalを使用するには、IISに一連のアプリケーションサーバーページ(ASP)をインストールして設定する必要があります。

**始める前に**

この章の手順では、[!DNL Report Portal]のインストールと設定の方法について説明します。 これらの手順を完了するには、次の操作を行う必要があります。

* Microsoft IISがインストールされ、バージョンがわかっている。
* [!DNL Report Portal]によってレポートが表示されるレポートセットの名前を確認します。
* [!DNL Report Server]がこれらのレポートセットの出力を保存するディレクトリの場所を把握します。 IISアプリケーションサーバーがこのディレクトリにアクセスできることを確認します。

>[!NOTE]
>
>* [!DNL Report Portal]を使用して表示するには、レポートは特定の命名規則に従う必要があります。 また、レポートの保存先ディレクトリは、所定の構造に従う必要があります。 これらの要件の説明については、[レポートセットとReport Portalの互換性の確保を参照してください。](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* Report PortalのパスワードがAES-256ビットに準拠するようになりました。 Report Portal 2.0にアップグレードする場合、**users.mdb**&#x200B;データベースの「パスワードのフィールドサイズ」フィールドを50から150に増やします。 更新された暗号化を使用してパスワードを受け入れるには、フィールドサイズを増やす必要があります。
>* Report Portal 2.0にアップグレードする場合、users.mdbデータベースの&#x200B;**Password**&#x200B;フィールドのフィールドサイズを50から150に増やします。 更新された暗号化を使用してパスワードを受け入れるには、フィールドサイズを増やす必要があります。
>* Report Portal には、ソルティングをサポートしている、より強力なハッシュアルゴリズムが導入されました。**Report Portal 2.1**&#x200B;にアップグレードする場合は、[!DNL users.mdb]データベースに、フィールドサイズが20文字の新しいテキストフィールド&#x200B;*PasswordSalt*&#x200B;を追加します。 このフィールドは、パスワードソルトを保存するのに必要です。

>


