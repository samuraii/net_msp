# Конспект по сетям

## Часть 1

### Представление IP адреса

32 бита в версии IPv4 по 8 в каждом октете

192.100.14.130 
```
Двоичная -> 1100 0000 | [0]110 0100 | [0000] 1110 | 1000 0010
Восьмеричная -> 030031007202
Шестнадцатиричная -> 0xC0640E82
```

### Классы подсетей

192.100.14.130

Калсс определяет деление на Net.id + Host.id
```
A -> 192 + 100.14.130
B -> 192.100 + 14.130
C -> 192.100.14 + 130

Net.id
x.0.0.0
x.x.0.0
x.x.x.0

От 1 до 254 - Host.id

Broadcast
x.255.255.255
x.x.255.255
x.x.x.255
```

#### Диапазоны многкратного использования
```
10.0.0.0 - 10.255.255.255
172.16.0.0 - 172.16.255.255
192.168.0.0 - 192.168.255.255
```

#### Пример расчета

197.197.197.[197] - Класс C

```
11000101 11000101 11000101 | 11000101 - host
                           | 00000000 - net
                           | 00000001 - 1st
                           | 11111110 - last
                           | 11111111 - broadcast
```

#### Технология Secure Inter-Domain Routing (SIDR)

197.197.197.197/21 - 21 это длина в битах ЛЕВОЙ части адреса

```
11000101 11000101 11000 | 101 11000101 - host
                        | 000 00000000 - net
                        | 000 00000001 - 1st
                        | 111 11111110 - last
                        | 111 11111111 - broadcast

```
