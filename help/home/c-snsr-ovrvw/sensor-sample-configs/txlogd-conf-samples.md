---
description: サポートされる Web サーバー/OS の組み合わせに対する txlogd.conf ファイルの例。
title: txlogd.conf ファイルのサンプル
uuid: ba8f3938-b7d6-44bd-93ca-eb66f509ef4e
exl-id: 3bbb794f-c771-43c6-9ebf-8892c1d9a707
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 7%

---

# txlogd.conf ファイルのサンプル{#txlogd-conf-file-samples}

{{eol}}

サポートされる Web サーバー/OS の組み合わせに対する txlogd.conf ファイルの例。

## IIS(Microsoft Windows Server 2000 以降 ) {#section-d5d602c3e87b4ecf910e71772350e865}

Microsoft Windows Server 2000 以降で実行されている Sensor for Internet Information Service(IIS)5.x または 6.x に必要な txlogd.conf ファイルの例。

```
# sample txlogd configuration file for IIS

# Unique identifier associated with this sensor, sent to the Server
SensorID SENSOR1

# Address of the Server.
ServerAddress 10.1.0.7

# Encrypt Sensor to Server communication. Defaults to 'on'.
SSL on

# Port used to connect to the Server. Defaults to 443 or 80, depending on SSL being 
# 'on' or 'off'.
ServerPort 443

# The common name (CN) of the Server as set in the Server's certificate.
CertName vs1.domain.com

# Queue file size in MB.
QueueSize 2000

# Path to directory that contains .pem certificate files. This parameter must point to the directory in 
# which the Sensor’s trusted_ca_cert.pem file resides.
CertPath C:\VisualSensor\

# The amount of time in seconds the transmitter will wait to send the next batch of packets. 
# Defaults to 15. Do not change without consulting Adobe.
MaxPageLoadTime 15

# The name of the cookie set on the visitor's browser. Defaults to 'v1st'.
TrackingCookie v1st

# Whether or not to validate the server against CertName. Defaults to 'on'. 
#VerifyCertName on

# Include or exclude certain content types from logging. These will be prefix matched against
# the content type of the reply.
# For example, "image/" will match all image content types while "image/gif" will match only that type
# exactly. When there are multiple matches for a given content-type, the most specific
# match will be used. Therefore, you could put "image/gif" in the ContentFilterInclude and "image/" in
# the ContentFilterExclude and image/gif replies will be allowed but all other image types will be
# filtered out.
ContentFilterInclude *
ContentFilterExclude image/,text/css,application/x-javascript

# For IIS only. Used to work around certain problems. Defaults to 'off'. 
# Only set to 'on' on advice from tech support.
IISCaptureBytesSent off

# IIS only. Used to work around certain problems. Defaults to 'no'. 
# Only set to 'yes' on advice from tech support.
IISUseAlternateHandler no

# Path to the Controlled Experiment configuration file.
ExpFile C:\VisualSensor\experiment.txt

# Resource that, when requested, will cause a new tracking ID to be generated and the user to be placed
# an experiment group. Note that this resource does not have to physically exist on the Web server.
ExpCookieURL /setcookie.htm

# If set to 'on', URLs visited need only match part of the URL listed in the experiment file to be
# considered a match. Defaults to 'off'.
ExpPartialMatch on

# The transmitter (txlogd) will periodically send requests to this location to see if the site is
# operating correctly. Note that the location is specified in the following format, not as a URL:
#        http, <serverAddress>, <port>, /<resource>
# where: <serverAddress> is server name or IP address, <port> is server’s HTTP listening port,
# <resource> is the specific resource to request (can include a query string).
# Only http is supported at this time. Multiple SiteTest lines can be specified.
SiteTest http,localhost,80,/test.html

# Additional HTTP headers to log. Fields will be saved as cs(header-name) in Server. Any valid
# HTTP header can be used (this is not a complete list).
LogHeader Accept
LogHeader Accept-Encoding
LogHeader Connection
LogHeader Host
LogHeader Keep-Alive
LogHeader Referrer

AddressFilter 10.2.1.89
# test machine
AddressFilter 192.168.*.*
# internal IP

DisableField s-dns
DisableField cs(cookie)

PrivacyID 0x1111111

# Send this Cache-Control response header to all new visitors
NewUserCacheControl no-cache=Set-Cookie

# Send this Cache-Control response to returning visitors
CacheControl private,max-age=0,must-revalidate
```

## Lotus Sametime（Windows Server 2000 以降） {#section-36265b8192484a268ebafc42e941fdf2}

Microsoft Windows Server 2000 以降で実行される Lotus Sametime のセンサーに必要な txlogd.conf ファイルの例。

