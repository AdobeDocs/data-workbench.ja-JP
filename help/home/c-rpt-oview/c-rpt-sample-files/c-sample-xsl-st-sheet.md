---
description: XSLスタイルシートのコードサンプル。
title: XSL スタイルシートのサンプル
uuid: cac5c5ad-b0ec-45d8-901d-e39ce1f6d61a
exl-id: 688b0ce5-999b-4cfc-9228-146450132aee
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '20'
ht-degree: 40%

---

# XSL スタイルシートのサンプル{#sample-xsl-style-sheet}

XSLスタイルシートのコードサンプル。

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
<xsl:template match="/">
  <html>
  <body>
    <h2>Reports</h2>
    <xsl:for-each select="REPORTS/REPORT">
    <a>
    <xsl:attribute name="href">
    <xsl:value-of select="PATH"/>
    </xsl:attribute>
    <xsl:value-of select="NAME"/>
    </a><p/>
    </xsl:for-each>
  </body>
  </html>
</xsl:template>
</xsl:stylesheet>
```
