---
name: IP-Adressen
menu: INF
---

# IP-Adressen

Created: Sep 18, 2020 8:13 AM

*172.16.20.1*

## Classful IP Addressing

### Class A

- Beginnend mit 0
    - 0XXXXXX
- IP-Adressen
    - 0.0.0.0 bis 127.XX.X ⇒ 16,7 Millionen IP-Adressen

### Class B

- Beginnend mit 10
    - 10XXXXXX
- IP-Adressen
    - 128.0.X.X bis 191.255.XX ⇒ 16384 Netzwerke mit je 65534 Adressen

### Class C

- Beginnend mit 110
    - 110XXXXX.
- IP-Adressen
    - 192.0.0.X bis 223.255.255.x ⇒ ~2,1 Millionen Netzwerke mit je 254 Adressen

### Class D

- Beginnend mit 1110
    - 1110XXXX
- IP-Adressen
    - 224.X.X.X bis 239.X.X.X ⇒ für Multicasting-Anwendungen reserviert

### Class E

- Beginnend mit 1111
    - 1111XXXX
- IP-Adressen
    - 240.X.X.X bis 255.X.X.X ⇒ für Weiterentwicklung

<!-- ![IP-Adressen%207b92240ed0ba402f9a60c543ec3300ac/Untitled.png](IP-Adressen%207b92240ed0ba402f9a60c543ec3300ac/Untitled.png) -->

## Subnetting

IP: 192.168.1.0

Binär `11000000.10101000.00000001.00000000`

SNM: 255.255.255.0

Binär `11111111.11111111.11111111.00000000`

    `<--------Netzanteil------> <-Host->`

2 Subnetze ⇒ 1 Bit

Binär                               `11111111.11111111.11111111.10000000`

SN1 Netzwerkadresse  `192.     168.     1.       0`

SN1  Broadcast             `192.     168.     1.       127`

SN1 Host                          `.        .      .       1 bis 126`

SN2 Netzwerkadresse `192.     168.     1.       128`

SN2 Host                          `.        .      .       129 bis 254`

## VLSM (Variable Length SubnetMasks)

Eingeführt 1987 mit der RFC 1009 ermöglicht VLSM eine individuelle Aufteilung von Netzen.

```markdown
																		/ 192.168.1.0  |25
								 / 192.167.1.0|24 -
192.168.0.0/16 -                    \ 192.168.1.128|25
								 \ 192.168.2.0|24
```

## CIDR (Classless Inter-Domain Routing)

Aufgrund der explosionsartigen Steigerung der Bedarfs and IP-Adressen in den 90er Jahren wurde 1993 mit den RFC 1517 bis 1520 CIDR eingeführt

CIDR besitzt 2 grundlegende Eigenschaften:

1. Das Kassenschema wurde komplett und ersatzlos gestrichen! Class A netze konnten damit "innerhalb der Internets" und außerhalb von Organisationen im kleinere Subnetze geteilt werden
2. Zusammenfassen von einzelnen Routen zu einzigen Routing-Eintrag.

![https://dropper.link/stream/PpmNRiY.jpg](https://dropper.link/stream/PpmNRiY.jpg)

## Bsp. Subnetting

`172.16.30.0 / 24`

Subnet für

- Geschätsführung
- Verwaltung
- Produktion
- Vertrieb