---
layout: post
title: "Examples of JAP_LOCAL/REMOTE_SSH.json"
date: 2013-08-20 10:55
comments: true
categories: 
---
## Example 1: LOCAL/REMOTE_PROXY_SERVER
You can generate a public/private key file (KP.pem) with KP.bat.

JAP_LOCAL_SSH.json:
```
{
    "LOCAL_PROXY_SERVER":
    {
        "ADDRESS": "127.0.0.1",
        "PORT": 1080,
        "KEYS":
        [
            {
                "PUBLIC":
                {
                    "FILE": "KP.pem",
                    "PASSPHRASE": ""
                },
                "PRIVATE":
                {
                    "FILE": "KP.pem",
                    "PASSPHRASE": ""
                }
            }
        ]
    },
    "REMOTE_PROXY_SERVERS":
    [
        {
            "ADDRESS": "127.0.0.1",
            "PORT": 8022,
            "AUTHENTICATION":
            {
                "USERNAME": "1",
                "PASSWORD": "2"
            },
            "KEY":
            {
                "AUTHENTICATION":
                {
                    "FINGERPRINT": ""
                }
            }
        }
    ]
}
```

JAP_REMOTE_SSH.json:
```
"REMOTE_PROXY_SERVER":
{
    "ADDRESS": "127.0.0.1",
    "PORT": 8022,
    "AUTHENTICATION":
    [
        {
            "USERNAME": "1",
            "PASSWORD": "2"
        }
    ],
    "KEY":
    {
        "PUBLIC":
        {
            "FILE": "KP.pem",
            "PASSPHRASE": ""
        },
        "PRIVATE":
        {
            "FILE": "KP.pem",
            "PASSPHRASE": ""
        }
    }
}
```

## Example 2: LOCAL/REMOTE_PROXY_SERVER

JAP_LOCAL_SSH.json:
```
{
    "LOCAL_PROXY_SERVER":
    {
        "ADDRESS": "127.0.0.1",
        "PORT": 1080,
        "KEYS":
        [
            {
                "PUBLIC":
                {
                    "FILE": "KP.pem",
                    "PASSPHRASE": ""
                },
                "PRIVATE":
                {
                    "FILE": "KP.pem",
                    "PASSPHRASE": ""
                }
            }
        ]
    },
    "REMOTE_PROXY_SERVERS":
    [
        {
            "ADDRESS": "127.0.0.1",
            "PORT": 8022,
            "AUTHENTICATION":
            {
                "USERNAME": "1",
                "PASSWORD": ""
            },
            "KEY":
            {
                "AUTHENTICATION":
                {
                    "FINGERPRINT": ""
                }
            }
        }
    ]
}
```

JAP_REMOTE_SSH.json:
```
"REMOTE_PROXY_SERVER":
{
    "ADDRESS": "127.0.0.1",
    "PORT": 8022,
    "AUTHENTICATION":
    [
        {
            "USERNAME": "1",
            "PASSWORD": "",
            "KEYS":
            [
                {
                    "PUBLIC":
                    {
                        "FILE": "KP.pem",
                        "PASSPHRASE": ""
                    }
                }
            ]
        }
    ],
    "KEY":
    {
        "PUBLIC":
        {
            "FILE": "KP.pem",
            "PASSPHRASE": ""
        },
        "PRIVATE":
        {
            "FILE": "KP.pem",
            "PASSPHRASE": ""
        }
    }
}
```