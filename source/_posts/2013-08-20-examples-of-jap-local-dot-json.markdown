---
layout: post
title: "Examples of JAP_LOCAL.json"
date: 2013-08-20 10:55
comments: true
categories: 
---
## Example 1: LOGGER
You can set LOGGER.LEVEL to DEBUG, INFO, WARNING, ERROR or CRITICAL.

JAP_LOCAL.json:
```
"LOGGER":
{
    "LEVEL": "DEBUG"
}
```

## Example 2: DNS_RESOLVER

JAP_LOCAL.json:
```
"DNS_RESOLVER":
{
    "HOSTS":
    {
        "FILE": "H.txt"
    },
    "SERVERS": 
    [
        {
            "ADDRESS": "8.8.8.8",
            "PORT": 53
        },
        {
            "ADDRESS": "8.8.8.4",
            "PORT": 53
        }
    ]
}
```

H.txt:
```
127.0.0.1       localhost
```

## Example 3: PROXY_SERVERS
You can set PROXY_SERVERS.TYPE to HTTP or SOCKS5.

JAP_LOCAL.json:
```
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
```

## Example 4: PROXY_SERVERS

JAP_LOCAL.json:
```
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
        "PORT": 2080
    },
    {
        "TYPE": "SOCKS5",
        "ADDRESS": "127.0.0.1",
        "PORT": 3080
    }
]
```

## Example 5: LOCAL_PROXY_SERVER

JAP_LOCAL.json:
```
"LOCAL_PROXY_SERVER":
{
    "ADDRESS": "127.0.0.1",
    "PORT": 1080
}
```