---
layout: default
title: Curl
nav_order: 1
comments: true
parent: Web
---

## Using Curl to call POST request

```bash
#!/bin/bash
curl --cookie "SESSION=ZTVhZjYwZjMtODZkNS00ODE2LTk4NjUtOTc3NmZlZTJmYzhh" -v localhost:8080/webapi/apps/monitor/quota -d '{"event":"test"}' -H "X-CSRF-TOKEN: 6c6a37e4-685c-4767-84e3-b3bb74ee9b00"
```