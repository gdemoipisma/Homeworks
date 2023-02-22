# Домашнее задание к занятию "Компьютерные сети.Лекция 2"

## 1. Проверьте список доступных сетевых интерфейсов на вашем компьютере. Какие команды есть для этого в Linux и в Windows?

### Решение 1:
```bash
vagrant@vagrant:~$ ip link
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 08:00:27:14:86:db brd ff:ff:ff:ff:ff:ff
vagrant@vagrant:~$
vagrant@vagrant:~$ ip -c -br link
lo               UNKNOWN        00:00:00:00:00:00 <LOOPBACK,UP,LOWER_UP>
eth0             UP             08:00:27:14:86:db <BROADCAST,MULTICAST,UP,LOWER_UP>
vagrant@vagrant:~$ 
```

Какие команды есть для этого в Linux и в Windows? 
*В Windows ipconfig, в Linux ip link*


## 2. Какой протокол используется для распознавания соседа по сетевому интерфейсу? Какой пакет и команды есть в Linux для этого?

### Решение 2:
Какой протокол используется для распознавания соседа по сетевому интерфейсу? 
*Cisco Discavery Protokol (CDP), Link Layer Discovery Protocol (LLDP)*

*В Linux пакет LLDPD *

```bash
vagrant@vagrant:~$ man lldpcli

LLDPCLI(8)                                                       BSD System Manager's Manual                                                      LLDPCLI(8)

NAME
     lldpcli, lldpctl — control LLDP daemon

SYNOPSIS
     lldpcli [-dv] [-u socket] [-f format] [-c file] [command ...]
     lldpctl [-dv] [-u socket] [-f format] [interfaces ...]

DESCRIPTION
     The lldpcli program controls lldpd(8) daemon.

     When no command is specified, lldpcli will start an interactive shell which can be used to input arbitrary commands as if they were specified on the
     command line. This interactive shell should provide completion and history support.
```


## 3. Какая технология используется для разделения L2 коммутатора на несколько виртуальных сетей? Какой пакет и команды есть в Linux для этого? Приведите пример конфига.

### Решение 3:
*Для разделения сетей между собой на одном коммутаторе на уроыне L2 используют виртуальную сеть VLAN 
В Linux используется пакет VLAN 
```bash
vconfig add eth0 100
Added VLAN with VID == 100 to IF -:eth0:-

 /etc/network/interfaces

auto eth0.100
iface eth0.100 inet static
address 192.168.100.33
netmask 255.255.255.224
vlan-raw-device eth0

 ```      

## 4. Какие типы агрегации интерфейсов есть в Linux? Какие опции есть для балансировки нагрузки? Приведите пример конфига.

### Решение 4:

*Есть два типа агрегации LAG: "статический и динамический LACP", в Linux - bonding настраивается с помощью пакета ifenslave*

```bash
/etc/network/interfaces

auto bond0

iface bond0 inet static
    address 10.31.1.5
    netmask 255.255.255.0
    network 10.31.1.0
    gateway 10.31.1.254
    bond-slaves eth0 eth1
    bond-mode active-backup
    bond-miimon 100
    bond-downdelay 200
    bond-updelay 200
```

Какие опции есть для балансировки нагрузки?

Метод балансировки нагрузки повлияет на распределение трафика во всех EtherChannel, которые созданы на коммутаторе.

В зависимости от модели коммутатора, могут поддерживаться такие методы балансировки:

- по MAC-адресу отправителя или MAC-адресу получателя или учитывая оба адреса
- по IP-адресу отправителя или IP-адресу получателя или учитывая оба адреса
- по номеру порта отправителя или номеру порта получателя или учитывая оба порта

- Если один из портов в агрегированном канале выходит из строя, агрегированный канал работает. Он остается работоспособным до тех пор пока есть хотя бы один порт
- Динамическое агрегирование каналов с помощью LACP поддерживает standby порты, которые позволяют настраивать резервные порты, на случай если один из портов в агрегированном канале выйдет из строя

```bash
sw1(config)# port-channel load-balance ?
  dst-ip       Dst IP Addr
  dst-mac      Dst Mac Addr
  src-dst-ip   Src XOR Dst IP Addr
  src-dst-mac  Src XOR Dst Mac Addr
  src-ip       Src IP Addr
  src-mac      Src Mac Addr
  ```

## 5. Сколько IP адресов в сети с маской /29 ? Сколько /29 подсетей можно получить из сети с маской /24. Приведите несколько примеров /29 подсетей внутри сети 10.10.10.0/24.

### 5. Решение:

/29 : 
```bash
>>> 32-29
3
>>> 2**3
8
```
8 - 2 = 6 доступно
```bash
/24
>>> 32-24
8
>>> 2**8
>>> 256
```
256-2 = 254 доступно

Сколько /29 подсетей можно получить из сети с маской /24?

