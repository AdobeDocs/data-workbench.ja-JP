---
description: 設定ファイルのサンプルファイル。
title: 設定ファイルのサンプル
uuid: 9bc5c0a9-e67a-4c63-952d-9a39d75e6975
exl-id: 8a9abadb-228b-4da6-bfe6-8e828bb6ace9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 8%

---

# 設定ファイルのサンプル{#sample-configuration-files}

{{eol}}

設定ファイルのサンプルファイル。

## Magnus.conf ファイルのサンプル {#section-aec81c734d0f483591c3ede1fe588b6a}

Netscape Enterprise Server、iPlanet、Sun ONE、Sun Java System Web サーバーの完全な magnus.conf ファイルのインストールと設定の例。

```
#ServerRoot /usr/iplanet/servers/https-nova.visualsciences.net
ServerID https-nova.visualsciences.net
ServerName nova.visualsciences.net
ErrorLog /usr/iplanet/servers/https-nova.visualsciences.net/logs/errors
PidLog /usr/iplanet/servers/https-nova.visualsciences.net/logs/pid
User nobody
MtaHost localhost
DNS off
Security off
ClientLanguage en
AdminLanguage en
DefaultLanguage en
RqThrottle 128
StackSize 131072
CGIWaitPid on
TempDir /tmp/https-nova.visualsciences.net-ab0d7966
Init fn=flex-init access="$accesslog" format.access="%Ses->client.ip% - %Req->vars.auth-user% [%SYSDATE%] \"%Req->reqpb.clf-request%\" %Req->srvhdrs.clf-status% %Req->srvhdrs.content-length%"
Init fn=load-types mime-types=mime.types
Init fn="load-modules" shlib="/usr/iplanet/servers/bin/https/lib/libNSServletPlugin.so" funcs="NSServletEarlyInit,NSServletLateInit,NSServletNameTrans,NSServletService" shlib_flags="(global|now)"
Init fn="NSServletEarlyInit" EarlyInit=yes
Init fn="NSServletLateInit"  LateInit=yes
Init fn="load-modules" shlib="/usr/iplanet/servers/visual_sciences/saf_visual_sciences.so" funcs="vys-cookie,vys-log,vys-init,vys-content-type"
Init fn="vys-init" config-file="/etc/txlogd.conf"
```

## Obj.conf ファイルのサンプル {#section-1acd3ae557074ee6a46492eb98f89805}

Netscape Enterprise Server、iPlanet、Sun ONE、Sun Java System Web サーバーの完全な obj.conf ファイルのインストールと設定の例。

```
<Object name=default>
  NameTrans fn="vys-cookie"
  NameTrans fn="NSServletNameTrans" name="servlet"
  NameTrans fn="pfx2dir" from="/servlet" dir="/usr/iplanet/servers/docs/servlet" name="ServletByExt"
  NameTrans fn=pfx2dir from=/mc-icons dir="/usr/iplanet/servers/ns-icons" name="es-internal"
  NameTrans fn="pfx2dir" from="/manual" dir="/usr/iplanet/servers/manual/https" name="es-internal"
  NameTrans fn=document-root root="$docroot"
  PathCheck fn=unix-uri-clean
  PathCheck fn="check-acl" acl="default"
  PathCheck fn=find-pathinfo
  PathCheck fn=find-index index-names="index.html,home.html"
  ObjectType fn=type-by-extension
  ObjectType fn=force-type type=text/plain     
  ObjectType fn="vys-content-type"
  Service type="magnus-internal/jsp" fn="NSServletService"
  Service method=(GET|HEAD) type=magnus-internal/imagemap fn=imagemap
  Service method=(GET|HEAD) type=magnus-internal/directory fn=index-common
  Service method=(GET|HEAD|POST) type=*~magnus-internal/* fn=send-file
  AddLog fn=flex-log name="access"
  AddLog fn="vys-log"
</Object>

<Object name=cgi>
  ObjectType fn=force-type type=magnus-internal/cgi
  Service fn=send-cgi user="$user" group="$group" chroot="$chroot" dir="$dir" nice="$nice"
</Object>

<Object name="servlet">
  ObjectType fn=force-type type=text/html
  Service fn="NSServletService"
</Object>

<Object name="jsp092">
  ObjectType fn="type-by-extension"
  ObjectType fn="change-type" type="magnus-internal/jsp092" if-type="magnus-internal/jsp"
  Service fn="NSServletService" type="magnus-internal/jsp092"
</Object>

<Object name="ServletByExt">
  ObjectType fn=force-type type=magnus-internal/servlet
  Service type="magnus-internal/servlet" fn="NSServletService"
</Object>

<Object name="es-internal">
  PathCheck fn="check-acl" acl="es-internal"
</Object>
```