```
# sample txlogd configuration file for Lotus Sametime

# Unique identifier associated with this sensor, sent to the Server.
SensorID SENSOR1

# Address of the Server.
ServerAddress 10.1.0.7

# Encrypt Sensor to Server communication. Defaults to 'on'.
SSL on

# Port used to connect to the Server. Defaults to 443 or 80, depending on SSL being 'on' 
# or 'off'.
ServerPort 443

# The common name (CN) of the Server as set in the Server's certificate.
CertName vs1.domain.com

# Path to directory that contains .pem certificate files.
CertPath C:\VisualSensor

# Full path to the Sensor disk queue on the web server.
# The queue file must be in the same directory as the Transmitter.
QueueFile C:\VisualSensor\diskq2000.log

# Queue file size in MB.
QueueSize 2000

# The amount of time in seconds the transmitter will wait to send the next batch of packets. 
# Defaults to 15.
#MaxPageLoadTime 15

# The name of the cookie set on the visitor's browser. Defaults to 'v1st'.
TrackingCookie v1st

# Whether or not to validate the server against CertName. Defaults to 'on'.
#VerifyCertName on

# Include or exclude certain content types from logging. These will be prefix matched against the
# content type of the reply. For example, "image/" will match all image content types while "image/gif"
# will match only that type exactly. When there are multiple matches for a given content-type, the most
# specific match will be used. Therefore, you could put "image/gif" in the ContentFilterInclude and
# "image/" in the ContentFilterExclude and image/gif replies will be allowed but all other image types
# will be filtered out.
ContentFilterInclude *
ContentFilterExclude image/,text/css,application/x-javascript

# Used to work around certain problems. Defaults to 'no'. Only set to 'yes' on advice from tech
# support. Apache 1.3, 2.x, IHS 1.3, and IHS 2.x only.
ApacheUseAlternateHandler no

# Path to the Controlled Experiment configuration file.
ExpFile C:\VisualSensor\experiment.txt

# If the user visits this page then a new tracking ID is generated and the user is placed in an
# experiment group.
ExpCookieURL /setcookie.html

# If set to 'on', URLs visited need only match part of the URL listed in the experiment file to be
# considered a match. Defaults to 'off'.
ExpPartialMatch on

# The transmitter (txlogd) will periodically send requests to this location to see if the site is
# operating correctly. Note that the location is specified in the following format, not as a URL:
#        http, <serverAddress>, <port>, /<resource>
# where: <serverAddress> is server name or IP address, <port> is server’s HTTP listening port,
# <resource> is the specific resource to request (can include a query string).
# Only http is supported at this time. Multiple SiteTest lines can be specified.
SiteTest http,localhost,80,/test.html
```

## Lotus Domino サーバー（Windows 2000 以降） {#section-d2fd9e0684fe460bbccaaabc4197bb48}

Microsoft Windows Server 2000 以降で実行される Lotus Domino 用 Sensor に必要な txlogd.conf ファイルの例。

```
# sample txlogd configuration file for Lotus Domino

# Unique identifier associated with this sensor, sent to the Server.
SensorID SENSOR1

# Address of the Server.
ServerAddress 10.1.0.7

# Encrypt Sensor to Server communication. Defaults to 'on'.
SSL on

# Port used to connect to the Server. Defaults to 443 or 80, depending on SSL being 'on' 
# or 'off'.
ServerPort 443

# The common name (CN) of the Server as set in the Server's certificate.
CertName vs1.domain.com

# Path to directory that contains .pem certificate files.
CertPath C:\VisualSensor

# Full path to the Sensor disk queue on the web server.
# The queue file must be in the same directory as the Transmitter.
QueueFile C:\VisualSensor\diskq2000.log

# Queue file size in MB.
QueueSize 2000

# The amount of time in seconds the transmitter will wait to send the next batch of packets. 
# Defaults to 15.
#MaxPageLoadTime 15

# The name of the cookie set on the visitor's browser. Defaults to 'v1st'.
TrackingCookie v1st

# Whether or not to validate the server against CertName. Defaults to 'on'.
#VerifyCertName on

# Include or exclude certain content types from logging. These will be prefix matched against the
# content type of the reply. For example, "image/" will match all image content types while "image/gif"
# will match only that type exactly. When there are multiple matches for a given content-type, the most
# specific match will be used. Therefore, you could put "image/gif" in the ContentFilterInclude and
# "image/" in the ContentFilterExclude and image/gif replies will be allowed but all other image types
# will be filtered out.
ContentFilterInclude *
ContentFilterExclude image/,text/css,application/x-javascript

# Used to work around certain problems. Defaults to 'no'. Only set to 'yes' on advice from tech
# support. Apache 1.3, 2.x, IHS 1.3, and IHS 2.x only.
ApacheUseAlternateHandler no

# Path to the Controlled Experiment configuration file.
ExpFile C:\VisualSensor\experiment.txt

# If the user visits this page then a new tracking ID is generated and the user is placed in an
# experiment group.
ExpCookieURL /setcookie.html

# If set to 'on', URLs visited need only match part of the URL listed in the experiment file to be
# considered a match. Defaults to 'off'.
ExpPartialMatch on

# The transmitter (txlogd) will periodically send requests to this location to see if the site is
# operating correctly. Note that the location is specified in the following format, not as a URL:
#        http, <serverAddress>, <port>, /<resource>
# where: <serverAddress> is server name or IP address, <port> is server’s HTTP listening port,
# <resource> is the specific resource to request (can include a query string).
# Only http is supported at this time. Multiple SiteTest lines can be specified.
SiteTest http,localhost,80,/test.html

# Lotus Domino specific additional fields to log (complete list).
SpecialLogField cs(dn)=vars.X509SubjectName vys_log
SpecialLogField cs(cert)=vars.certificate vys_log
```

