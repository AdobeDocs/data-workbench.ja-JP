---
description: DeviceAtlas JSON ファイルは、DeviceAtlas.dll と DeviceAtlas64.dll ファイルと共に .bundle ファイル（.tar.gz に名前が変更）で配布されます。
title: DeviceAtlas の配布
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 97%

---

# DeviceAtlas の配布{#deviceatlas-distribution}

DeviceAtlas JSON ファイルは、DeviceAtlas.dll と DeviceAtlas64.dll ファイルと共に .bundle ファイル（.tar.gz に名前が変更）で配布されます。

管理者が Insight サーバーをバージョン 6.0 にアップグレードした場合、DeviceAtlas.bundle ファイルはアップグレードパッケージと一緒に次の場所にあるソフトウェアおよびドキュメントプロファイル（softdocs プロファイル）に含まれています。

[!DNL Server Packages > v6.00 > Server_6.00.zip]

DeviceAtlas.bundleファイルは[!DNL Server\Lookups\DeviceAtlas]に抽出されます。

DeviceAtlas.bundle ファイルは、DPU と同期されるディレクトリに配置する必要があります。新しい DeviceAtlasComponent に対応する DeviceAtlas.cfg ファイルは、同期マスター上の「Components for Processing Servers」ディレクトリに配置する必要があります。DeviceAtlas.bundle ファイルが変更されると、そのすぐ次の DeviceAtlas ルックアップの呼び出しでは、更新された API または JSON ファイルに基づいた結果が返されます。

## Transformation.cfg ファイルの変更 {#section-394823348f5740028666e62e2bd42754}

DeviceAtlas 変換では、JSON ファイルのパスを指定する必要がなくなりました。transformation.cfg ファイルに定義されている以前のどの DeviceAtlasTransformation にも不明化された JSON ファイルを指す File パラメーターが含まれている必要はありません。

この例の Transformation.cfg ファイルでは、混乱を避けるために削除する必要がある File 引数が示されています（File 引数があっても無視されるので問題を引き起こすことはありませんが、混乱を招く可能性があります）。

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  
```

## DeviceAtlas.cfg ファイルの変更  {#section-10b43705a6c846fd9ec54ea6be249f88}

これは、DeviceAtlas.cfg ファイルに必要な [!DNL component] 引数の例です。

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

この DeviceAtlas.bundle ファイルは、プロファイル同期機能の観点からは設定ファイルのように扱われます。また、JSON データと DLL は、個々の変換レベルではなく、コンポーネントレベルで使用されます。

新しい DeviceAtlasComponent は、起動時に、.bundle ファイルを探し、JSON ファイルの不明化を解除してメモリに読み込み、ファイルを一時ディレクトリに展開して、実行しているプラットフォームに適した DLL をロードします。このコンポーネントは、バンドルファイルの変更を監視し、変更された場合に自動的に DLL と .cfg ファイルをリロードします。

## DeviceAtlas の実行  {#section-6ed37b39199d4ffd95d30b49a7ee9666}

適切に設定すると、変換に必要な時間が大きく異なります。変換を各セッションの訪問者ごとに 1 回だけ実行するように設定すると、DeviceAtlas の処理をスピードアップできます。

**Log Processing.cfg を使用してデプロイする場合**：

変換を 2 回実行します。

1. [!DNL mobile id]フィールドのみを検索し、
1. [!DNL mobile id] を無視する条件を作成して、残りのフィールドを検索します。

**Transformation.cfg を使用してデプロイする場合**：

上記の Log Processing の手順 1 に従ってデプロイするか、または条件の設定をサポートするクロス行を使用します。

* クロス行：前回のセッションキーを取得します。次に、現在のセッションキーがクロス行で見つけたキーと異なるかどうかを判別します。異なる場合は、DeviceAtlas 変換がセッションあたり 1 つのレコードに対して実行されます。
