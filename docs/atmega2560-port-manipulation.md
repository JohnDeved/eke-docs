---
name: Port Manipulation
menu: Atmega 2560
---

# Port Manipulation

Verwendung der GPIO (General Purpose Input/Output) Pins.

## Ports

### Was ist ein Port?
Ein Array von 8 Pins die logisch zu einem Port zusammengefasst werden. Da der Atmega2560 ein 8-Bit-Controller ist macht es Sinn Gruppen von 8 zu bilden.

*PORTF am [Pinout](../docs-atmega2560-pinmap):*

![PORTF](https://i.imgur.com/Mf3BDdw.png)

Um auf einzelne Pins oder auf einen ganzen Port etwas zu schreiben müssen zuerst die jeweiligen Pins im Datenrichtungsregister auf Ausgang gesetzt werden.
Danach kann auf einem Port 0 oder 1 geschaltet werden indem das entsprechende Bit gesetzt wird.

```c
PORTA = 0xFF; // PORTA - alle Ausgänge auf 1 setzen
PORTB = 0xF0; // PORTB - 4 Bits auf 1 setzen; 4 Bits auf 0 setzen
```

## Datenrichtungsregister

Mit dem DDR können ganze Ports oder einzelne Pins auf Ausgang/Eingang gesetzt werden.

```c
//x .. Bezeichnung des Ports
DDRx = [0 .. 255];
```
Beispiel:
```c
DDRA = 0xFF; // PORTA - alle 8 Bits auf Ausgang
DDRB = 0b10101010; // PORTB - abwechselnd Ausgang und Eingang
DDRC = 0x0F; // PORTC - 4 Bits auf Eingang; 4 auf Ausgang
```
