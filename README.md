# Домашнее задание к занятию "3.6. Компьютерные сети, лекция 1"

### 1. Работа c HTTP через телнет.
- Подключитесь утилитой телнет к сайту stackoverflow.com
`telnet stackoverflow.com 80`
- Отправьте HTTP запрос
```bash
GET /questions HTTP/1.0
HOST: stackoverflow.com
[press enter]
[press enter]
```
*В ответе укажите полученный HTTP код, что он означает?*

## 1. Решение:
agrant@vagrant:~$ telnet stackoverflow.com 80
Trying 151.101.193.69...
Connected to stackoverflow.com.
Escape character is '^]'.
GET /questions HTTP/1.0
HOST: stackoverflow.com

`HTTP/1.1 301 Moved Permanently`
cache-control: no-cache, no-store, must-revalidate
`location: https://stackoverflow.com/questions`
x-request-guid: f93c26d6-c46b-4b25-85b0-78d56ab1acc6
feature-policy: microphone 'none'; speaker 'none'
content-security-policy: upgrade-insecure-requests; frame-ancestors 'self' https://stackexchange.com
Accept-Ranges: bytes
Date: Wed, 23 Feb 2022 16:32:56 GMT
Via: 1.1 varnish
Connection: close
X-Served-By: cache-bma1646-BMA
X-Cache: MISS
X-Cache-Hits: 0
X-Timer: S1645633977.604817,VS0,VE101
Vary: Fastly-SSL
X-DNS-Prefetch-Control: off
Set-Cookie: prov=00d8c188-d042-2884-9f00-aa23a5919e6f; domain=.stackoverflow.com; expires=Fri, 01-Jan-2055 00:00:00 GMT; path=/; HttpOnly

Connection closed by foreign host.


HTTP код 301 Moved Permanently (перемещенно навсегда)

Код из 300 серии относится к перенаправлению
запрошенный документ был окончательно перенесен на новый URI, указанный в поле Location заголовка. Некоторые клиенты некорректно ведут себя при обработке данного кода. Появился в HTTP/1.0.
В нашем случае как я понял, location: https://stackoverflow.com/questions

### 2. Повторите задание 1 в браузере, используя консоль разработчика F12.
- откройте вкладку `Network`
- отправьте запрос http://stackoverflow.com
- найдите первый ответ HTTP сервера, откройте вкладку `Headers`
- укажите в ответе полученный HTTP код
- проверьте время загрузки страницы, какой запрос обрабатывался дольше всего?
- приложите скриншот консоли браузера в ответ.

## 2. Решение:
- укажите в ответе полученный HTTP код - *код 200* 