## IBM AIX 5.2 上のIBM HTTP Server {#section-d7c88cc65b0b4c7a877bf7a084cbf4fb}

IBM AIX 5.2 で実行されるIBM HTTP Server 2.0.x 用 Sensor に必要な txlogd.conf ファイルの例。

```
# sample txlogd configuration file for IHS 2.0.x

# Unique identifier associated with this sensor, sent to the Server.
SensorID SENSOR1

# Address of the Server.
ServerAddress 10.1.0.7

# Encrypt Sensor to Server communication. Defaults to 'on'.
SSL on

# Port used to connect to the Server. Defaults to 443 or 80, depending on SSL being 'on' 
# or 'off'.
ServerPort 443

# The common name (CN) of the Server as set in the Server's certificate.
CertName vs1.domain.com

# Path to directory that contains .pem certificate files.
CertPath /usr/local/visualsensor

# Full path to the Sensor disk queue on the web server.
QueueFile /var/queue/VisualSensor.dat

# Queue file size in MB.
QueueSize 2000

# The amount of time in seconds the transmitter will wait to send the next batch of packets. 
# Defaults to 15.
MaxPageLoadTime 15

# The name of the cookie set on the visitor's browser. Defaults to 'v1st'.
TrackingCookie v1st

# Whether or not to validate the server against CertName. Defaults to 'on'.
#VerifyCertName on

# Include or exclude certain content types from logging. These will be prefix matched against the
# content type of the reply. For example, "image/" will match all image content types while "image/gif"
# will match only that type exactly. When there are multiple matches for a given content-type, the most
# specific match will be used. Therefore, you could put "image/gif" in the ContentFilterInclude and
# "image/" in the ContentFilterExclude and image/gif replies will be allowed but all other image types
# will be filtered out.
ContentFilterInclude *
ContentFilterExclude image/,text/css,application/x-javascript

# Used to work around certain problems. Defaults to 'no'. Only set to 'yes' on advice from tech
# support. Apache 1.3, 2.x, IHS 1.3, and IHS 2.x only.
ApacheUseAlternateHandler no

# Path to the Controlled Experiment configuration file.
ExpFile /home/experiment.txt

# If the user visits this page then a new tracking ID is generated and the user is placed in an
# experiment group.
ExpCookieURL /setcookie.html

# If set to 'on', URLs visited need only match part of the URL listed in the experiment file to be
# considered a match. Defaults to 'off'.
ExpPartialMatch on

# The transmitter (txlogd) will periodically send requests to this location to see if the site is
# operating correctly. Note that the location is specified in the following format, not as a URL:
#        http, <serverAddress>, <port>, /<resource>
# where: <serverAddress> is server name or IP address, <port> is server’s HTTP listening port,
# <resource> is the specific resource to request (can include a query string).
# Only http is supported at this time. Multiple SiteTest lines can be specified.
SiteTest http,localhost,80,/test.html

# Additional HTTP headers to log. Fields will be saved as cs(header-name) in Server. Any valid
# HTTP header can be used (this is not a complete list).
LogHeader Accept
LogHeader Accept-Encoding
LogHeader Connection
LogHeader Host
LogHeader Keep-Alive
LogHeader Referrer

# IHS 2.0.x specific additional fields to log (complete list).
SpecialLogField x = request.allowed vys_log
SpecialLogField x = request.ap_auth_type vys_log
SpecialLogField x = request.query vys_log
SpecialLogField x = request.bytes_sent vys_log
SpecialLogField x = request.canonical_filename vys_log
SpecialLogField x = request.chunked vys_log
SpecialLogField x = request.clength vys_log
SpecialLogField x = request.content_encoding vys_log
SpecialLogField x = request.content_type vys_log
SpecialLogField x = request.eos_sent vys_log
SpecialLogField x = request.expecting_100 vys_log
SpecialLogField x = request.filename vys_log
SpecialLogField x = request.handler vys_log
SpecialLogField x = request.header_only vys_log
SpecialLogField x = request.hostname vys_log
SpecialLogField x = request.method vys_log
SpecialLogField x = request.method_number vys_log
SpecialLogField x = request.mtime vys_log
SpecialLogField x = request.no_cache vys_log
SpecialLogField x = request.no_local_copy vys_log
SpecialLogField x = request.path_info vys_log
SpecialLogField x = request.proto_num vys_log
SpecialLogField x = request.protocol vys_log
SpecialLogField x = request.proxyreq vys_log
SpecialLogField x = request.range vys_log
SpecialLogField x = request.read_body vys_log
SpecialLogField x = request.read_chunked vys_log
SpecialLogField x = request.read_length vys_log
SpecialLogField x = request.remaining vys_log
SpecialLogField x = request.request_time vys_log
SpecialLogField x = request.sent_bodyct vys_log
SpecialLogField x = request.status vys_log
SpecialLogField x = request.status_line vys_log
SpecialLogField x = request.clf-request vys_log
SpecialLogField x = request.unparsed_uri vys_log
SpecialLogField x = request.uri vys_log
SpecialLogField x = request.used_path_info vys_log
SpecialLogField x = request.user vys_log
SpecialLogField x = request.vlist_validator vys_log
SpecialLogField x = headers.Referrer vys_log
SpecialLogField x = headers.User-Agent vys_log
SpecialLogField x = headers.Cookie vys_log
SpecialLogField x = headers_out.Cookie vys_log

AddressFilter 10.2.1.89
# test machine
AddressFilter 192.168.*.*
# internal IP

DisableField s-dns
DisableField cs(cookie)

PrivacyID 0x1111111
```

