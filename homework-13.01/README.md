### Задание 1


- Какие сетевые службы в ней разрешены?

![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-13.01/nvm.png)

- Какие уязвимости были вами обнаружены? (список со ссылками: достаточно трёх уязвимостей)


https://www.exploit-db.com/exploits/18368
---
https://www.exploit-db.com/exploits/15449
---
https://www.exploit-db.com/exploits/17491

### Задание 2

Проведите сканирование Metasploitable в режимах SYN, FIN, Xmas, UDP.

Запишите сеансы сканирования в Wireshark.

Ответьте на следующие вопросы:

Чем отличаются эти режимы сканирования с точки зрения сетевого трафика?
Как отвечает сервер?

```
При использовании режима SYN не откывается полного TCP соединения, посылается пакет SYN если ответ приходит SYN/ACK то порт слушается а RST что не прослушивается 
При использовании FIN сканирования пакет содержит ACK флаг открытые и закрытые порты будут отвечать RST порты которые ответят ICMP будут помечены как фильтруемые
При использовании Xmas сканирования отправляются FIN PSH URG флаги, если ответ приходит с RTS порт считается открытым, отстуствие ответа означает что порт открыт или фильтруется 
Использование UDP режима являяется очень долгим nmap отправляет 1 пакет в секунду , в режиме UDP отправляется пакет с UDP флагом , ответ ICMP пакетом TYPE : 3 CODE : 3 означает что порт закрыт, другие ICMP ошибки означают что порт фильтруется, UDP ответ будет означать что порт открыт 
```



![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-13.01/1.png)
---
![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-13.01/2.png)
---
![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-13.01/3.png)
---
![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-13.01/4.png)

