256/8=32 подсети

```bash
Network Address	Usable Host Range	Broadcast Address:
10.10.10.0	10.10.10.1 - 10.10.10.6	10.10.10.7
10.10.10.8	10.10.10.9 - 10.10.10.14	10.10.10.15
10.10.10.16	10.10.10.17 - 10.10.10.22	10.10.10.23
10.10.10.24	10.10.10.25 - 10.10.10.30	10.10.10.31
10.10.10.32	10.10.10.33 - 10.10.10.38	10.10.10.39
10.10.10.40	10.10.10.41 - 10.10.10.46	10.10.10.47
10.10.10.48	10.10.10.49 - 10.10.10.54	10.10.10.55
10.10.10.56	10.10.10.57 - 10.10.10.62	10.10.10.63
10.10.10.64	10.10.10.65 - 10.10.10.70	10.10.10.71
10.10.10.72	10.10.10.73 - 10.10.10.78	10.10.10.79
10.10.10.80	10.10.10.81 - 10.10.10.86	10.10.10.87
10.10.10.88	10.10.10.89 - 10.10.10.94	10.10.10.95
10.10.10.96	10.10.10.97 - 10.10.10.102	10.10.10.103
10.10.10.104	10.10.10.105 - 10.10.10.110	10.10.10.111
10.10.10.112	10.10.10.113 - 10.10.10.118	10.10.10.119
10.10.10.120	10.10.10.121 - 10.10.10.126	10.10.10.127
10.10.10.128	10.10.10.129 - 10.10.10.134	10.10.10.135
10.10.10.136	10.10.10.137 - 10.10.10.142	10.10.10.143
10.10.10.144	10.10.10.145 - 10.10.10.150	10.10.10.151
10.10.10.152	10.10.10.153 - 10.10.10.158	10.10.10.159
10.10.10.160	10.10.10.161 - 10.10.10.166	10.10.10.167
10.10.10.168	10.10.10.169 - 10.10.10.174	10.10.10.175
10.10.10.176	10.10.10.177 - 10.10.10.182	10.10.10.183
10.10.10.184	10.10.10.185 - 10.10.10.190	10.10.10.191
10.10.10.192	10.10.10.193 - 10.10.10.198	10.10.10.199
10.10.10.200	10.10.10.201 - 10.10.10.206	10.10.10.207
10.10.10.208	10.10.10.209 - 10.10.10.214	10.10.10.215
10.10.10.216	10.10.10.217 - 10.10.10.222	10.10.10.223
10.10.10.224	10.10.10.225 - 10.10.10.230	10.10.10.231
10.10.10.232	10.10.10.233 - 10.10.10.238	10.10.10.239
10.10.10.240	10.10.10.241 - 10.10.10.246	10.10.10.247
10.10.10.248	10.10.10.249 - 10.10.10.254	10.10.10.255
```


## 6. Задача: вас попросили организовать стык между 2-мя организациями. Диапазоны 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16 уже заняты. Из какой подсети допустимо взять частные IP адреса? Маску выберите из расчета максимум 40-50 хостов внутри подсети.

### 6. Решение: 

*Берем из диапазона 100.64.0.0 — 100.127.255.255*

```bash
vagrant@vagrant:~$ ipcalc 100.64.0.0/10 -s 40 -b
Address:   100.64.0.0
Netmask:   255.192.0.0 = 10
Wildcard:  0.63.255.255
=>
Network:   100.64.0.0/10
HostMin:   100.64.0.1
HostMax:   100.127.255.254
Broadcast: 100.127.255.255
Hosts/Net: 4194302               Class A

1. Requested size: 40 hosts
Netmask:   255.255.255.192 = 26
Network:   100.64.0.0/26
HostMin:   100.64.0.1
HostMax:   100.64.0.62
Broadcast: 100.64.0.63
Hosts/Net: 62                    Class A

Needed size:  64 addresses.
Used network: 100.64.0.0/26
```


## 7. Как проверить ARP таблицу в Linux, Windows? Как очистить ARP кеш полностью? Как из ARP таблицы удалить только один нужный IP?

### 7. Решение:

*windows - arp -a*
*Linux:*
```bash
~$ arp -e
Address                  HWtype  HWaddress           Flags Mask            Iface
10.0.2.3                 ether   52:54:00:12:35:03   C                     eth0
_gateway                 ether   52:54:00:12:35:02   C                     eth0
```

*Очистка Windows - 
  -d            Удаляет узел, задаваемый inet_addr. Параметр inet_addr может
                содержать знак шаблона * для удаления всех узлов.*
                
*Очистка Linux -
sudo ip neigh flush all*


arp -d hostname, –delete hostname: Removes any entry for the specified host.
If any host is down, there is no need of keeping its entry in arp cache so this command is used to delete those entries explicitly by the user
