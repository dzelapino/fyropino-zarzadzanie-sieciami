# kroki wykonywania zadania

## OPIS FIRMY

Średniego rozmiaru firma podzielona na 3 zespoły, plus pare dodatkowych osób

##### Router 1 - Dev 1

ip 192.168.30.1
nazwa Developers-1
siec dev1
haslo dev1admin

siec dev1 jest wireless

posiada ona 6 podpiętych komputerów adresy są dynamiczne
- Dev_1-1
- Dev_1-2
- Dev_1-3
- Dev_1-4
- Dev_1-5
- Dev_1-6

Router sieci jest podpięty do sieci routera Developers-2
192.168.3.2 (Dev-1) idzie do default gateway 192.168.3.1 (Dev-2)

##### Router 2 - Dev 2

siec przewodowa 
- g0/0
- ip 192.168.3.1

- Dev_2-1 podpięty do fa0/11, 192.168.3.11
- Dev_2-2 podpięty do fa0/12, 192.168.3.12
- Dev_2-3 podpięty do fa0/13, 192.168.3.13
- Dev_2-4 podpięty do fa0/14, 192.168.3.14
- Dev_2-5 podpięty do fa0/15, 192.168.3.15
- Dev_2-6 podpięty do fa0/16, 192.168.3.16


##### Router 3 - Dev 3

- ip 192.168.4.1

- Dev_3-1 podpięty do fa0/11, 192.168.4.11
- Dev_3-2 podpięty do fa0/12, 192.168.4.12
- Dev_3-3 podpięty do fa0/13, 192.168.4.13
- Dev_3-4 podpięty do fa0/14, 192.168.4.14
- Dev_3-5 podpięty do fa0/15, 192.168.4.15
- Dev_3-6 podpięty do fa0/16, 192.168.4.16
- Dev_3-7 podpięty do fa0/17, 192.168.4.17
- Dev_3-8 podpięty do fa0/18, 192.168.4.18

### Zespół 2 - helpdesk

Zespół liczy 12 osób

- ip 192.168.5.1

- Help-1 podpięty do fa0/11, 192.168.5.11
- Help-2 podpięty do fa0/12, 192.168.5.12
- Help-3 podpięty do fa0/13, 192.168.5.13
- Help-4 podpięty do fa0/14, 192.168.5.14
- Help-5 podpięty do fa0/15, 192.168.5.15
- Help-6 podpięty do fa0/16, 192.168.5.16
- Help-7 podpięty do fa0/17, 192.168.5.17
- Help-8 podpięty do fa0/18, 192.168.5.18
- Help-9 podpięty do fa0/19, 192.168.5.19
- Help-10 podpięty do fa0/20, 192.168.5.20
- Help-11 podpięty do fa0/21, 192.168.5.21
- Help-12 podpięty do fa0/22, 192.168.5.22

### Zespół 3 - sales

- ip 192.168.6.1

Zespół liczy 10 osób

- Sa-1 podpięty do fa0/11, 192.168.6.11
- Sa-2 podpięty do fa0/12, 192.168.6.12
- Sa-3 podpięty do fa0/13, 192.168.6.13
- Sa-4 podpięty do fa0/14, 192.168.6.14
- Sa-5 podpięty do fa0/15, 192.168.6.15
- Sa-6 podpięty do fa0/16, 192.168.6.16
- Sa-7 podpięty do fa0/17, 192.168.6.17
- Sa-8 podpięty do fa0/18, 192.168.6.18
- Sa-9 podpięty do fa0/19, 192.168.6.19
- Sa-10 podpięty do fa0/20, 192.168.6.20

### Biuro

- ip 192.168.7.1

- Szefowa-1 podpięta do fa0/11, 192.168.7.11
- Szef-1 podpięty do fa0/12, 192.168.7.12
- Ksiegowy-1 podpięty do fa0/13, 192.168.7.13
- Ksiegowy-2 podpięty do fa0/14, 192.168.7.14
- Sekretarka-1 podpięty do fa0/15, 192.168.7.15

## Kroki po zbudowaniu dwóch gałęzi

Mamy dwa zespoły Developers-3 i Developers-2
Żeby mogły się nawzajem komunikować musimy ustawić next hop, jest to jakby następny skok w sieci, ustawiamy go w zakładce routing static. Następnie należy podać adres ip na który chcemy iść (czyli ten docelowy np z dev3 chcemy do dev2 więc docelowy to 192.168.3.0), maskę podsieci (255.255.255.0) i next hop (jest to adres którym jakby wchodzimy do tamtej sieci patrz router dev2 czyli podajemy 192.168.10.1). Ostatecznie aby komunikacja się powiodła druga strona musi zostać adekwatnie skonfigurowana (192.168.4.0, 255.255.255.0, 192.168.10.2).

## Komunikacja

Biuro może komunikować się z każdym z zespołów (Każdy zespół zna ścieżkę do biura i biuro do każdego). Zespoły nie mogą się ze sobą komunikować, jedynym wyjątkiem są zespoły dev1 i dev2, dev1 jest podpięty do routera bezprzewodowego który należy do sieci routera dev2.

## Remote access

W celu umożliwienia połączenia z chmurą dodany zostaje Cloud-PT

Komputer pracownika łączy się z modemem przez ethernet a modem z chmurą przez kabel telefoniczny

Wchodzimy w config modemu wybieramy DSL i widzimy że pt nam podpowiada Modem4 <-> Ethernet6

Następnie nalezy skonfigurować router Remote-1
Ustawiamy ip i maskę podsieci (192.168.8.1 255.255.255.0), następnie robimy dhcp pool

```txt
z poziomu config

ip dhcp pool REMOTE_POOL

network 192.168.8.0 255.255.255.0

default-router 192.168.8.1

ctrl-z

wpisujemy wr
```

Wbijamy w komputer pracownika, wybieramy desktop i potem ip configuration, klikamy dhcp i widzimy że dostał adres ip

### VPN

Wchodzimy w Remote-1, wpisujemy conf t, a następnie ustawiamy AAA.

```txt
aaa new-model 

aaa authentication login REMOTE local
aaa authorization network REMOTE local

username VPN secret supersecure
```

Te powyższe powodują że nasze uwierzytelnienie nastąpi z lokalnym username w routerze

```txt
i mimo zmiany routera na nowszy nie działa poniższe polecenie

crypto isakmp policy 10

```

No ale dobra pomimo że nie da sie skonfigurowac tak jak powinno to w skrócie
Robimy grupę vpn, w desktopie usera wpisujemy potrzebne dane, i wtedy pojawiłby się nam tunel którym mamy dostęp do sieci w naszej firmie 