## RedHat Linux、Sun Solaris、FreeBSD、またはMac OSX 上の Apache サーバー 1.3.x {#section-36d0b6d761424d358280226a16e643d2}

RedHat Linux 7.x、Sun Solaris 2.6 以降、FreeBSD 4 以降、またはMac OS X PowerPC で実行される Apache Server 1.3.x 用の Sensor に必要な txlogd.conf ファイルの例。

```
# sample txlogd configuration file for Apache 1.3

# Unique identifier associated with this sensor, sent to the Server.
SensorID SENSOR1

# Address of the Server.
ServerAddress 10.1.0.7

# Encrypt Sensor to Server communication. Defaults to 'on'.
SSL on

# Port used to connect to the Server. Defaults to 443 or 80, depending on SSL being 'on' 
# or 'off'.
ServerPort 443

# The common name (CN) of the Server as set in the Server's certificate.
CertName vs1.domain.com

# Path to directory that contains .pem certificate files.
CertPath /usr/local/visualsensor

# Full path to the Sensor disk queue on the web server.
QueueFile /var/queue/VisualSensor.dat

# Queue file size in MB.
QueueSize 2000

# The amount of time in seconds the transmitter will wait to send the next batch of packets. 
# Defaults to 15.
#MaxPageLoadTime 15

# The name of the cookie set on the visitor's browser. Defaults to 'v1st'.
TrackingCookie v1st

# Whether or not to validate the server against CertName. Defaults to 'on'.
#VerifyCertName on

# Include or exclude certain content types from logging. These will be prefix matched against the
# content type of the reply. For example, "image/" will match all image content types while "image/gif"
# will match only that type exactly. When there are multiple matches for a given content-type, the most
# specific match will be used. Therefore, you could put "image/gif" in the ContentFilterInclude and
# "image/" in the ContentFilterExclude and image/gif replies will be allowed but all other image types
# will be filtered out.
ContentFilterInclude *
ContentFilterExclude image/,text/css,application/x-javascript

# Used to work around certain problems. Defaults to 'no'. Only set to 'yes' on advice from tech
# support. Apache 1.3, 2.x, IHS 1.3, and IHS 2.x only.
ApacheUseAlternateHandler no

# Path to the Controlled Experiment configuration file.
ExpFile /home/experiment.txt

# If the user visits this page then a new tracking ID is generated and the user is placed in an
# experiment group.
ExpCookieURL /setcookie.html

# If set to 'on', URLs visited need only match part of the URL listed in the experiment file to be
# considered a match. Defaults to 'off'.
ExpPartialMatch on

# The transmitter (txlogd) will periodically send requests to this location to see if the site is
# operating correctly. Note that the location is specified in the following format, not as a URL:
#        http, <serverAddress>, <port>, /<resource>
# where: <serverAddress> is server name or IP address, <port> is server’s HTTP listening port,
# <resource> is the specific resource to request (can include a query string).
# Only http is supported at this time. Multiple SiteTest lines can be specified.
SiteTest http,localhost,80,/test.html

# Additional HTTP headers to log. Fields will be saved as cs(header-name) in Server. Any valid
# HTTP header can be used (this is not a complete list).
LogHeader Accept
LogHeader Accept-Encoding
LogHeader Connection
LogHeader Host
LogHeader Keep-Alive
LogHeader Referrer

# Apache 1.3 specific additional fields to log (complete list).
SpecialLogField x = request.allowed vys_log
SpecialLogField x = request.boundary vys_log
SpecialLogField x = request.byterange vys_log
SpecialLogField x = request.bytes_sent vys_log
SpecialLogField x = request.case_preserved_filename vys_log
SpecialLogField x = request.chunked vys_log
SpecialLogField x = request.clength vys_log
SpecialLogField x = request.clf-request vys_log
SpecialLogField x = request.content_encoding vys_log
SpecialLogField x = request.content_type vys_log
SpecialLogField x = request.expecting_100 vys_log
SpecialLogField x = request.filename vys_log
SpecialLogField x = request.handler vys_log
SpecialLogField x = request.header_only vys_log
SpecialLogField x = request.hostname vys_log
SpecialLogField x = request.method vys_log
SpecialLogField x = request.method_number vys_log
SpecialLogField x = request.mtime vys_log
SpecialLogField x = request.no_cache vys_log
SpecialLogField x = request.no_local_copy vys_log
SpecialLogField x = request.path_info vys_log
SpecialLogField x = request.proto_num vys_log
SpecialLogField x = request.protocol vys_log
SpecialLogField x = request.query vys_log
SpecialLogField x = request.range vys_log
SpecialLogField x = request.read_body vys_log
SpecialLogField x = request.read_chunked vys_log
SpecialLogField x = request.read_length vys_log
SpecialLogField x = request.remaining vys_log
SpecialLogField x = request.request_time vys_log
SpecialLogField x = request.sent_bodyct vys_log
SpecialLogField x = request.status vys_log
SpecialLogField x = request.status_line vys_log
SpecialLogField x = request.unparsed_uri vys_log
SpecialLogField x = request.uri vys_log
SpecialLogField x = request.vlist_validator vys_log
SpecialLogField x = headers.Referrer vys_log
SpecialLogField x = headers.User-Agent vys_log
SpecialLogField x = headers.Cookie vys_log
SpecialLogField x = headers_out.Cookie vys_log

AddressFilter 10.2.1.89
# test machine
AddressFilter 192.168.*.*
# internal IP

DisableField s-dns
DisableField cs(cookie)

PrivacyID 0x1111111

# Send this Cache-Control response header to all new visitors
NewUserCacheControl no-cache=Set-Cookie

# Send this Cache-Control response to returning visitors
CacheControl private,max-age=0,must-revalidate
```

