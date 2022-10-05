---
description: 最初の手順では、ダッシュボードサーバーで IIS の役割を有効にします。
title: IIS の有効化
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# IIS の有効化{#enabling-iis}

{{eol}}

最初の手順では、ダッシュボードサーバーで IIS の役割を有効にします。

1. の下 **[!UICONTROL Administrative Tools]**、 **[!UICONTROL Server Manager]**.
1. の左側の部分にある役割メニュー項目を右クリックします。 **[!UICONTROL Server Manager]** ウィンドウ
1. **[!UICONTROL Add Roles]** を選択します。
1. 選択 **[!UICONTROL Web Server (IIS)]** をクリックし、 **[!UICONTROL Add Roles Wizard]**. 次のロールサービスが有効になっていることを確認します。

   | 一般的な HTTP 機能 |
   |---|
   | 静的コンテンツ |
   | デフォルトのドキュメント |
   | ディレクトリ参照 |
   | HTTP エラー |
   | HTTP リダイレクト |

   | アプリケーション開発 |
   |---|
   | ASP.NET |
   | .NET 拡張機能 |
   | ISAPI 拡張 |
   | ISAPI フィルタ |

   | ヘルスと診断 |
   |---|
   | HTTP ログ |
   | ログツール |
   | リクエストモニター |
   | トレース |
   | カスタムログ |

   | セキュリティ |
   |---|
   | 基本認証 |
   | Windows 認証 |
   | URL 認証 |
   | リクエストのフィルター |
   | IP とドメインの制限 |

   | 管理ツール |
   |---|
   | IIS 管理コンソール |
   | IIS 管理スクリプトおよびツール |
   | 管理サービス |

1. ウィザードに従ってインストールを完了します。
