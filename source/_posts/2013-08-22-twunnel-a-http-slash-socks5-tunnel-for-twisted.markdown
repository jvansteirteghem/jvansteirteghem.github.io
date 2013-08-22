---
layout: post
title: "Twunnel: a HTTP/SOCKS5 tunnel for Twisted"
date: 2013-08-22 09:06
comments: true
categories: 
keywords: "twunnel, http, socks5, tunnel, twisted"
description: "Twunnel: a HTTP/SOCKS5 tunnel for Twisted"
---
Twunnel is a HTTP/SOCKS5 tunnel for Twisted.

Twunnel supports:

* HTTP
* HTTP + Basic authentication
* SOCKS5

The Twunnel project page: https://github.com/jvansteirteghem/twunnel

## Examples

```
import twunnel

protocolFactory = ..

configuration = \
{
}

tunnel = twunnel.Tunnel(configuration)
tunnel.connect("www.google.com", 80, protocolFactory)
```

```
from twisted.internet import ssl
import twunnel

protocolFactory = ..

configuration = \
{
}

contextFactory = ssl.ClientContextFactory()

tunnel = twunnel.Tunnel(configuration)
tunnel.connect("www.google.com", 443, protocolFactory, contextFactory)
```

```
import twunnel

protocolFactory = ..

configuration = \
{
    "PROXY_SERVERS":
    [
        {
            "TYPE": "HTTP",
            "ADDRESS": "127.0.0.1",
            "PORT": 8080,
            "AUTHENTICATION":
            {
                "USERNAME": "1",
                "PASSWORD": "2"
            }
        }
    ]
}

tunnel = twunnel.Tunnel(configuration)
tunnel.connect("www.google.com", 80, protocolFactory)
```

```
import twunnel

protocolFactory = ..

configuration = \
{
    "PROXY_SERVERS":
    [
        {
            "TYPE": "SOCKS5",
            "ADDRESS": "127.0.0.1",
            "PORT": 1080
        }
    ]
}

tunnel = twunnel.Tunnel(configuration)
tunnel.connect("www.google.com", 80, protocolFactory)
```

```
import twunnel

protocolFactory = ..

configuration = \
{
    "PROXY_SERVERS":
    [
        {
            "TYPE": "HTTP",
            "ADDRESS": "127.0.0.1",
            "PORT": 8080,
            "AUTHENTICATION":
            {
                "USERNAME": "1",
                "PASSWORD": "2"
            }
        },
        {
            "TYPE": "SOCKS5",
            "ADDRESS": "127.0.0.1",
            "PORT": 1080
        }
    ]
}

tunnel = twunnel.Tunnel(configuration)
tunnel.connect("www.google.com", 80, protocolFactory)
```