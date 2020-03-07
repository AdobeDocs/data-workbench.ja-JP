---
description: Mail XSLスタイルシートのコードサンプル。
solution: Analytics
title: メールXSLスタイルシートの例
topic: Data workbench
uuid: 846ddf22-e6da-4d37-ba50-d75f850b9a3f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# メールXSLスタイルシートの例{#sample-mail-xsl-style-sheet}

Mail XSLスタイルシートのコードサンプル。

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
<xsl:template match="/">
<html>
<body>
<h2>Reports</h2>
<xsl:for-each select="REPORTS/REPORT[@format!='xls']">
<img><xsl:attribute name="src">cid:<xsl:value-of select="PATH"/></xsl:attribute></img><p/>
</xsl:for-each>
</body>
</html>
</xsl:template>
</xsl:stylesheet>
```

