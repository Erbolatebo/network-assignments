# Cisco Packet Tracer: Практические задачи

Данный проект включает три базовые задачи по сетевым технологиям, выполненные в Cisco Packet Tracer. Цель — закрепить навыки настройки IP-адресации, маршрутизации, VLAN и DHCP.

---

## Задача 1: Простая сеть с ручной IP-настройкой

**Цель:** Научиться настраивать IP-адреса вручную и проверять сетевое соединение.

**Описание:**
- Устройства: 2 ПК (PC0, PC1), коммутатор (Switch1)
- Схема подключения:  
  `PC0 ↔ Switch1 ↔ PC1`
- Назначение IP:
  - PC0: `192.168.10.1/24`, шлюз `192.168.10.254`
  - PC1: `192.168.10.2/24`, шлюз `192.168.10.254`
- Результат: успешный ping между ПК

---

## Задача 2: Сеть с двумя подсетями и статической маршрутизацией

**Цель:** Понять, как соединяются разные подсети через маршрутизатор.

**Описание:**
- Подсеть A:
  - PC2: `192.168.1.1/24`
  - PC3: `192.168.1.2/24`
- Подсеть B:
  - PC4: `192.168.2.1/24`
  - PC5: `192.168.2.2/24`
- Устройства: 2 коммутатора, Router0
- Настроена статическая маршрутизация:
- `ip route 192.168.1.0 255.255.255.0 via <IP_интерфейса>`
- `ip route 192.168.2.0 255.255.255.0 via <IP_интерфейса>`

- Результат: обмен трафиком между подсетями работает

---

## Задача 3: VLAN + DHCP + изоляция

**Цель:** Настроить динамическую IP-адресацию и изолировать трафик между отделами с помощью VLAN.

**Описание:**
- VLAN10 (бухгалтерия):
- PC6: DHCP → `192.168.10.2`
- PC7: DHCP → `192.168.10.3`
- VLAN20 (IT-отдел):
- PC8: DHCP → `192.168.20.2`
- PC9: DHCP → `192.168.20.3`
- DHCP на Router1 (использован `ip dhcp pool`)
- Изоляция между VLAN (без маршрутизации между ними)
- Результат:
- Каждая VLAN получила IP автоматически
- Устройства внутри одной VLAN видят друг друга
- Между VLAN нет доступа (без маршрута)

---

## Топология

![image](https://github.com/user-attachments/assets/c6709a8a-1515-4baf-a383-93579ed12114)

---

## Файлы

- `Usser_Yerbolat.pkt` — проект Cisco Packet Tracer
- `architecture.png` — скриншот схемы сети
- `README.md` — описание проекта

---

> Автор: Ерболат Уссер Ералханұлы  
> Год: 2025  
> Направление: DevOps / Computer Networks / Cisco Packet Tracer
