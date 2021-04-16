---
description: テストを設定する前に、テストで使用する代替コンテンツを作成する必要があります。
solution: Analytics,Analytics
title: テストコンテンツの作成
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# テストコンテンツの作成{#creating-the-test-content}

テストを設定する前に、テストで使用する代替コンテンツを作成する必要があります。

コントロール母集団は元のURIに送信され、テストグループは新しい代替URIに送信されます。

混乱を避けるために、テストグループのファイル名を再利用しないでください。 例えば、[!DNL test2.asp]という名前のテストグループファイルを使用してテストを実行する場合、次のテストではテストファイルの名前に[!DNL test2.asp]を使用しないでください。

「デモの要請」グラフィカルリンクをホームページに移動する仮説は、訪問者コンバージョンに影響を与えます。この場合、新しい位置に「デモの要請」グラフィカルリンクを含む代替ホームページを作成します。 次の節では、特定の割合の訪問者に対してコントロール母集団URI [!DNL index.asp]をテストグループURI [!DNL index2.asp]に置き換える方法を説明します。
