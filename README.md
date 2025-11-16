<h1 align="center">
  <img src="Meta.png" alt="Ulysses" width="200">
  <br>Ulysses<br>
</h1>

<h3 align="center">A custom Mihomo kernel based on Meta branch.</h3>

<p align="center">
  <a href="https://goreportcard.com/report/github.com/berkisland/mihomorig">
    <img src="https://goreportcard.com/badge/github.com/berkisland/mihomorig?style=flat-square">
  </a>
  <img src="https://img.shields.io/github/go-mod/go-version/berkisland/mihomorig/ulysses?style=flat-square">
  <a href="https://github.com/berkisland/mihomorig/releases">
    <img src="https://img.shields.io/github/release/berkisland/mihomorig/all.svg?style=flat-square">
  </a>
  <a href="https://github.com/berkisland/mihomorig/tree/ulysses">
    <img src="https://img.shields.io/badge/branch-ulysses-00b4f0?style=flat-square">
  </a>
</p>

## Features

- Local HTTP/HTTPS/SOCKS server with authentication support
- VMess, VLESS, Shadowsocks, Trojan, Snell, TUIC, Hysteria protocol support
- Built-in DNS server that aims to minimize DNS pollution attack impact, supports DoH/DoT upstream and fake IP.
- Rules based off domains, GEOIP, IPCIDR or Process to forward packets to different nodes
- Remote groups allow users to implement powerful rules. Supports automatic fallback, load balancing or auto select node
  based off latency
- Remote providers, allowing users to get node lists remotely instead of hard-coding in config
- Netfilter TCP redirecting. Deploy Mihomo on your Internet gateway with `iptables`.
- Comprehensive HTTP RESTful API controller

## Dashboard

A web dashboard with first-class support for this project has been created; it can be checked out at [metacubexd](https://github.com/MetaCubeX/metacubexd).

## Configration example

Configuration example is located at [/docs/config.yaml](https://github.com/berkisland/mihomorig/blob/ulysses/docs/config.yaml).

## Docs

Documentation can be found in [mihomo Docs](https://wiki.metacubex.one/).

## For development

Requirements:
[Go 1.20 or newer](https://go.dev/dl/)

Build Ulysses:

```shell
git clone https://github.com/berkisland/mihomorig.git -b ulysses
cd mihomorig && go mod download
make all
```

Set go proxy if a connection to GitHub is not possible:

```shell
go env -w GOPROXY=https://goproxy.io,direct
```

Build with gvisor tun stack:

```shell
make all
```

Or build a specific platform:

```shell
make darwin-arm64
make linux-amd64-v3
make windows-amd64
```

Generate release packages:

```shell
make releases
```

### IPTABLES configuration

Work on Linux OS which supported `iptables`

```yaml
# Enable the TPROXY listener
tproxy-port: 9898

iptables:
  enable: true # default is false
  inbound-interface: eth0 # detect the inbound interface, default is 'lo'
```

## Debugging

Check [wiki](https://wiki.metacubex.one/api/#debug) to get an instruction on using debug
API.

## About

Ulysses is a custom fork based on the [MetaCubeX/mihomo](https://github.com/MetaCubeX/mihomo) Meta branch. This project is maintained at [berkisland/mihomorig](https://github.com/berkisland/mihomorig) and is designed for development and customization purposes.

## Credits

- [berkisland/mihomorig](https://github.com/berkisland/mihomorig) - Ulysses project repository
- [MetaCubeX/mihomo](https://github.com/MetaCubeX/mihomo) - The base project
- [Dreamacro/clash](https://github.com/Dreamacro/clash)
- [SagerNet/sing-box](https://github.com/SagerNet/sing-box)
- [riobard/go-shadowsocks2](https://github.com/riobard/go-shadowsocks2)
- [v2ray/v2ray-core](https://github.com/v2ray/v2ray-core)
- [WireGuard/wireguard-go](https://github.com/WireGuard/wireguard-go)
- [yaling888/clash-plus-pro](https://github.com/yaling888/clash)

## License

This software is released under the GPL-3.0 license.

**Ulysses is based on MetaCubeX/mihomo and maintains the same license terms.**