## Apache サーバー 1.3.x（Windows 2000 Server 以降） {#section-d225f200da28441895fb90a64c2a2ffd}

Microsoft Windows Server 2000 以降で動作する Apache サーバー 1.3.x 用 Sensor で必要な txlogd.conf ファイルの例。

```
# sample txlogd configuration file for Apache 1.3

# Unique identifier associated with this sensor, sent to the Server.
SensorID SENSOR1

# Address of the Server.
ServerAddress 10.1.0.7

# Encrypt Sensor to Server communication. Defaults to 'on'.
SSL on

# Port used to connect to the Server. Defaults to 443 or 80, depending on SSL being 'on' 
# or 'off'.
ServerPort 443

# The common name (CN) of the Server as set in the Server's certificate.
CertName vs1.domain.com

# Path to directory that contains .pem certificate files.
CertPath C:\VisualSensor

# Full path to the Sensor disk queue on the web server.
# The queue file must be in the same directory as the Transmitter.
QueueFile C:\VisualSensor\diskq2000.log

# Queue file size in MB.
QueueSize 2000

# The amount of time in seconds the transmitter will wait to send the next batch of packets. 
# Defaults to 15.
#MaxPageLoadTime 15

# The name of the cookie set on the visitor's browser. Defaults to 'v1st'.
TrackingCookie v1st

# Whether or not to validate the server against CertName. Defaults to 'on'.
#VerifyCertName on

# Include or exclude certain content types from logging. These will be prefix matched against the
# content type of the reply. For example, "image/" will match all image content types while "image/gif"
# will match only that type exactly. When there are multiple matches for a given content-type, the most
# specific match will be used. Therefore, you could put "image/gif" in the ContentFilterInclude and
# "image/" in the ContentFilterExclude and image/gif replies will be allowed but all other image types
# will be filtered out.
ContentFilterInclude *
ContentFilterExclude image/,text/css,application/x-javascript

# Used to work around certain problems. Defaults to 'no'. Only set to 'yes' on advice from tech
# support. Apache 1.3, 2.x, IHS 1.3, and IHS 2.x only.
ApacheUseAlternateHandler no

# Path to the Controlled Experiment configuration file.
ExpFile C:\VisualSensor\experiment.txt

# If the user visits this page then a new tracking ID is generated and the user is placed in an
# experiment group.
ExpCookieURL /setcookie.html

# If set to 'on', URLs visited need only match part of the URL listed in the experiment file to be
# considered a match. Defaults to 'off'.
ExpPartialMatch on

# The transmitter (txlogd) will periodically send requests to this location to see if the site is
# operating correctly. Note that the location is specified in the following format, not as a URL:
#        http, <serverAddress>, <port>, /<resource>
# where: <serverAddress> is server name or IP address, <port> is server’s HTTP listening port,
# <resource> is the specific resource to request (can include a query string).
# Only http is supported at this time. Multiple SiteTest lines can be specified.
SiteTest http,localhost,80,/test.html

# Additional HTTP headers to log. Fields will be saved as cs(header-name) in Server. Any valid
# HTTP header can be used (this is not a complete list).
LogHeader Accept
LogHeader Accept-Encoding
LogHeader Connection
LogHeader Host
LogHeader Keep-Alive
LogHeader Referrer

# Apache 1.3 specific additional fields to log (complete list).
SpecialLogField x = request.allowed vys_log
SpecialLogField x = request.boundary vys_log
SpecialLogField x = request.byterange vys_log
SpecialLogField x = request.bytes_sent vys_log
SpecialLogField x = request.case_preserved_filename vys_log
SpecialLogField x = request.chunked vys_log
SpecialLogField x = request.clength vys_log
SpecialLogField x = request.clf-request vys_log
SpecialLogField x = request.content_encoding vys_log
SpecialLogField x = request.content_type vys_log
SpecialLogField x = request.expecting_100 vys_log
SpecialLogField x = request.filename vys_log
SpecialLogField x = request.handler vys_log
SpecialLogField x = request.header_only vys_log
SpecialLogField x = request.hostname vys_log
SpecialLogField x = request.method vys_log
SpecialLogField x = request.method_number vys_log
SpecialLogField x = request.mtime vys_log
SpecialLogField x = request.no_cache vys_log
SpecialLogField x = request.no_local_copy vys_log
SpecialLogField x = request.path_info vys_log
SpecialLogField x = request.proto_num vys_log
SpecialLogField x = request.protocol vys_log
SpecialLogField x = request.query vys_log
SpecialLogField x = request.range vys_log
SpecialLogField x = request.read_body vys_log
SpecialLogField x = request.read_chunked vys_log
SpecialLogField x = request.read_length vys_log
SpecialLogField x = request.remaining vys_log
SpecialLogField x = request.request_time vys_log
SpecialLogField x = request.sent_bodyct vys_log
SpecialLogField x = request.status vys_log
SpecialLogField x = request.status_line vys_log
SpecialLogField x = request.unparsed_uri vys_log
SpecialLogField x = request.uri vys_log
SpecialLogField x = request.vlist_validator vys_log
SpecialLogField x = headers.Referrer vys_log
SpecialLogField x = headers.User-Agent vys_log
SpecialLogField x = headers.Cookie vys_log
SpecialLogField x = headers_out.Cookie vys_log

AddressFilter 10.2.1.89
# test machine
AddressFilter 192.168.*.*
# internal IP

DisableField s-dns
DisableField cs(cookie)

PrivacyID 0x1111111

# Send this Cache-Control response header to all new visitors
NewUserCacheControl no-cache=Set-Cookie

# Send this Cache-Control response to returning visitors
CacheControl private,max-age=0,must-revalidate
```

