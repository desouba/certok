# certok

[![Travis CI](https://img.shields.io/travis/genuinetools/certok.svg?style=for-the-badge)](https://travis-ci.org/genuinetools/certok)
[![GoDoc](https://img.shields.io/badge/godoc-reference-5272B4.svg?style=for-the-badge)](https://godoc.org/github.com/genuinetools/certok)
[![Github All Releases](https://img.shields.io/github/downloads/genuinetools/certok/total.svg?style=for-the-badge)](https://github.com/genuinetools/certok/releases)

Command line tool to check the validity and expiration dates of SSL certificates.

 * [Installation](README.md#installation)
      * [Binaries](README.md#binaries)
      * [Via Go](README.md#via-go)
 * [Usage](README.md#usage)

## Installation

#### Binaries

For installation instructions from binaries please visit the [Releases Page](https://github.com/genuinetools/certok/releases).

#### Via Go

```console
$ go get github.com/genuinetools/certok
```

## Usage

Pass a line deliminated file filled with hostnames to either stdin or the first
argument of the command. For example:

```console
$ certok ~/hostsfile
NAME                 SUBJECT            ISSUER                        ALGO           EXPIRES     SUNSET DATE
telize.j3ss.co:443   telize.j3ss.co     Let's Encrypt Authority X3    SHA256-RSA     77 days
r.j3ss.co:443        r.j3ss.co          Let's Encrypt Authority X3    SHA256-RSA     77 days
contained.af:443     contained.af       Let's Encrypt Authority X3    SHA256-RSA     77 days
```

```console
$ certok -h
certok -  A tool to check the validity and expiration dates of SSL certificates.

Usage: certok <command>

Flags:

  -all     Show entire certificate chain, not just the first. (default: false)
  -d       enable debug logging (default: false)
  -days    Warn if the certificate will expire within this many days. (default: 0)
  -months  Warn if the certificate will expire within this many months. (default: 0)
  -years   Warn if the certificate will expire within this many years. (default: 0)

Commands:

  version  Show the version information.
```
