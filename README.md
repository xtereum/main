## EXtereum-Ethereum - a fast, light, and robust EVM and WASM blockchain client

### [» Download the latest release «](https://github.com/EXtereumtech/EXtereum-ethereum/releases/latest)

[![build status](https://gitlab.EXtereum.io/EXtereum/EXtereum/badges/master/build.svg)](https://gitlab.EXtereum.io/EXtereum/EXtereum/commits/master)
[![codecov](https://codecov.io/gh/EXtereumtech/EXtereum/branch/master/graph/badge.svg)](https://codecov.io/gh/EXtereumtech/EXtereum)
[![Snap Status](https://build.snapcraft.io/badge/EXtereumtech/EXtereum.svg)](https://build.snapcraft.io/user/EXtereumtech/EXtereum)
[![GPLv3](https://img.shields.io/badge/license-GPL%20v3-green.svg)](https://www.gnu.org/licenses/gpl-3.0.en.html)


### Join the chat!

Get in touch with us on Gitter:
[![Gitter: EXtereum](https://img.shields.io/badge/gitter-EXtereum-4AB495.svg)](https://gitter.im/EXtereumtech/EXtereum)
[![Gitter: EXtereum.js](https://img.shields.io/badge/gitter-EXtereum.js-4AB495.svg)](https://gitter.im/EXtereumtech/EXtereum.js)
[![Gitter: EXtereum/Miners](https://img.shields.io/badge/gitter-EXtereum/miners-4AB495.svg)](https://gitter.im/EXtereumtech/EXtereum/miners)
[![Gitter: EXtereum-PoA](https://img.shields.io/badge/gitter-EXtereum--poa-4AB495.svg)](https://gitter.im/EXtereumtech/EXtereum-poa)

Or join our community on Matrix:
[![Riot: +EXtereum](https://img.shields.io/badge/riot-%2BEXtereum%3Amatrix.EXtereum.io-orange.svg)](https://riot.im/app/#/group/+EXtereum:matrix.EXtereum.io)

Official website: https://EXtereum.io | Be sure to check out [our wiki](https://wiki.EXtereum.io) for more information.

----

## About EXtereum-Ethereum

EXtereum-Ethereum's goal is to be the fastest, lightest, and most secure Ethereum client. We are developing EXtereum-Ethereum using the sophisticated and cutting-edge Rust programming language. EXtereum-Ethereum is licensed under the GPLv3, and can be used for all your Ethereum needs.

By default, EXtereum-Ethereum will run a JSON-RPC HTTP server on `127.0.0.1:8545` and a Web-Sockets server on `127.0.0.1:8546`. This is fully configurable and supports a number of APIs.

If you run into problems while using EXtereum-Ethereum, feel free to file an issue in this repository or hop on our [Gitter](https://gitter.im/EXtereumtech/EXtereum) or [Riot](https://riot.im/app/#/group/+EXtereum:matrix.EXtereum.io) chat room to ask a question. We are glad to help! **For security-critical issues**, please refer to the security policy outlined in [SECURITY.md](SECURITY.md).

EXtereum-Ethereum's current beta-release is 2.0. You can download it at [the releases page](https://github.com/EXtereumtech/EXtereum-ethereum/releases) or follow the instructions below to build from source. Please, mind the [CHANGELOG.md](CHANGELOG.md) for a list of all changes between different versions.

----

## Build dependencies

**EXtereum-Ethereum requires Rust version 1.27.0 to build**

We recommend installing Rust through [rustup](https://www.rustup.rs/). If you don't already have rustup, you can install it like this:

- Linux:
  ```bash
  $ curl https://sh.rustup.rs -sSf | sh
  ```

  EXtereum-Ethereum also requires `gcc`, `g++`, `libudev-dev`, `pkg-config`, `file`, `make`, and `cmake` packages to be installed.

- OSX:
  ```bash
  $ curl https://sh.rustup.rs -sSf | sh
  ```

  `clang` is required. It comes with Xcode command line tools or can be installed with homebrew.

- Windows
  Make sure you have Visual Studio 2015 with C++ support installed. Next, download and run the rustup installer from
  https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe, start "VS2015 x64 Native Tools Command Prompt", and use the following command to install and set up the msvc toolchain:
  ```bash
  $ rustup default stable-x86_64-pc-windows-msvc
  ```

Once you have rustup installed, then you need to install:
* [Perl](https://www.perl.org)
* [Yasm](http://yasm.tortall.net)

Make sure that these binaries are in your `PATH`. After that you should be able to build EXtereum-Ethereum from source.

----

## Install from the snap store

In any of the [supported Linux distros](https://snapcraft.io/docs/core/install):

```bash
sudo snap install EXtereum
```

Or, if you want to contribute testing the upcoming release:

```bash
sudo snap install EXtereum --beta
```

And to test the latest code landed into the master branch:

```bash
sudo snap install EXtereum --edge
```

----

## Build from source

```bash
# download EXtereum-Ethereum code
$ git clone https://github.com/EXtereumtech/EXtereum-ethereum
$ cd EXtereum-ethereum

# build in release mode
$ cargo build --release --features final
```

This will produce an executable in the `./target/release` subdirectory.

Note: if cargo fails to parse manifest try:

```bash
$ ~/.cargo/bin/cargo build --release
```

Note, when compiling a crate and you receive errors, it's in most cases your outdated version of Rust, or some of your crates have to be recompiled. Cleaning the repository will most likely solve the issue if you are on the latest stable version of Rust, try:

```bash
$ cargo clean
```

This will always compile the latest nightly builds. If you want to build stable or beta, do a

```bash
$ git checkout stable
```

or

```bash
$ git checkout beta
```

first.

----

## Simple one-line installer for Mac and Ubuntu

```bash
bash <(curl https://get.EXtereum.io -L)
```

The one-line installer always defaults to the latest beta release. To install a stable release, run:

```bash
bash <(curl https://get.EXtereum.io -L) -r stable
```

## Start EXtereum-Ethereum

### Manually

To start EXtereum-Ethereum manually, just run

```bash
$ ./target/release/EXtereum
```

and EXtereum-Ethereum will begin syncing the Ethereum blockchain.

### Using systemd service file

To start EXtereum-Ethereum as a regular user using systemd init:

1. Copy `./scripts/EXtereum.service` to your
systemd user directory (usually `~/.config/systemd/user`).
2. To configure EXtereum-Ethereum, write a `/etc/EXtereum/config.toml` config file, see [Configuring EXtereum-Ethereum](https://EXtereumtech.github.io/wiki/Configuring-EXtereum) for details.
