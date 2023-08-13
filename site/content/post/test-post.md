---
title: Test Post
date: 2023-08-13T13:03:04.967Z
description: Intro
image: img/blog-chemex.jpg
---
# DNG Test

\

| **Type** | **Name** | **Value** | **TTL(sec)** | **Purpose** |
|----|----|----|----|----|
| A | portal | 148.251.12.183 | 300 | Base DNG record |
| CNAME | relay | portal.techhosting.lol | 300 | RDP Relay for authentication |
| NS | rdp | portal.techhosting.lol | 300 | Subdomain delegation |


Current records in Namecheap

 ![](/api/attachments.redirect?id=6e982fab-1ab7-4299-832e-ba8afa836388)


# Troubleshooting


 ![](/api/attachments.redirect?id=699b5795-5705-42eb-bd8e-e9f6a727e181)


\
When trying to access RDP using the subdomain


 ![](/api/attachments.redirect?id=dc370d17-b2c8-41d3-89bd-7737d29b78ca)


NSLOOKUP of a record that uses NS to portal.techhosting.lol


 ![](/api/attachments.redirect?id=82356456-fb99-4723-9959-71ac9e9b11aa)

## Logs from client machine

100.64.1.2:53527 | remote ip:port -> 100.114.218.74:445(microsoft-ds)

2023/08/07 20:46:47.559097 dctun.go:732: [tun_dispatch] New Connection: error getting session id for SYN: Access is denied.

2023/08/07 20:46:47.559602 dctun.go:747: [tun_dispatch] NAT 100.64.1.2:53527 -> 100.114.218.74:445 <==> 100.64.1.3:28201 -> 100.64.1.2:53091 

2023/08/07 20:46:47.559602 dctun.go:1126: [tun_main] 100.64.1.2:53527 -> 100.114.218.74:445: SYN_SENT[DN SYN ACK] => ESTABLISHED

2023/08/07 20:47:04.049229 dctun.go:1126: [tun_main] 100.64.1.2:53471 -> 100.114.218.74:389: ESTABLISHED[DN ACK RST] => TIME_WAIT

2023/08/07 20:47:05.102970 dctun.go:1126: [tun_main] 100.64.1.2:53527 -> 100.114.218.74:445: ESTABLISHED[DN ACK RST] => TIME_WAIT

2023/08/07 20:47:34.055091 dctun.go:752: [tun_dispatch] 100.64.1.2:53471 -> 100.114.218.74:389: TIME_WAIT completed. Deleting

2023/08/07 20:47:35.106860 dctun.go:752: [tun_dispatch] 100.64.1.2:53527 -> 100.114.218.74:445: TIME_WAIT completed. Deleting


## Logs from docker stack

[Dng.log 2016828](/api/attachments.redirect?id=621e27a3-39ed-4370-a102-987c678a7486)


