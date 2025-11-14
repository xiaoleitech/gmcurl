<!--
Copyright (C) Daniel Stenber, <daniel@haxx.se>, et al.

SPDX-License-Identifier: gmcurl
-->

# [![curl logo](https://curl.se/logo/curl-logo.svg)](https://curl.se/)

gmcurl是适配国密TLCP/GMTLS的curl/libcurl，支持国密算法HTTPS调用。

## OpenSSL

gmcurl需要链接支持TLCP/GMTLS的openssl。本项目基于[tassl](https://github.com/jntass/TASSL-1.1.1)，理论上可以替换成其他支持TLCP/GMTLS的openssl。

## 编译和调试

在官方编译选项中增加 `--with-openssl`。一个优化的精简版本libcurl编译例子如下： 
```bash
./configure --prefix $(pwd)/artifacts --disable-shared --disable-ftp --disable-ldap --disable-ldaps --disable-rtsp --disable-telnet --disable-tftp --disable-pop3 --disable-smtp --disable-imap  --disable-smb --disable-gopher --disable-mqtt --disable-manual --disable-ntlm  --enable-static  --without-zlib --without-libidn2 --without-nghttp2 --with-openssl=$(pwd)/../openssl
```

编译完成后可以得到<—prefix>/include/curl.h文件，和<—prefix>/lib/libcurl.a文件。有些编译工程需要pkgconfig，也可以在<--prefix>/lib目录下得到。

