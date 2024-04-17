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

##### Router 4 - Dev 4

#### Dane ich sieci

ip 192.168.2.1
nazwa Zespol_dev
siec Siec_dev
haslo devdevdev

### Zespół 2 - helpdesk

Zespół liczy 15 osób

### Zespół 3 - sales

Zespół liczy 10 osób

### Pozostałe osoby

- Kurier 1
- Kurier 2

## Kroki po zbudowaniu dwóch gałęzi

Mamy dwa zespoły Developers-1 i Developers-2
