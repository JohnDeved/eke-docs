---
name: USART
menu: Atmega 2560
---

# USART

## Welche Register werden Verwendet

- UCSRA
    - Aktueller Status des UART (Framing Error, Parity Error, Transmit Completed...)
- UCSRB
    - Einstellungen des UART (Interrupt Enable, Receiver/Transmitter, Charsize...)
- UCSRC
    - Modus Auswahl (Asynchron/Synchron, Stop Bits, Charsize, Clock Polarity...)
- UDR
    - Daten Register, Eigentlich 2 Register (Input, Output), je nach Betriebsart wird eines angesprochen
- UBRR
    - Hier wird die Baud Rate festgelegt
    - UBRR = Taktfrequenz / (Baudrate*16) - 1
    - Baudraten bis über 115200 möglich
    
## Daten Senden    
### UART initialisieren

```c++
UCSRB |= (1<<TXEN);                 //Transmitter Enable bit setzen um Daten zu empfangen
UCSR0C = (1<<UCSZ01)|(1<<UCSZ00);   //Frame Format auf Asynchron 8N1 setzen
```

### Zeichen Senden Funktion

```c++
void uart_putc(unsigned char c) {
    while (!(UCSRA & (1<<UDRE))) {}    // Warten bis UDR Frei is
    UDR = c;                           // schreibt den char auf die Schnittstelle
}
```

## Daten Empfangen
### UART initialisieren

```cpp
UBRRH = UBRR_VAL >> 8;
UBRRL = UBRR_VAL & 0xFF;

UCSRB |= (1<<RXEN);                 //Receiver Enable bit setzen um Daten zu empfangen
UCSR0C = (1<<UCSZ01)|(1<<UCSZ00);   //Frame Format auf Asynchron 8N1 setzen
```

###Zeichen Empfangen Funktion
```cpp
uint8_t uart_getc(void) {
    while (!(UCSRA & (1<<RXC))) {}        // Warten bis Daten auf UDR
    return UDR:                           // Empfangene Daten Zurückgeben
}