## Apache サーバー 2.0.x または 2.2（Linux、Sun Solaris、FreeBSD のいずれか） {#section-b87565beba44472483348d442329c3fe}

次の Apache サーバーの Sensor に必要な txlogd.conf ファイルの例。

```
Apache Server 2.0.40 running under RedHat Linux 7.x or later or Sun Solaris SPARC 2.6 or later
Apache Server 2.0.42 or later running under RedHat Linux 7.x or later, Sun Solaris SPARC 2.6 or later, SUSE Linux 9.x or later, or FreeBSD 5.3
Apache Server 2.0.42 or later running under 64-bit versions of RedHat Linux ES 4 and  ES 5
Apache Server 2.2 running under RedHat Linux 7.x or later

# sample txlogd configuration file for Apache 2.0.x or 2.2

# Unique identifier associated with this sensor, sent to the Server.
SensorID SENSOR1

# Address of the Server.
ServerAddress 10.1.0.7

# Encrypt Sensor to Server communication.
# Defaults to 'on'.
SSL on

# Port used to connect to the Server. Defaults to 443 or 80, depending on SSL being 'on' or 'off'.
ServerPort 443

# The common name (CN) of the Server as set in the Server's certificate.
CertName vs1.domain.com

# Path to directory that contains .pem certificate files.
CertPath /usr/local/visualsensor

# Full path to the Sensor disk queue on the web server.
QueueFile /var/queue/VisualSensor.dat

# Queue file size in MB.
QueueSize 2000

# The amount of time in seconds the transmitter will wait to send the next batch of packets. Defaults to 15.
MaxPageLoadTime 15

# The name of the cookie set on the visitor's browser. Defaults to 'v1st'.
TrackingCookie v1st

# Whether or not to validate the server against CertName. Defaults to 'on'.
#VerifyCertName on

# Include or exclude certain content types from logging. These will be prefix matched against the
# content type of the reply. For example, "image/" will match all image content types while "image/gif"
# will match only that type exactly. When there are multiple matches for a given content-type, the most
# specific match will be used. Therefore, you could put "image/gif" in the ContentFilterInclude and
# "image/" in the ContentFilterExclude and image/gif replies will be allowed but all other image types will be filtered out.
ContentFilterInclude *
ContentFilterExclude image/,text/css,application/x-javascript

# Apache 1.3, 2.x, IHS 1.3, and IHS 2.x only. Used to work around certain problems. Defaults to 'no'. 
# Only set to 'yes' on advice from tech support. 
ApacheUseAlternateHandler no

# Path to the Controlled Experiment configuration file.
ExpFile /home/experiment.txt

# If the user visits this page then a new tracking ID is generated and the user is placed in an experiment group.
ExpCookieURL /setcookie.htm

# If set to 'on', URLs visited need only match part of the URL listed in the experiment file to be
# considered a match. Defaults to 'off'.
ExpPartialMatch on

# The transmitter (txlogd) will periodically send requests to this location to see if the site is
# operating correctly. Note that the location is specified in the following format, not as a URL:
#        http, <serverAddress>, <port>, /<resource>
# where: <serverAddress> is server name or IP address, <port> is server’s HTTP listening port,
# <resource> is the specific resource to request (can include a query string).
# Only http is supported at this time. Multiple SiteTest lines can be specified.
SiteTest http,localhost,80,/test.html

# Additional HTTP headers to log. Fields will be saved as cs(header-name) in Server. Any valid
# HTTP header can be used (this is not a complete list).
LogHeader Accept
LogHeader Accept-Encoding
LogHeader Connection
LogHeader Host
LogHeader Keep-Alive
LogHeader Referrer

# Apache 2.0.x specific additional fields to log (complete list).
SpecialLogField x = request.allowed vys_log
SpecialLogField x = request.ap_auth_type vys_log
SpecialLogField x = request.query vys_log
SpecialLogField x = request.bytes_sent vys_log
SpecialLogField x = request.canonical_filename vys_log
SpecialLogField x = request.chunked vys_log
SpecialLogField x = request.clength vys_log
SpecialLogField x = request.content_encoding vys_log
SpecialLogField x = request.content_type vys_log
SpecialLogField x = request.eos_sent vys_log
SpecialLogField x = request.expecting_100 vys_log
SpecialLogField x = request.filename vys_log
SpecialLogField x = request.handler vys_log
SpecialLogField x = request.header_only vys_log
SpecialLogField x = request.hostname vys_log
SpecialLogField x = request.method vys_log
SpecialLogField x = request.method_number vys_log
SpecialLogField x = request.mtime vys_log
SpecialLogField x = request.no_cache vys_log
SpecialLogField x = request.no_local_copy vys_log
SpecialLogField x = request.path_info vys_log
SpecialLogField x = request.proto_num vys_log
SpecialLogField x = request.protocol vys_log
SpecialLogField x = request.proxyreq vys_log
SpecialLogField x = request.range vys_log
SpecialLogField x = request.read_body vys_log
SpecialLogField x = request.read_chunked vys_log
SpecialLogField x = request.read_length vys_log
SpecialLogField x = request.remaining vys_log
SpecialLogField x = request.request_time vys_log
SpecialLogField x = request.sent_bodyct vys_log
SpecialLogField x = request.status vys_log
SpecialLogField x = request.status_line vys_log
SpecialLogField x = request.clf-request vys_log
SpecialLogField x = request.unparsed_uri vys_log
SpecialLogField x = request.uri vys_log
SpecialLogField x = request.used_path_info vys_log
SpecialLogField x = request.user vys_log
SpecialLogField x = request.vlist_validator vys_log
SpecialLogField x = headers.Referrer vys_log
SpecialLogField x = headers.User-Agent vys_log
SpecialLogField x = headers.Cookie vys_log
SpecialLogField x = headers_out.Cookie vys_log

AddressFilter 10.2.1.89
# test machine
AddressFilter 192.168.*.*
# internal IP

DisableField s-dns
DisableField cs(cookie)

PrivacyID 0x1111111

# Send this Cache-Control response header to all new visitors
NewUserCacheControl no-cache=Set-Cookie

# Send this Cache-Control response to returning visitors
CacheControl private,max-age=0,must-revalidate
```

