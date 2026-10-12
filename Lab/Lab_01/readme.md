#  Базовая настройка коммутатора
<details open>

<summary>Топология:</summary>

![](cpt1.png)

</details>

## Таблица адресации.

| Устройство     | Интерфейс   | IP-адрес / префикс            |
|---------------:|:------------|------------------------------:|
| S1             | VLAN 1      | 192.168.1.2 /24               | 
| PC-A           | NIC         | 192.168.1.10 /24              | 


###  	Задачи:

  1. [Проверка конфигурации коммутатора по умолчанию;](readme.md#проверка-конфигурации-коммутатора-по-умолчанию)
  2. [Создание сети и настройка основных параметров устройства;](readme.md#%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D0%B5%D1%82%D0%B8-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D1%8B%D1%85-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0)
      -	[Настройте базовые параметры коммутатора;](readme.md#%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B1%D0%B0%D0%B7%D0%BE%D0%B2%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%BA%D0%BE%D0%BC%D0%BC%D1%83%D1%82%D0%B0%D1%82%D0%BE%D1%80%D0%B0)
      - Настройте IP-адрес для ПК;
  3. Проверка сетевых подключений;
      -	Отобразите конфигурацию устройства;
      - Протестируйте сквозное соединение, отправив эхо-запрос;
      - Протестируйте возможности удаленного управления с помощью Telnet;

<details open>
	
## Проверка конфигурации коммутатора по умолчанию: 

![](telnet.png)

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

</details>


<details open>
	
## Создание сети и настройка основных параметров устройства;

###	Настройте базовые параметры коммутатора;
	
~~~
Switch>en
Switch#no ip domain-lookup
          ^
% Invalid input detected at '^' marker.
	
Switch#hostname S1
                ^
% Invalid input detected at '^' marker.
	
Switch#service password-encryption
               ^
% Invalid input detected at '^' marker.
	
Switch#enable secret class
              ^
% Invalid input detected at '^' marker.
	
Switch#banner motd #
              ^
% Invalid input detected at '^' marker.
	
Switch#Unauthorized access is strictly prohibited. #
                    ^
% Invalid input detected at '^' marker.
	
Switch#co
Switch#con
Switch#conf
Switch#configure 
Configuring from terminal, memory, or network [terminal]? 
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#no ip domain-lookup
Switch(config)#hostname S1
S1(config)#service password-encryption
S1(config)#enable secret class
S1(config)#banner motd #
Enter TEXT message.  End with the character '#'.
Unauthorized access is strictly prohibited. #

S1(config)#
S1(config)#li
S1(config)#line ccon
S1(config)#line con
S1(config)#line console 0
S1(config-line)#log
S1(config-line)#logg
S1(config-line)#logging 
% Incomplete command.
S1(config-line)#logging ?
  synchronous   Synchronized message output
S1(config-line)#logging syn
S1(config-line)#logging synchronous 
S1(config-line)#
~~~

</details>
