---
layout: post
title:  "[Service] ngrok & localtunnel"
date:   2021-12-07 23:20:00 +0900
categories: [service]
---

#### ngrok
[https://ngrok.com](https://ngrok.com)
```bash
./ngrok http 80
````

#### localtunnel
[https://github.com/localtunnel/localtunnel](https://github.com/localtunnel/localtunnel)
> Install Node.JS & NPM 
```bash
npm install -g localtunnel
lt --port 4000 --subdomain joyplug
```
> joyplug.loca.lt 
