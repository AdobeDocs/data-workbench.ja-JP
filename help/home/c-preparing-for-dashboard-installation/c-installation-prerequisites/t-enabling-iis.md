---
description: 最初の手順は、ダッシュボードサーバーでIISの役割を有効にすることです。
solution: Analytics
title: IISを有効にする
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# IISを有効にする{#enabling-iis}

最初の手順は、ダッシュボードサーバーでIISの役割を有効にすることです。

1. で、 **[!UICONTROL Administrative Tools]**&#x200B;を開きます **[!UICONTROL Server Manager]**。
1. ウィンドウの左側の部分にある役割メニュー項目を右クリックし **[!UICONTROL Server Manager]** ます。
1. Select **[!UICONTROL Add Roles]**.
1. を選択 **[!UICONTROL Web Server (IIS)]** し、を続行します **[!UICONTROL Add Roles Wizard]**。 次の役割サービスが有効になっていることを確認します。

   | 一般的なHTTP機能 |
   |---|
   | 静的コンテンツ |
   | デフォルトのドキュメント |
   | ディレクトリの参照 |
   | HTTPエラー |
   | HTTPリダイレクト |

   | アプリケーション開発 |
   |---|
   | ASP.NET |
   | .NET拡張機能 |
   | ISAPI拡張 |
   | ISAPIフィルタ |

   | 正常性と診断 |
   |---|
   | HTTPログ |
   | ログツール |
   | 要求モニタ |
   | トレース |
   | カスタムログ |

   | セキュリティ |
   |---|
   | 基本認証 |
   | Windows認証 |
   | URL認証 |
   | リクエストのフィルタ |
   | IPとドメインの制限 |

   | 管理ツール |
   |---|
   | IIS管理コンソール |
   | IIS管理スクリプトとツール |
   | 管理サービス |

1. ウィザードに従ってインストールを完了します。
