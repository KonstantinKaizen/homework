### Задание 1

Проведите разведку системы и определите, какие сетевые службы запущены на защищаемой системе:

sudo nmap -sA < ip-адрес >

sudo nmap -sT < ip-адрес >

sudo nmap -sS < ip-адрес >

sudo nmap -sV < ip-адрес >

![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-13.03/2.png)





### Задание 2

Проведите атаку на подбор пароля для службы SSH:

hydra -L users.txt -P pass.txt < ip-адрес > ssh


![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-13.03/1.png)
































