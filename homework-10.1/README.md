# Домашнее задание к занятию 10.1"`Keepalived/vrrp`" - `Konstantin Frolov`




### Задание 1

https://ibb.co/s96JVhW

---

vrrp_instance failover_test {
state MASTER
interface enp0s8
virtual_router_id 10
priority 255
advert_int 4
authentication {
auth_type AH
auth_pass 1111
}
unicast_peer {
192.168.1.6
}
virtual_ipaddress {
192.168.0.50 dev enp0s8 label enp0s8:vip
}
}

---

vrrp_instance failover_test {
state BACKUP
interface enp0s8
virtual_router_id 10
priority 110
advert_int 4
authentication {
auth_type AH
auth_pass 1111
}
unicast_peer {
192.168.1.7
}
virtual_ipaddress {
192.168.0.50 dev enp0s8 label enp0s8:vip
}
}