![screen_2_03-sysadmin-06-net ](https://user-images.githubusercontent.com/69511724/219902813-e1dc784e-1989-49ef-854d-896ae05f3ceb.png)

- проверьте время загрузки страницы, какой запрос обрабатывался дольше всего?

*Первый запрос дольше всего обрабатывался 186 мс, загружался тип документ размер 51,6 Кб*

![screen_2_1_03-sysadmin-06-net ](https://user-images.githubusercontent.com/69511724/219902950-621eb8db-522e-40f6-8e00-eec8065cd1b7.png)


### 3. Какой IP адрес у вас в интернете?

## 3. Решение:

*Адрес свой скрыл в целях безопасности*

![screen_3_03-sysadmin-06-net ](https://user-images.githubusercontent.com/69511724/219972129-ed5067f0-c339-4c25-916c-72a5d6ac695f.png)


### 4. Какому провайдеру принадлежит ваш IP адрес? Какой автономной системе AS? Воспользуйтесь утилитой `whois`

## 4. Решение:

Какому провайдеру принадлежит ваш IP адрес?  -  `TELUS Communications Inc.`

Какой автономной системе AS?  - `AS852`

```bash
vagrant@vagrant:~$ whois 104.*.*.*

# start

NetRange:       104.*.0.0 - 104.*.255.255
CIDR:           104.*.0.0/16
NetName:        TELUS
NetHandle:      NET-104-*-0-0-1
Parent:         NET104 (NET-104-0-0-0-0)
NetType:        Direct Allocation
`OriginAS:       AS852
Organization:   TELUS Communications Inc. (TACE)`
RegDate:        2014-09-22
Updated:        2014-09-22
Ref:            https://rdap.arin.net/registry/ip/104.205.0.0



`OrgName:        TELUS Communications Inc.`
OrgId:          TACE
Address:        10 - 3777 Kingsway
City:           Burnaby
StateProv:      BC
PostalCode:     V5H-3Z7
Country:        CA
RegDate:
Updated:        2020-10-09
Ref:            https://rdap.arin.net/registry/entity/TACE


OrgAbuseHandle: AAT-ARIN
OrgAbuseName:   Abuse at TELUS
OrgAbusePhone:  +1-877-945-8220
OrgAbuseEmail:  abuse@telus.com
OrgAbuseRef:    https://rdap.arin.net/registry/entity/AAT-ARIN

OrgTechHandle: TBOTP-ARIN
OrgTechName:   TELUS BC ORG TECH POC
OrgTechPhone:  +1-877-310-8324
OrgTechEmail:  IPadmin@telus.com
OrgTechRef:    https://rdap.arin.net/registry/entity/TBOTP-ARIN

# end


# start

NetRange:       104.*.*.0 - 104.*.*.255
CIDR:           104.*.*.0/22
`NetName:        TELUS-DSL-CLGRAB15`
NetHandle:      NET-104-*-*-0-1
Parent:         TELUS (NET-104-*-*-0-1)
NetType:        Reassigned
OriginAS:       AS852
Customer:       TELUS-DSL-CLGRAB15 (C08019593)
RegDate:        2021-09-07
Updated:        2021-09-07
Ref:            https://rdap.arin.net/registry/ip/104.*.*.0


CustName:       TELUS-DSL-CLGRAB15
Address:        2631 106 AVENUE SW
City:           Calgary
StateProv:      AB
PostalCode:     T2W 4H7
Country:        CA
RegDate:        2021-09-07
Updated:        2021-09-07
Ref:            https://rdap.arin.net/registry/entity/C08019593

OrgAbuseHandle: AAT-ARIN
OrgAbuseName:   Abuse at TELUS
OrgAbusePhone:  +1-877-945-8220
OrgAbuseEmail:  abuse@telus.com
OrgAbuseRef:    https://rdap.arin.net/registry/entity/AAT-ARIN

OrgTechHandle: TBOTP-ARIN
OrgTechName:   TELUS BC ORG TECH POC
OrgTechPhone:  +1-877-310-8324
OrgTechEmail:  IPadmin@telus.com
OrgTechRef:    https://rdap.arin.net/registry/entity/TBOTP-ARIN

# end
```

### 5. Через какие сети проходит пакет, отправленный с вашего компьютера на адрес 8.8.8.8? Через какие AS? Воспользуйтесь утилитой `traceroute`

№№ 5. Решение:

У меня так получается
```bash
vagrant@vagrant:~$ traceroute -An 8.8.8.8
traceroute to 8.8.8.8 (8.8.8.8), 30 hops max, 60 byte packets
 1  10.0.2.2 [*]  0.201 ms  0.158 ms  0.150 ms
 2  * * *
 3  * * *
 4  * * *
 5  * * *
 6  * * *
 7  * * *
 8  * * *
 9  * * *
10  * * *
11  * * *
12  * * *
13  * * *
14  * * *
15  * * *
16  * * *
17  * * *
18  * * *
19  * * *
20  * * *
21  * * *
22  * * *
23  * * *
24  * * *
25  * * *
26  * * *
27  * * *
28  * * *
29  * * *
30  * * *
vagrant@vagrant:~$ 
```

### 6. Повторите задание 5 в утилите `mtr`. На каком участке наибольшая задержка - delay?

## 6. Решение:

```bash
vagrant@vagrant:~$ mtr -zn 8.8.8.8
                                                                     My traceroute  [v0.93]
vagrant (10.0.2.15)                                                                                                                     2023-02-19T20:18:55+0000
Keys:  Help   Display mode   Restart statistics   Order of fields   quit
                                                                                                                        Packets               Pings
 Host                                                                                                                 Loss%   Snt   Last   Avg  Best  Wrst StDev
 1. AS???    10.0.2.2                                                                                                  0.0%    10    0.4   0.4   0.3   0.5   0.1
 2. AS???    192.168.1.254                                                                                             0.0%    10    2.9   2.9   2.4   4.5   0.6
 3. AS???    10.145.144.1                                                                                              0.0%    10    8.5   7.4   6.7   8.8   0.7
 4. AS852    154.11.12.217                                                                                             0.0%    10   23.4  25.1  22.8  39.5   5.1
 `5. AS15169  74.125.50.110                                                                                             0.0%    10   25.8  27.2  24.6  31.5   2.4`
 6. AS15169  142.251.229.139                                                                                           0.0%    10   23.4  23.7  23.0  24.5   0.5
 7. AS15169  142.251.55.203                                                                                            0.0%    10   23.5  23.6  22.7  25.3   0.8
 8. AS15169  8.8.8.8                                                                                                   0.0%     9   23.4  23.8  22.8  26.4   1.0
```

На каком участке наибольшая задержка - delay?  - * Наибольшая я думаю на 5 смотрю по среднему значению Avg 27.2

### 7. Какие DNS сервера отвечают за доменное имя dns.google? Какие A записи? Воспользуйтесь утилитой `dig`

## 7 Решение: 

```bash
vagrant@vagrant:~$ dig dns.google

; <<>> DiG 9.16.1-Ubuntu <<>> dns.google
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 38973
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;dns.google.                    IN      A

;; ANSWER SECTION:
dns.google.             643     IN      A       8.8.8.8
dns.google.             643     IN      A       8.8.4.4

;; Query time: 12 msec
;; SERVER: 127.0.0.53#53(127.0.0.53)
;; WHEN: Sun Feb 19 20:28:43 UTC 2023
;; MSG SIZE  rcvd: 71
```

Какие DNS сервера отвечают за доменное имя dns.google - *8.8.8.8; 8.8.4.4*

Какие A записи? 

`dns.google.             643     IN      A       8.8.8.8`

`dns.google.             643     IN      A       8.8.4.4`

### 8. Проверьте PTR записи для IP адресов из задания 7. Какое доменное имя привязано к IP? Воспользуйтесь утилитой `dig`

## 8. Решение:

```bash
vagrant@vagrant:~$ dig -x 8.8.8.8

; <<>> DiG 9.16.1-Ubuntu <<>> -x 8.8.8.8
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 46557
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;8.8.8.8.in-addr.arpa.          IN      PTR

;; ANSWER SECTION:
8.8.8.8.in-addr.arpa.   36128   IN      PTR     dns.google.

;; Query time: 8 msec
;; SERVER: 127.0.0.53#53(127.0.0.53)
;; WHEN: Sat Feb 18 22:15:11 UTC 2023
;; MSG SIZE  rcvd: 73


vagrant@vagrant:~$ dig -x 8.8.4.4

; <<>> DiG 9.16.1-Ubuntu <<>> -x 8.8.4.4
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 48695
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;4.4.8.8.in-addr.arpa.          IN      PTR

;; ANSWER SECTION:
4.4.8.8.in-addr.arpa.   19562   IN      PTR     dns.google.

;; Query time: 8 msec
;; SERVER: 127.0.0.53#53(127.0.0.53)
;; WHEN: Sun Feb 19 20:36:03 UTC 2023
;; MSG SIZE  rcvd: 73
```

Какое доменное имя привязано к IP? 
*dns.google.*








