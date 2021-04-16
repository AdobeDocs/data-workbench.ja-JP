---
description: 最初の手順は、ダッシュボードサーバーでIISの役割を有効にすることです。
title: IIS の有効化
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# IIS の有効化{#enabling-iis}

最初の手順は、ダッシュボードサーバーでIISの役割を有効にすることです。

1. **[!UICONTROL Administrative Tools]**&#x200B;の下で、**[!UICONTROL Server Manager]**&#x200B;を開きます。
1. **[!UICONTROL Server Manager]**&#x200B;ウィンドウの左側の部分にあるRolesメニュー項目を右クリックします。
1. **[!UICONTROL Add Roles]** を選択します。
1. **[!UICONTROL Web Server (IIS)]**&#x200B;を選択し、**[!UICONTROL Add Roles Wizard]**&#x200B;に進みます。 次の役割サービスが有効になっていることを確認します。

   | 一般的なHTTP機能 |
   |---|
   | 静的コンテンツ |
   | デフォルトドキュメント |
   | ディレクトリの参照 |
   | HTTPエラー |
   | HTTPリダイレクト |

   | アプリケーション開発 |
   |---|
   | ASP.NET |
   | .NET拡張機能 |
   | ISAPI拡張 |
   | ISAPIフィルター |

   | 正常性と診断 |
   |---|
   | HTTPログ |
   | ログツール |
   | リクエストモニター |
   | トレース |
   | カスタムログ |

   | セキュリティ |
   |---|
   | 基本認証 |
   | Windows認証 |
   | URL認証 |
   | リクエストのフィルタリング |
   | IPおよびドメインの制限 |

   | 管理ツール |
   |---|
   | IIS管理コンソール |
   | IIS管理スクリプトとツール |
   | 管理サービス |

1. ウィザードに従ってインストールを完了します。
