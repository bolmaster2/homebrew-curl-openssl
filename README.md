# Homebrew-curl-openssl@1.1

A formula for `curl` with `openssl@1.1` backend named `curl-openssl@1.1`.

## Motivation

To be able to make curl support TLSv1.3 you can't use openssl version 1.0.2, which is the default one in homebrew. `openssl` started [support for TLSv1.3 as of version 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/). Therefore this is a quick-fix of making curl work with openssl 1.1.1 on macos.

## Installation

```shell
brew tap bolmaster2/curl-openssl
brew install curl-openssl@1.1
```

If this is the only curl you want to have first in your `PATH` do:

```shell
export PATH="/usr/local/opt/curl-openssl@1.1/bin:$PATH"
```

## Good to know

This tap includes changing curl dependencies `libssh2` and `nghttp2` to be using `openssl@1.1`.
