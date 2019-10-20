+++
title= "Install"
date= 2019-10-02T22:01:36+02:00
tags = ["install"]
description = "cargo install s3mon"
+++

To install `s3mon`:

    $ cargo install s3mon

> check your PATH `$HOME/.cargo/bin/s3mon`


```sh
$ ~/.cargo/bin/s3mon -h
s3mon x.x.x

USAGE:
    s3mon [OPTIONS]

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information

OPTIONS:
    -c, --config <FILE>    config.yml

```

If you don't have [`cargo`](https://doc.rust-lang.org/cargo/getting-started/installation.html) try:

```sh
$ curl https://sh.rustup.rs -sSf | sh
```
