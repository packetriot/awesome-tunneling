The purpose of this list is to track and compare tunneling solutions. This is
primarily targeting toward developers and self-hosters who want to do things
like exposing a local webserver via a public address.

# The dream

I started this list because I'm looking for a simple tool/service that does the
following:

* Allows me to register a domain name and automatically points the records at
  the server running the tunnels.
* Automatically sets up and manages HTTPS certificates (apex and subdomains)
  for the domain.
* Provides a client tool that tunnels TCP connects through the server without
  requiring root on the client.
* Provides a simple interface to allow me to map X domain/subdomain to Y port
  on Z client, and proxy all connections to that domain.

So far I haven't found a tool that does all of this. In particular, while some
of them can do automatic certs through Lets's Encrypt, none of them integrate
the domain registration and DNS management.


# Open source

* [frp](https://github.com/fatedier/frp) [![frp github stars badge](https://img.shields.io/github/stars/fatedier/frp?style=flat)](https://github.com/fatedier/frp/stargazers) - Seems to be a pretty comprehensive open alternative to ngrok.
* [ngrok 1.0](https://github.com/inconshreveable/ngrok) [![ngrok 1.0 github stars badge](https://img.shields.io/github/stars/inconshreveable/ngrok?style=flat)](https://github.com/inconshreveable/ngrok/stargazers) - Original version of ngrok. No longer developed in favor of the commercial 2.0 version.
* [localtunnel](https://github.com/localtunnel) [![localtunnel github stars badge](https://img.shields.io/github/stars/localtunnel/localtunnel?style=flat)](https://github.com/localtunnel/localtunnel/stargazers) - Written in node. Popular suggestion.
* [inlets](https://github.com/inlets) [![inlets github stars badge](https://img.shields.io/github/stars/inlets/inlets?style=flat)](https://github.com/inlets/inlets/stargazers) - Open source ngrok alternative. Has pro option.
* [sshuttle](https://github.com/sshuttle/sshuttle) [![sshuttle github stars badge](https://img.shields.io/github/stars/sshuttle/sshuttle?style=flat)](https://github.com/sshuttle/sshuttle/stargazers) - Open source project originally from one of the founders of Tailscale. Server doesn't require root; client does. Explicitly designed to avoid TCP-over-TCP issues.
* [chisel](https://github.com/jpillora/chisel) [![chisel github stars badge](https://img.shields.io/github/stars/jpillora/chisel?style=flat)](https://github.com/jpillora/chisel/stargazers) - SSH under the hood, but still uses a custom client binary. Supports auto certs from LetsEncrypt.
* [expose](https://github.com/beyondcode/expose) [![expose github stars badge](https://img.shields.io/github/stars/beyondcode/expose?style=flat)](https://github.com/beyondcode/expose/stargazers) - ngrok alternative written in PHP.
* [teleconsole](https://www.teleconsole.com/) [![teleconsole github stars badge](https://img.shields.io/github/stars/gravitational/teleconsole?style=flat)](https://github.com/gravitational/teleconsole/stargazers) - SSH-based, but uses special client script. Focused on forwarding SSH console sessions, but can also forward ports.
* [go-http-tunnel](https://github.com/mmatczuk/go-http-tunnel) [![go-http-tunnel github stars badge](https://img.shields.io/github/stars/mmatczuk/go-http-tunnel?style=flat)](https://github.com/mmatczuk/go-http-tunnel/stargazers) - Uses a single HTTP/2 connection for muxing. Need to manually generate certs for server and clients.
* [sish](https://github.com/antoniomika/sish) [![sish github stars badge](https://img.shields.io/github/stars/antoniomika/sish?style=flat)](https://github.com/antoniomika/sish/stargazers) - Open source ngrok/serveo alternative. SSH-based but uses a custom server written in Go. Supports WebSocket tunneling.
* [PageKite](https://pagekite.net/) [![pagekite github stars badge](https://img.shields.io/github/stars/pagekite/PyPagekite?style=flat)](https://github.com/pagekite/PyPagekite/stargazers) - Comprehensive open source solution with hosted options. 
* [Crowbar](https://github.com/q3k/crowbar) [![crowbar github stars badge](https://img.shields.io/github/stars/q3k/crowbar?style=flat)](https://github.com/q3k/crowbar/stargazers) - Tunnels TCP connections over HTTP GET and POST requests. 
* [slt](https://github.com/inconshreveable/slt) [![slt github stars badge](https://img.shields.io/github/stars/inconshreveable/slt?style=flat)](https://github.com/inconshreveable/slt/stargazers) - Open source TLS proxy from the creator of ngrok. Supports SNI.
* [tunneller](https://github.com/skx/tunneller) [![tunneller github stars badge](https://img.shields.io/github/stars/skx/tunneller?style=flat)](https://github.com/skx/tunneller/stargazers) - Open source. Written in Go.
* [jprq](https://github.com/azimjohn/jprq) [![jprq github stars badge](https://img.shields.io/github/stars/azimjohn/jprq?style=flat)](https://github.com/azimjohn/jprq/stargazers) - Another home-grown Golang solution. Proxies over WebSockets. 
* [docker-tunnel](https://github.com/vitobotta/docker-tunnel) [![docker-tunnel github stars badge](https://img.shields.io/github/stars/vitobotta/docker-tunnel?style=flat)](https://github.com/vitobotta/docker-tunnel/stargazers) - Simple Docker-based nginx+SSH solution.
* [holepunch.io](https://holepunch.io) [![holepunch github stars badge](https://img.shields.io/github/stars/CypherpunkArmory/holepunch?style=flat)](https://github.com/CypherpunkArmory/holepunch/stargazers) - Has nice hosted solution. Uses SSH for muxing.
* [tnnlink](https://github.com/LiljebergXYZ/tnnlink) [![tnnlink github stars badge](https://img.shields.io/github/stars/LiljebergXYZ/tnnlink?style=flat)](https://github.com/LiljebergXYZ/tnnlink/stargazers) - SSH-based. Golang. Not maintained.
* [StaqLab Tunnel](https://tunnel.staqlab.com/) [![staqlab github stars badge](https://img.shields.io/github/stars/abhishekq61/tunnel-client?style=flat)](https://github.com/abhishekq61/tunnel-client/stargazers) - SSH-based. Client is open source. Server doesn't appear to be.
* [SirTunnel](https://github.com/anderspitman/SirTunnel) [![SirTunnel github stars badge](https://img.shields.io/github/stars/anderspitman/SirTunnel?style=flat)](https://github.com/anderspitman/SirTunnel/stargazers) - Minimal, self-hosted, 0-config alternative to ngrok. Similar to sish but leverages Caddy+OpenSSH rather than custom server code.
* [Telebit](https://telebit.cloud/) - Written in JS. [Code](https://git.coolaj86.com/coolaj86/telebit.js).

# Commerical/Closed source

* [ngrok 2.0](https://ngrok.com/) - Probably the gold standard and most popular. Closed source. Lots of features, including TLS and TCP tunnels. Doesn't require root to run client.
* [CloudFlare Argo Tunnel](https://www.cloudflare.com/products/argo-tunnel/) - $5/mo + $0.1/GB. Integrates with Argo smart routing. Client source code is [available](https://github.com/cloudflare/cloudflared).
* [serveo](https://serveo.net) - Mentioned quite a bit the last couple years, but appears to be down currently. Simply uses SSH for tunneling.
* [Tailscale](https://www.tailscale.com/) - Built on WireGuard. Closed source. Easy to use. Doesn't include an HTTPS proxy on the public side, but could be combined with nginx/Caddy/etc.
* [Packetriot](https://packetriot.com) - Comprehensive alternative to ngrok.  HTTP Inspector, Let's Encrypt integration, doesn't require root and Linux repos for apt, yum and dnf.  Enterprise licenses and self-hosted option.

# Blog posts

* [Roll your own Ngrok with Nginx, Letsencrypt, and SSH reverse tunnelling](https://jerrington.me/posts/2019-01-29-self-hosted-ngrok.html)
* [Poor man's ngrok with tcp proxy and ssh reverse tunnel](https://dev.to/k4ml/poor-man-ngrok-with-tcp-proxy-and-ssh-reverse-tunnel-1fm)
* [How I built Ngrok Alternative (jprq)](https://dev.to/azimjohn/how-i-built-ngrok-alternative-3n0g)


# Discussions

* [HN comment about needing Namecheap + CloudFlare + ngrok](https://news.ycombinator.com/item?id=24475946).