## Apache Server 2.0.x または 2.2（Windows Server 2000 以降） {#section-a1749d32a8aa4ca0b81f8b95c8dc511c}

Microsoft Windows Server 2000 以降で動作する Apache Server 2.0.x または 2.2 用の Sensor で必要な txlogd.conf ファイルの例。

```
# sample txlogd configuration file for Apache 2.0.x or 2.2

# Unique identifier associated with this sensor, sent to the Server.
SensorID SENSOR1

# Address of the Server.
ServerAddress 10.1.0.7

# Encrypt Sensor to Server communication.
# Defaults to 'on'.
SSL on

# Port used to connect to the Server. Defaults to 443 or 80, depending on SSL being 'on' 
# or 'off'.
ServerPort 443

# The common name (CN) of the Server as set in the Server's certificate.
CertName vs1.domain.com

# Path to directory that contains .pem certificate files.
CertPath C:\VisualSensor

# Full path to the Sensor disk queue on the web server.
# The queue file must be in the same directory as the Transmitter.
QueueFile C:\VisualSensor\diskq2000.log

# Queue file size in MB.
QueueSize 2000

# The amount of time in seconds the transmitter will wait to send the next batch of packets. 
# Defaults to 15.
MaxPageLoadTime 15

# The name of the cookie set on the visitor's browser. Defaults to 'v1st'.
TrackingCookie v1st

# Whether or not to validate the server against CertName. Defaults to 'on'.
#VerifyCertName on

# Include or exclude certain content types from logging. These will be prefix matched against the
# content type of the reply. For example, "image/" will match all image content types while "image/gif"
# will match only that type exactly. When there are multiple matches for a given content-type, the most
# specific match will be used. Therefore, you could put "image/gif" in the ContentFilterInclude and
# "image/" in the ContentFilterExclude and image/gif replies will be allowed but all other image types
# will be filtered out.
ContentFilterInclude *
ContentFilterExclude image/,text/css,application/x-javascript

# Apache 1.3, 2.x, IHS 1.3, and IHS 2.x only. Used to work around certain problems. Defaults to 'no'. 
# Only set to 'yes' on advice from tech support. 
ApacheUseAlternateHandler no

# Path to the Controlled Experiment configuration file.
ExpFile C:\VisualSensor\experiment.txt

# If the user visits this page then a new tracking ID is generated and the user is placed in an
# experiment group.
ExpCookieURL /setcookie.htm

# If set to 'on', URLs visited need only match part of the URL listed in the experiment file to be
# considered a match. Defaults to 'off'.
ExpPartialMatch on

# The transmitter (txlogd) will periodically send requests to this location to see if the site is
# operating correctly. Note that the location is specified in the following format, not as a URL:
#        http, <serverAddress>, <port>, /<resource>
# where: <serverAddress> is server name or IP address, <port> is server’s HTTP listening port,
# <resource> is the specific resource to request (can include a query string).
# Only http is supported at this time. Multiple SiteTest lines can be specified.
SiteTest http,localhost,80,/test.html

# Additional HTTP headers to log. Fields will be saved as cs(header-name) in Server. Any valid
# HTTP header can be used (this is not a complete list).
LogHeader Accept
LogHeader Accept-Encoding
LogHeader Connection
LogHeader Host
LogHeader Keep-Alive
LogHeader Referrer

# Apache 2.0.x specific additional fields to log (complete list).
SpecialLogField x = request.allowed vys_log
SpecialLogField x = request.ap_auth_type vys_log
SpecialLogField x = request.query vys_log
SpecialLogField x = request.bytes_sent vys_log
SpecialLogField x = request.canonical_filename vys_log
SpecialLogField x = request.chunked vys_log
SpecialLogField x = request.clength vys_log
SpecialLogField x = request.content_encoding vys_log
SpecialLogField x = request.content_type vys_log
SpecialLogField x = request.eos_sent vys_log
SpecialLogField x = request.expecting_100 vys_log
SpecialLogField x = request.filename vys_log
SpecialLogField x = request.handler vys_log
SpecialLogField x = request.header_only vys_log
SpecialLogField x = request.hostname vys_log
SpecialLogField x = request.method vys_log
SpecialLogField x = request.method_number vys_log
SpecialLogField x = request.mtime vys_log
SpecialLogField x = request.no_cache vys_log
SpecialLogField x = request.no_local_copy vys_log
SpecialLogField x = request.path_info vys_log
SpecialLogField x = request.proto_num vys_log
SpecialLogField x = request.protocol vys_log
SpecialLogField x = request.proxyreq vys_log
SpecialLogField x = request.range vys_log
SpecialLogField x = request.read_body vys_log
SpecialLogField x = request.read_chunked vys_log
SpecialLogField x = request.read_length vys_log
SpecialLogField x = request.remaining vys_log
SpecialLogField x = request.request_time vys_log
SpecialLogField x = request.sent_bodyct vys_log
SpecialLogField x = request.status vys_log
SpecialLogField x = request.status_line vys_log
SpecialLogField x = request.clf-request vys_log
SpecialLogField x = request.unparsed_uri vys_log
SpecialLogField x = request.uri vys_log
SpecialLogField x = request.used_path_info vys_log
SpecialLogField x = request.user vys_log
SpecialLogField x = request.vlist_validator vys_log
SpecialLogField x = headers.Referrer vys_log
SpecialLogField x = headers.User-Agent vys_log
SpecialLogField x = headers.Cookie vys_log
SpecialLogField x = headers_out.Cookie vys_log

AddressFilter 10.2.1.89
# test machine
AddressFilter 192.168.*.*
# internal IP

DisableField s-dns
DisableField cs(cookie)

PrivacyID 0x1111111

# Send this Cache-Control response header to all new visitors
NewUserCacheControl no-cache=Set-Cookie

# Send this Cache-Control response to returning visitors
CacheControl private,max-age=0,must-revalidate
```

## セクションタイトル {#section-f25d181e181e4bb7bf46d4410756e945}
