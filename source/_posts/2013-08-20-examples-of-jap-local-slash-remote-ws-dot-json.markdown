---
layout: post
title: "Examples of JAP_LOCAL/REMOTE_WS.json"
date: 2013-08-20 10:55
comments: true
categories: 
---
## Example 1: LOCAL/REMOTE_PROXY_SERVER

JAP_LOCAL_WS.json:
```
"LOCAL_PROXY_SERVER":
{
    "ADDRESS": "127.0.0.1",
    "PORT": 1080
},
"REMOTE_PROXY_SERVERS":
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

JAP_REMOTE_WS.json:
```
"REMOTE_PROXY_SERVER":
{
    "TYPE": "HTTP",
    "ADDRESS": "127.0.0.1",
    "PORT": 8080,
    "AUTHENTICATION":
    [
        {
            "USERNAME": "1",
            "PASSWORD": "2"
        }
    ]
}
```

## Example 2: LOCAL/REMOTE_PROXY_SERVER
You can generate a certificate authentication file (CA.pem) with CA.bat and CA.ini and you can generate a certificate file (C.pem) and a certificate key file (CK.pem) with C.bat and C.ini.

JAP_LOCAL_WS.json:
```
"LOCAL_PROXY_SERVER":
{
    "ADDRESS": "127.0.0.1",
    "PORT": 1080
},
"REMOTE_PROXY_SERVERS":
[
    {
        "TYPE": "HTTPS",
        "ADDRESS": "127.0.0.1",
        "PORT": 8443,
        "AUTHENTICATION":
        {
            "USERNAME": "1",
            "PASSWORD": "2"
        },
        "CERTIFICATE":
        {
            "AUTHENTICATION":
            {
                "FILE": "CA.pem"
            }
        }
    }
]
```

JAP_REMOTE_WS.json:
```
"REMOTE_PROXY_SERVER":
{
    "TYPE": "HTTPS",
    "ADDRESS": "127.0.0.1",
    "PORT": 8443,
    "AUTHENTICATION":
    [
        {
            "USERNAME": "1",
            "PASSWORD": "2"
        }
    ],
    "CERTIFICATE":
    {
        "KEY":
        {
            "FILE": "CK.pem"
        },
        "FILE": "C.pem"
    }
}
```

## Example 3: LOCAL/REMOTE_PROXY_SERVER

JAP_LOCAL_WS.json:
```
"LOCAL_PROXY_SERVER":
{
    "ADDRESS": "127.0.0.1",
    "PORT": 1080
},
"REMOTE_PROXY_SERVERS":
[
    {
        "TYPE": "HTTPS",
        "ADDRESS": "",
        "PORT": 443,
        "AUTHENTICATION":
        {
            "USERNAME": "1",
            "PASSWORD": "2"
        },
        "CERTIFICATE":
        {
            "AUTHENTICATION":
            {
                "FILE": "CA_DEFAULT.pem"
            }
        }
    }
]
```

JAP_REMOTE_WS.json:
```
"REMOTE_PROXY_SERVER":
{
    "TYPE": "HTTPS",
    "AUTHENTICATION":
    [
        {
            "USERNAME": "1",
            "PASSWORD": "2"
        }
    ]
}
```