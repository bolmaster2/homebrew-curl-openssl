# Homebrew-curl-openssl@1.1

A formula for `curl` with `openssl@1.1` backend named `curl-openssl@1.1`.

## Motivation

To be able to make curl support TLSv1.3 you can't use openssl version 1.0.2, which is the default one in homebrew. `openssl` started [support for TLSv1.3 as of version 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/). Therefore this is a quick-fix of making curl work with openssl 1.1.1 on macOS. This is tested on macos Mojave.

## Installation

```shell
brew tap bolmaster2/curl-openssl
brew install curl-openssl@1.1
```

If this is the only curl you want to have first in your `PATH` do:

```shell
export PATH="/usr/local/opt/curl-openssl@1.1/bin:$PATH"
```

To make sure you got the correct openssl run:

```shell
/usr/local/opt/curl-openssl@1.1/bin/curl --version
```

Expected output is something like this:

```shell
curl 7.65.3 (x86_64-apple-darwin18.7.0) libcurl/7.65.3 OpenSSL/1.1.1c zlib/1.2.11 brotli/1.0.7 c-ares/1.15.0 libidn2/2.2.0 libssh2/1.9.0 nghttp2/1.39.2 librtmp/2.3
Release-Date: 2019-07-19
Protocols: dict file ftp ftps gopher http https imap imaps ldap ldaps pop3 pop3s rtmp rtsp scp sftp smb smbs smtp smtps telnet tftp
Features: AsynchDNS brotli GSS-API HTTP2 HTTPS-proxy IDN IPv6 Kerberos Largefile libz Metalink NTLM NTLM_WB SPNEGO SSL TLS-SRP UnixSockets
```

## Good to know

This tap includes changing curl dependencies `libssh2` and `nghttp2` to be using `openssl@1.1`.
