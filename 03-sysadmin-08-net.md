# Домашнее задание к занятию «Компьютерные сети. Лекция 3»

## 1. Подключитесь к публичному маршрутизатору в интернет. Найдите маршрут к вашему публичному IP.

 ```
telnet route-views.routeviews.org
Username: rviews
show ip route x.x.x.x/32
show bgp x.x.x.x/32
```

## Решение 1:

```bash
route-views>show ip route *.*.125.105
Routing entry for *.*.0.0/16
  Known via "bgp 6447", distance 20, metric 0
  Tag 852, type external
  Last update from 154.11.12.212 7w0d ago
  Routing Descriptor Blocks:
  * 154.11.12.212, from 154.11.12.212, 7w0d ago
      Route metric is 0, traffic share count is 1
      AS Hops 1
      Route tag 852
      MPLS label: none
       ```
       
 ---bash
 route-views>show bgp *.*.125.105
BGP routing table entry for *.*.0.0/16, version 2559085809
Paths: (20 available, best #18, table default)
  Not advertised to any peer
  Refresh Epoch 1
  8283 57866 2914 852
    94.142.247.3 from 94.142.247.3 (94.142.247.3)
      Origin IGP, metric 0, localpref 100, valid, external
      Community: 2914:410 2914:1003 2914:2000 2914:3000 8283:15 8283:102 57866:100 65100:2914 65103:1 65104:31
      unknown transitive attribute: flag 0xE0 type 0x20 length 0x48
        value 0000 205B 0000 0005 0000 0002 0000 205B
              0000 0006 0000 000F 0000 E20A 0000 0064
              0000 0B62 0000 E20A 0000 0065 0000 0064
              0000 E20A 0000 0067 0000 0001 0000 E20A
              0000 0068 0000 001F
      path 7FE148B42A40 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3267 1299 852
    194.85.40.15 from 194.85.40.15 (185.141.126.1)
      Origin IGP, metric 0, localpref 100, valid, external
      path 7FE10AF7DCD0 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  7018 3356 852
    12.0.1.63 from 12.0.1.63 (12.0.1.63)
      Origin IGP, localpref 100, valid, external
      Community: 7018:5000 7018:37232
      path 7FE028AF0408 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  20912 3257 852
    212.66.96.126 from 212.66.96.126 (212.66.96.126)
      Origin IGP, localpref 100, valid, external
      Community: 3257:1999 3257:4000 3257:8769 3257:50002 3257:50120 3257:51300 3257:51301 20912:65004
      path 7FE0D8DA7810 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  49788 174 852
    91.218.184.60 from 91.218.184.60 (91.218.184.60)
      Origin IGP, metric 0, localpref 100, valid, external
      Community: 174:21001 174:22013
      Extended Community: 0x43:100:0
      path 7FE15CF68F28 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3333 1257 1299 852
    193.0.0.56 from 193.0.0.56 (193.0.0.56)
      Origin IGP, localpref 100, valid, external
      Community: 1257:50 1257:51 1257:2000 1257:3528 1257:4103
      path 7FE109DB4EF8 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  6939 852
    64.71.137.241 from 64.71.137.241 (216.218.253.53)
      Origin IGP, localpref 100, valid, external
      path 7FE00B4F9930 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3257 852
    89.149.178.10 from 89.149.178.10 (213.200.83.26)
      Origin IGP, metric 10, localpref 100, valid, external
      Community: 3257:1999 3257:4000 3257:8769 3257:50002 3257:50120 3257:51300 3257:51301
      path 7FE04FCC61E0 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  19214 3257 852
    208.74.64.40 from 208.74.64.40 (208.74.64.40)
      Origin IGP, localpref 100, valid, external
      Community: 3257:1999 3257:4000 3257:8769 3257:50002 3257:50120 3257:51300 3257:51301
      path 7FE040897860 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3561 209 3356 852
    206.24.210.80 from 206.24.210.80 (206.24.210.80)
      Origin IGP, localpref 100, valid, external
      path 7FE0BB381CF0 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3549 3356 852
    208.51.134.254 from 208.51.134.254 (67.16.168.191)
      Origin IGP, metric 0, localpref 100, valid, external
      Community: 3356:3 3356:22 3356:100 3356:123 3356:575 3356:901 3356:2042 3549:2581 3549:30840
      path 7FE02D80C200 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  4901 6079 3257 852
    162.250.137.254 from 162.250.137.254 (162.250.137.254)
      Origin IGP, localpref 100, valid, external
      Community: 65000:10100 65000:10300 65000:10400
      path 7FE1088C8F10 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  101 852
    209.124.176.223 from 209.124.176.223 (209.124.176.223)
      Origin IGP, localpref 100, valid, external
      Community: 101:20300 101:22100
      path 7FE0E4D4D550 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3356 852
    4.68.4.46 from 4.68.4.46 (4.69.184.201)
      Origin IGP, metric 0, localpref 100, valid, external
      Community: 3356:3 3356:22 3356:100 3356:123 3356:575 3356:901 3356:2042
      path 7FE03339E388 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  57866 2914 852
    37.139.139.17 from 37.139.139.17 (37.139.139.17)
      Origin IGP, metric 0, localpref 100, valid, external
      Community: 2914:410 2914:1003 2914:2000 2914:3000 57866:100 65100:2914 65103:1 65104:31
      unknown transitive attribute: flag 0xE0 type 0x20 length 0x30
        value 0000 E20A 0000 0064 0000 0B62 0000 E20A
              0000 0065 0000 0064 0000 E20A 0000 0067
              0000 0001 0000 E20A 0000 0068 0000 001F

      path 7FE0A31BCA18 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 2
  2497 852
    202.232.0.2 from 202.232.0.2 (58.138.96.254)
      Origin IGP, localpref 100, valid, external
      path 7FE047BC96F8 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  20130 6939 852
    140.192.8.16 from 140.192.8.16 (140.192.8.16)
      Origin IGP, localpref 100, valid, external
      path 7FE150F03D98 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  852
    154.11.12.212 from 154.11.12.212 (96.1.209.43)
      Origin IGP, metric 0, localpref 100, valid, external, best
      path 7FE05589A3B8 RPKI State valid
      rx pathid: 0, tx pathid: 0x0
  Refresh Epoch 1
  1351 11164 852
    132.198.255.253 from 132.198.255.253 (132.198.255.253)
      Origin IGP, localpref 100, valid, external
      path 7FE107A60210 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3303 852
    217.192.89.50 from 217.192.89.50 (138.187.128.158)
      Origin IGP, localpref 100, valid, external
      Community: 3303:1004 3303:1005 3303:1030 3303:3062
      path 7FE149608B30 RPKI State valid
      rx pathid: 0, tx pathid: 0
```

## 2. Создайте dummy-интерфейс в Ubuntu. Добавьте несколько статических маршрутов. Проверьте таблицу маршрутизации.


## 2.Решение:
```bash
vagrant@vagrant:~$ cat /etc/network/interfaces
# interfaces(5) file used by ifup(8) and ifdown(8)
# Include files from /etc/network/interfaces.d:
auto dummy0
iface dummy0 inet static
address 10.2.2.2/32
pre-up ip link add dummy0 type dummy
post-down ip link del dummy0

auto dummy1
iface dummy1 inet static
address 10.2.2.3/32
pre-up ip link add dummy1 type dummy
post-down ip link del dummy1


source-directory /etc/network/interfaces.d
vagrant@vagrant:~$

vagrant@vagrant:~$ lsmod | grep dummy
dummy                  16384  0
vagrant@vagrant:~$ ifconfig -a | grep dummy
dummy0: flags=195<UP,BROADCAST,RUNNING,NOARP>  mtu 1500
dummy1: flags=195<UP,BROADCAST,RUNNING,NOARP>  mtu 1500
vagrant@vagrant:~$
vagrant@vagrant:~$
vagrant@vagrant:~$ netstat -rn
Kernel IP routing table
Destination     Gateway         Genmask         Flags   MSS Window  irtt Iface
0.0.0.0         10.0.2.2        0.0.0.0         UG        0 0          0 eth0
10.0.2.0        0.0.0.0         255.255.255.0   U         0 0          0 eth0
10.0.2.2        0.0.0.0         255.255.255.255 UH        0 0          0 eth0
vagrant@vagrant:~$
vagrant@vagrant:~$
vagrant@vagrant:~$ ip ro sh
default via 10.0.2.2 dev eth0 proto dhcp src 10.0.2.15 metric 100
10.0.2.0/24 dev eth0 proto kernel scope link src 10.0.2.15
10.0.2.2 dev eth0 proto dhcp scope link src 10.0.2.15 metric 100
vagrant@vagrant:~$
```

## 3. Проверьте открытые TCP-порты в Ubuntu. Какие протоколы и приложения используют эти порты? Приведите несколько примеров.

## 3. Решение:

Открытые порты TCP

```bash
vagrant@vagrant:~$ sudo ss -tlpn
State      Recv-Q     Send-Q         Local Address:Port           Peer Address:Port     Process
LISTEN     0          128                  0.0.0.0:22                  0.0.0.0:*         users:(("sshd",pid=1020,fd=3))
LISTEN     0          4096                 0.0.0.0:111                 0.0.0.0:*         users:(("rpcbind",pid=572,fd=4),("systemd",pid=1,fd=115))
LISTEN     0          511                  0.0.0.0:80                  0.0.0.0:*         users:(("nginx",pid=838,fd=6),("nginx",pid=837,fd=6))
LISTEN     0          4096           127.0.0.53%lo:53                  0.0.0.0:*         users:(("systemd-resolve",pid=575,fd=13))
LISTEN     0          128                     [::]:22                     [::]:*         users:(("sshd",pid=1020,fd=4))
LISTEN     0          4096                    [::]:111                    [::]:*         users:(("rpcbind",pid=572,fd=6),("systemd",pid=1,fd=117))
LISTEN     0          511                     [::]:80                     [::]:*         users:(("nginx",pid=838,fd=7),("nginx",pid=837,fd=7))
vagrant@vagrant:~$
```

Открытые порты TCP через NMAP

```bash
vagrant@vagrant:~$ nmap localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-02-25 00:37 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.000034s latency).
Other addresses for localhost (not scanned): ::1
Not shown: 997 closed ports
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
111/tcp open  rpcbind
```

Просмотр служб через Lsof

```bash
vagrant@vagrant:~$ sudo lsof -i :22,80,111 -P
COMMAND  PID     USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
systemd    1     root  115u  IPv4  14662      0t0  TCP *:111 (LISTEN)
systemd    1     root  116u  IPv4  14665      0t0  UDP *:111
systemd    1     root  117u  IPv6  14670      0t0  TCP *:111 (LISTEN)
systemd    1     root  118u  IPv6  14675      0t0  UDP *:111
rpcbind  572     _rpc    4u  IPv4  14662      0t0  TCP *:111 (LISTEN)
rpcbind  572     _rpc    5u  IPv4  14665      0t0  UDP *:111
rpcbind  572     _rpc    6u  IPv6  14670      0t0  TCP *:111 (LISTEN)
rpcbind  572     _rpc    7u  IPv6  14675      0t0  UDP *:111
nginx    837     root    6u  IPv4  22295      0t0  TCP *:80 (LISTEN)
nginx    837     root    7u  IPv6  22296      0t0  TCP *:80 (LISTEN)
nginx    838 www-data    6u  IPv4  22295      0t0  TCP *:80 (LISTEN)
nginx    838 www-data    7u  IPv6  22296      0t0  TCP *:80 (LISTEN)
sshd    1020     root    3u  IPv4  24617      0t0  TCP *:22 (LISTEN)
sshd    1020     root    4u  IPv6  24619      0t0  TCP *:22 (LISTEN)
sshd    1131     root    4u  IPv4  26970      0t0  TCP vagrant:22->_gateway:13796 (ESTABLISHED)
sshd    1133     root    4u  IPv4  27029      0t0  TCP vagrant:22->_gateway:13797 (ESTABLISHED)
sshd    1191  vagrant    4u  IPv4  26970      0t0  TCP vagrant:22->_gateway:13796 (ESTABLISHED)
sshd    1205  vagrant    4u  IPv4  27029      0t0  TCP vagrant:22->_gateway:13797 (ESTABLISHED)
vagrant@vagrant:~$
```

## 4. Проверьте используемые UDP-сокеты в Ubuntu. Какие протоколы и приложения используют эти порты?

## 4. Решение:

Открытые порты UDP через SS

```bash
vagrant@vagrant:~$ sudo ss -ulpn
State      Recv-Q     Send-Q          Local Address:Port          Peer Address:Port     Process
UNCONN     0          0              10.0.2.15%eth0:68                 0.0.0.0:*         users:(("systemd-network",pid=390,fd=19))
UNCONN     0          0                     0.0.0.0:111                0.0.0.0:*         users:(("rpcbind",pid=572,fd=5),("systemd",pid=1,fd=116))
UNCONN     0          0               127.0.0.53%lo:53                 0.0.0.0:*         users:(("systemd-resolve",pid=575,fd=12))
UNCONN     0          0                        [::]:111                   [::]:*         users:(("rpcbind",pid=572,fd=7),("systemd",pid=1,fd=118))
vagrant@vagrant:~$
```



## 5. Используя diagrams.net, создайте L3-диаграмму вашей домашней сети или любой другой сети, с которой вы работали.

## 5 Решение:


Создал схему домашнего интернета

https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1&title=shema.png#R7VvbUuM4EP2aPG7KkuNLHocEhqlitrILxew%2BpZRYOBrsyCsrkOzXb8v3Sy6exCawhAewWi1Z7j4%2B3S2Lnj7y118FCRbfuUO9HtacdU8f9zBGmqHBHyXZxBLD0mOBK5iTKOWCe%2FYvTUcm0hVzaFhSlJx7kgVl4Zwvl3QuSzIiBH8tqz1xr3zXgLi0JrifE68u%2FcEcuYilNrZy%2BS1l7iK9MzKHcY9PUuXkScIFcfhrQaRf9%2FSR4FzGV%2F56RD1lvNQu8bibHb3ZwgRdyiYDHP6AH%2B9nz7NgdctG%2F9yb17%2F%2F8Vs6TSg36RNTBwyQNLmQC%2B7yJfGuc%2BmV4KulQ9W0GrRynTvOAxAiEP6kUm4Sb5KV5CBaSN9LekNJhPyivAOCuUfCkM1T8Q3zUrV4aWo9Ox85XT5fiTnd85wpdIhwqdynhzLPAKQp96kUGxgoqEckeykvhCTYcjO93PxwkXjgF7yRzPtCvFVyp5p3ClbkK%2BmxJR1lyFfeeALzjbjHRaSuj6KfyLaCP9NCj2nb6EqHHlcQh4FB074lX9KCeMwEzM74MuoSCtTJZOn7gJVkQQK1Qn%2FtKh7oL6l85eI57M89vnLUunh%2BB7j7U%2FST%2BfiFCknX%2B71cd0oyIKWYhGEsq2%2FEgtf8hUVaorQovKzpwNb9iGt%2BvCOBhJcDa%2BPb0aTm1IpxNM00I6cpszDgoi8ec5X91RS59I7MqDfhIUu8M%2BNSch8UvErHHAxJYe4rksyTCT4amrzYjK3AZjAo48ZIIXIQNkZHsNG1GjLegIzBXGLzlxoP703S%2FDuZLmqM16XWptiaUMHg4RWYIuHbM7vekNmtcxK7fiGED0AIVpkQTNw4kHTFCIMabiaCu2AwMOUFOqdB5wUKCz4NBP8Z27MVDJlmGUNYa5yN6F2ByKiB6DufMcDLBUGnIciPzdgOcCrkMxjWs5HBFtRYnSUjn6QyNBvmDwifmEAkQyecwRJzv6MKYZiVoiReWDIq9ynYiGwKaoFSCPfcB5fvY1c2Cw6oH9LH1l59uIgXnOMxM%2BHxEDUvxPYBiW0Lrxl1XrO7qs2tGmgemZArogZORhfMHJ9ORVacBvOWsnHTKOEGWVvKc7QtInaFnPRmBeh8Jb5iG%2FBMyC%2B8czKGXDBnQJyWiGeQ1W8JhPTmW4OdgWjLlu4bpFUt5kuo8VZ6KwnTr%2BY5eFgON2hg7k1c0In6aTzrNNHB5jlAU9gYzJrRxmDfwtbH2BxEuCFY9XNgVbf3YumgPtL07rGH6h%2Blvt1DjNPUt16%2Fh00P7Ho1E3Dlqis0xH1k2n0Fmlrn0aExC367omMcO%2F%2B%2FodGPrN1KYMSVDx928y2qzqLi4LwEV6Y3G5ZzBL01563DsdNsg48OBq9B1aE7NhsaR8FsopiZT961OBBtDz%2Fgm0Rn%2BxzgPVcwbR2UVnWrqfpZvqUdsOoWlY72Y6m6rop%2BR1gafiYsvQUTnlby41ry8yekC0D5WNuS3qS5D9L62Ggz%2Ffn0OwOvMNyjYThdrGYtZUGV13vr%2FtK2JMju6osLqp8SuPfhDQTRw2MDMCUECNfGVc8YK7eHQezSJ7ZW%2FFB0ew0S2flE5X%2BHhIuMUZgfHZJM%2F46Z78IDemwGv4nnMepMpfIOA%2Fa9mXM%2FUG%2FIlCyVWPgMmEh1fJtMHx774Yvbq50G0%2BAnglcLfoWQ37fLxG2ifnoqs%2BDc4bCP695FGijjrjxsfRJ2b%2FxR7Tx19440eGfdvV%2B%2Fo7r7LFllcc%2BnfBosPxz2zrd8mmLvLNuTulaGkpEUD91C6SxJ5c5zhX1teO7yWmvD9%2FWKoeJcHR9ZXtdKlerniJbK69p9DpTX5lDfp99RSfSuTsWiY6BL10wW5oJWNhVc5zOpxqbQ%2BEBsapz4Rp2WV9VPgmRlGj5QpuEaui5F2bspyvQOizJo5v98FZNV%2Fi9s%2BvV%2F

