# kroki wykonywania zadania

## OPIS FIRMY

Średniego rozmiaru firma podzielona na 3 zespoły, plus pare dodatkowych osób

### Zespół 1 - dev

Zespół liczy 20 osób

#### Ich dane sieciowe

Mają 4 routery

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

z interfejsu g0/0 wychodzi kabel do switcha (g0/1)

- Dev_2-1 podpięty do fa0/11, 192.168.3.11
- Dev_2-2 podpięty do fa0/12, 192.168.3.12
- Dev_2-3 podpięty do fa0/13, 192.168.3.13
- Dev_2-4 podpięty do fa0/14, 192.168.3.14
- Dev_2-5 podpięty do fa0/15, 192.168.3.15
- Dev_2-6 podpięty do fa0/16, 192.168.3.16


##### Router 3 - Dev 3

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

### Zespół 3 - sales

Zespół liczy 10 osób

### Pozostałe osoby

- Kurier 1
- Kurier 2

## Kroki po zbudowaniu dwóch gałęzi

Mamy dwa zespoły Developers-3 i Developers-2
Żeby mogły się nawzajem komunikować musimy ustawić next hop, jest to jakby następny skok w sieci, ustawiamy go w zakładce routing static. Następnie należy podać adres ip na który chcemy iść (czyli ten docelowy np z dev3 chcemy do dev2 więc docelowy to 192.168.3.0), maskę podsieci (255.255.255.0) i next hop (jest to adres którym jakby wchodzimy do tamtej sieci patrz router dev2 czyli podajemy 192.168.10.1). Ostatecznie aby komunikacja się powiodła druga strona musi zostać adekwatnie skonfigurowana (192.168.4.0, 255.255.255.0, 192.168.10.2).