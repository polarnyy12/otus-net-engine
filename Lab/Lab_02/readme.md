#  Просмотр таблицы MAC-адресов коммутатора 
## Топология:

![](topology.png)



## Таблица адресации.

| Устройство     | Интерфейс   | IP-адрес / префикс            | Маска подсети                 |
|---------------:|:------------|------------------------------:|------------------------------:|
| S1             | VLAN 1      | 192.168.1.11/24              | 255.255.255.0                 | 
| S2             | VLAN 1      | 192.168.1.12/24              | 255.255.255.0                 | 
| PC-A           | NIC         | 192.168.1.1/24               | 255.255.255.0                 | 
| PC-B           | NIC         | 192.168.1.2/24               | 255.255.255.0                 | 


###  	Задачи:

  1. [Создание и настройка сети;](readme.md#проверка-конфигурации-коммутатора-по-умолчанию)
  2. [Изучение таблицы МАС-адресов коммутатора;](readme.md#%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D0%B5%D1%82%D0%B8-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D1%8B%D1%85-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0)
      -	[Настройте базовые параметры коммутатора;](readme.md#%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B1%D0%B0%D0%B7%D0%BE%D0%B2%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%BA%D0%BE%D0%BC%D0%BC%D1%83%D1%82%D0%B0%D1%82%D0%BE%D1%80%D0%B0)
      - [Настройте IP-адрес для ПК;](readme.md#%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-ip-%D0%B0%D0%B4%D1%80%D0%B5%D1%81-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BA)
  3. [Проверка сетевых подключений;](readme.md#%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D1%81%D0%B5%D1%82%D0%B5%D0%B2%D1%8B%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9)
      -	[Отобразите конфигурацию устройства;](readme.md#%D0%BE%D1%82%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D0%B8%D1%82%D0%B5-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B3%D1%83%D1%80%D0%B0%D1%86%D0%B8%D1%8E-%D0%BA%D0%BE%D0%BC%D0%BC%D1%83%D1%82%D0%B0%D1%82%D0%BE%D1%80%D0%B0)
      - [Протестируйте сквозное соединение, отправив эхо-запрос;](readme.md#%D0%BF%D1%80%D0%BE%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D1%83%D0%B9%D1%82%D0%B5-%D1%81%D0%BA%D0%B2%D0%BE%D0%B7%D0%BD%D0%BE%D0%B5-%D1%81%D0%BE%D0%B5%D0%B4%D0%B8%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%B2-%D1%8D%D1%85%D0%BE-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81)
      - [Протестируйте возможности удаленного управления с помощью Telnet;](readme.md#%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%BD%D0%BE%D0%B5-%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BC%D0%BC%D1%83%D1%82%D0%B0%D1%82%D0%BE%D1%80%D0%BE%D0%BC-s1)


###  Создание и настройка сети:

![](topology.png)

####  Настройте базовые параметры каждого коммутатора

##### S1:
~~~
Password: 
S1>sh
S1>show r
S1>show ru
S1>show run
S1>en      
Password: 
Password: 
S1#sh
S1#show ru
S1#show running-config 
Building configuration...

Current configuration : 890 bytes
!
! Last configuration change at 12:21:56 UTC Sun Oct 25 2026
!
version 15.2
service timestamps debug datetime msec
service timestamps log datetime msec
service password-encryption
service compress-config
!
hostname S1
!
boot-start-marker
boot-end-marker
!
!
enable secret 5 $1$BZKU$kwytmKYl1dCvnv7b1GDoi1
!
no aaa new-model
!
!
!
!         
!
!
!
!
no ip domain-lookup
ip cef
no ipv6 cef
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
vlan internal allocation policy ascending
!
! 
!
!
!
!
!
!
!
!         
!
!
!
interface Ethernet0/0
!
interface Ethernet0/1
!
interface Ethernet0/2
!
interface Ethernet0/3
!
interface Vlan1
 ip address 192.168.1.11 255.255.255.0
!
ip forward-protocol nd
!
no ip http server
no ip http secure-server
!
!
!
!
!         
!
control-plane
!
!
line con 0
 password 7 14141B180F0B
 logging synchronous
 login
line aux 0
line vty 0 4
 password 7 060506324F41
 login
!
!
end

S1# 

~~~

##### S2:

~~~
S2>en      
Password: 
S2#sh
S2#show ru
S2#show running-config 
Building configuration...

Current configuration : 890 bytes
!
! Last configuration change at 12:33:49 UTC Sun Oct 25 2026
!
version 15.2
service timestamps debug datetime msec
service timestamps log datetime msec
service password-encryption
service compress-config
!
hostname S2
!
boot-start-marker
boot-end-marker
!
!
enable secret 5 $1$j.Rq$U1P7KZECSzJbrNu7cjrpp/
!
no aaa new-model
!
!
!
!         
!
!
!
!
no ip domain-lookup
ip cef
no ipv6 cef
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
vlan internal allocation policy ascending
!
! 
!
!
!
!
!
!
!
!         
!
!
!
interface Ethernet0/0
!
interface Ethernet0/1
!
interface Ethernet0/2
!
interface Ethernet0/3
!
interface Vlan1
 ip address 192.168.1.12 255.255.255.0
!
ip forward-protocol nd
!
no ip http server
no ip http secure-server
!
!
!
!
!         
!
control-plane
!
!
line con 0
 password 7 01100F175804
 logging synchronous
 login
line aux 0
line vty 0 4
 password 7 00071A150754
 login
!
!
end
~~~
~~~
enable
  show running-configure
~~~
~~~
Building configuration...

Current configuration : 1080 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Switch
!
!
!
!
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
!
interface FastEthernet0/2
!
interface FastEthernet0/3
!
interface FastEthernet0/4
!
interface FastEthernet0/5
!
interface FastEthernet0/6
!
interface FastEthernet0/7
!
interface FastEthernet0/8
!
interface FastEthernet0/9
!
interface FastEthernet0/10
!
interface FastEthernet0/11
!
interface FastEthernet0/12
!
interface FastEthernet0/13
!
interface FastEthernet0/14
!
interface FastEthernet0/15
!
interface FastEthernet0/16
!
interface FastEthernet0/17
!
interface FastEthernet0/18
!
interface FastEthernet0/19
!
interface FastEthernet0/20
!
interface FastEthernet0/21
!
interface FastEthernet0/22
!
interface FastEthernet0/23
!
interface FastEthernet0/24
!
interface GigabitEthernet0/1
!
interface GigabitEthernet0/2
!
interface Vlan1
 no ip address
 shutdown
!
!
!
!
line con 0
!
line vty 0 4
 login
line vty 5 15
 login
!
!
!
!
end
~~~


### Изучение таблицы МАС-адресов коммутатора;

#### Запишите МАС-адреса сетевых устройств;

| Устройство     | MAC-адрес   | 
|---------------:|:------------|
| PC-A           |  00:50:79:66:68:03    |
| PC-B           |  00:50:79:66:68:04    | 

![](pc-a.png)      ![](pc-b.png)


S1:
~~~
S1#show interfaces ethernet 0/3
Ethernet0/3 is up, line protocol is up (connected) 
  Hardware is AmdP2, address is aabb.cc00.1030 (bia aabb.cc00.1030)
  MTU 1500 bytes, BW 10000 Kbit/sec, DLY 1000 usec, 
     reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation ARPA, loopback not set
  Keepalive set (10 sec)
  Auto-duplex, Auto-speed, media type is unknown
  input flow-control is off, output flow-control is unsupported 
  ARP type: ARPA, ARP Timeout 04:00:00
  Last input 00:03:36, output 00:00:01, output hang never
  Last clearing of "show interface" counters never
  Input queue: 0/2000/0/0 (size/max/drops/flushes); Total output drops: 0
  Queueing strategy: fifo
  Output queue: 0/0 (size/max)
  5 minute input rate 0 bits/sec, 0 packets/sec
  5 minute output rate 0 bits/sec, 0 packets/sec
     8 packets input, 500 bytes, 0 no buffer
     Received 2 broadcasts (0 multicasts)
     0 runts, 0 giants, 0 throttles 
     0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored
     0 input packets with dribble condition detected
     2377 packets output, 182136 bytes, 0 underruns
     0 output errors, 0 collisions, 0 interface resets
     0 unknown protocol drops
     0 babbles, 0 late collision, 0 deferred
     0 lost carrier, 0 no carrier
     0 output buffer failures, 0 output buffers swapped out
~~~

S2:

~~~
S2#show interfaces ethernet 0/2 
Ethernet0/2 is up, line protocol is up (connected) 
  Hardware is AmdP2, address is aabb.cc00.2020 (bia aabb.cc00.2020)
  MTU 1500 bytes, BW 10000 Kbit/sec, DLY 1000 usec, 
     reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation ARPA, loopback not set
  Keepalive set (10 sec)
  Auto-duplex, Auto-speed, media type is unknown
  input flow-control is off, output flow-control is unsupported 
  ARP type: ARPA, ARP Timeout 04:00:00
  Last input 00:06:59, output 00:00:01, output hang never
  Last clearing of "show interface" counters never
  Input queue: 0/2000/0/0 (size/max/drops/flushes); Total output drops: 0
  Queueing strategy: fifo
  Output queue: 0/0 (size/max)
  5 minute input rate 0 bits/sec, 0 packets/sec
  5 minute output rate 0 bits/sec, 0 packets/sec
     4 packets input, 254 bytes, 0 no buffer
     Received 0 broadcasts (0 multicasts)
     0 runts, 0 giants, 0 throttles 
     0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored
     0 input packets with dribble condition detected
     911 packets output, 72031 bytes, 0 underruns
     0 output errors, 0 collisions, 0 interface resets
     0 unknown protocol drops
     0 babbles, 0 late collision, 0 deferred
     0 lost carrier, 0 no carrier
     0 output buffer failures, 0 output buffers swapped out
~~~



 ##### В режиме глобальной конфигурации скопируйте следующие базовые параметры конфигурации и вставьте их в файл на коммутаторе.

~~~
Switch>clear
Translating "clear"...domain server (255.255.255.255) % Name lookup aborted
Switch>en
Switch#no ip
Switch#no ip do
Switch#no ip dom
Switch#no ip doma
Switch#no ip doma?
% Unrecognized command
Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#n
Switch(config)#no ip do
Switch(config)#no ip dom
Switch(config)#no ip dom?
domain  domain-lookup  domain-name  
Switch(config)#no ip domain0l
Switch(config)#no ip domain-lo
Switch(config)#no ip domain-lookup 
Switch(config)#ho
Switch(config)#hostname S1
S1(config)#ser
S1(config)#service pas
S1(config)#service password-encryption 
S1(config)#ena
S1(config)#enable se
S1(config)#enable secret class
S1(config)#bann
S1(config)#banner 
S1(config)#banner motd #
Enter TEXT message.  End with the character '#'.
Unauthorized access is strictly prohibited #

S1(config)#
~~~

##### Назначить IP-адрес интерфейсу VLAN 1

~~~
S1(config)#log
S1(config)#logging s
S1(config)#logging sy
S1(config)#logging ?
  A.B.C.D   IP address of the logging host
  buffered  Set buffered logging parameters
  console   Set console logging parameters
  host      Set syslog server IP address and parameters
  on        Enable logging to all enabled destinations
  trap      Set syslog server logging level
S1(config)#li
S1(config)#line con
S1(config)#line console 0
S1(config-line)#logg
S1(config-line)#logging s
S1(config-line)#logging synchronous 
S1(config-line)#exit
S1(config)#in
S1(config)#interface vl
S1(config)#interface vlan 1
S1(config-if)#ip
S1(config-if)#ip af
S1(config-if)#ip ad
S1(config-if)#ip address 192.168.1.2 255.255.255.0
S1(config-if)#no
S1(config-if)#no sh
S1(config-if)#no shutdown 

S1(config-if)#
%LINK-3-UPDOWN: Interface Vlan1, changed state to down

%LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan1, changed state to up

S1(config-if)#
S1(config-if)#

~~~

##### Доступ через порт консоли также следует ограничить с помощью пароля.

~~~
S1(config)#li
S1(config)#line cco
S1(config)#line co
S1(config)#line console 0
S1(config-line)#pas
S1(config-line)#password cisco
S1(config-line)#lo
S1(config-line)#lo
% Ambiguous command: "lo"
S1(config-line)#log
S1(config-line)#log?
logging  login  
S1(config-line)#logi
S1(config-line)#login 
S1(config-line)#li
S1(config-line)#lin
S1(config-line)#line vty 0 4
S1(config-line)#pas
S1(config-line)#password cisco
S1(config-line)#log
S1(config-line)#login
S1(config-line)#login 
S1(config-line)#tra
S1(config-line)#transport in
S1(config-line)#transport input all
S1(config-line)#line vty 5 8
S1(config-line)#tra
S1(config-line)#transport in
S1(config-line)#transport input ssh
S1(config-line)#ser
S1(config-line)#serv
S1(config-line)#exit
S1(config)#ser
S1(config)#end
~~~

#### Настройте IP-адрес для ПК.

![](pc-a.png)

![](pc-a1.png)


### Проверка сетевых подключений:

#### Отобразите конфигурацию коммутатора

~~~
Unauthorized access is strictly prohibited 


User Access Verification

Password: 
S1>sh
S1>show r
S1>show ru
S1>en
S1>enable 
Password: 
S1#
S1#
S1#
S1#
S1#
S1#sh
S1#show r
S1#show running-config 
Building configuration...

Current configuration : 1333 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname S1
!
enable secret 5 $1$mERr$9cTjUIEqNGurQiFU.ZeCi1
!
!
!
no ip domain-lookup
!
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
!
interface FastEthernet0/2
!
interface FastEthernet0/3
!
interface FastEthernet0/4
!
interface FastEthernet0/5
!
interface FastEthernet0/6
!
interface FastEthernet0/7
!
interface FastEthernet0/8
!
interface FastEthernet0/9
!
interface FastEthernet0/10
!
interface FastEthernet0/11
!
interface FastEthernet0/12
!
interface FastEthernet0/13
!
interface FastEthernet0/14
!
interface FastEthernet0/15
!
interface FastEthernet0/16
!
interface FastEthernet0/17
!
interface FastEthernet0/18
!
interface FastEthernet0/19
!
interface FastEthernet0/20
!
interface FastEthernet0/21
!
interface FastEthernet0/22
!
interface FastEthernet0/23
!
interface FastEthernet0/24
!
interface GigabitEthernet0/1
!
interface GigabitEthernet0/2
!
interface Vlan1
 ip address 192.168.1.2 255.255.255.0
!
banner motd ^C
Unauthorized access is strictly prohibited ^C
!
!
!
line con 0
 password 7 0822455D0A16
 logging synchronous
 login
!
line vty 0 4
 password 7 0822455D0A16
 login
line vty 5 8
 login
 transport input ssh
line vty 9 15
 login
!
!
!
!
end

~~~

#### Протестируйте сквозное соединение, отправив эхо-запрос.

![](ping.png)

####  Проверьте удаленное управление коммутатором S1.

![](telnet_по_сети.png)


