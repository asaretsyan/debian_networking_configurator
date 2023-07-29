# Ansible проект для настройки сети в Linux (планируется)
*Примечание: Это описание представляет планируемый **Ansible** проект для настройки сетевых интерфейсов в **Linux** дистрибутивах на базе **Debian**. Разработка проекта в процессе и еще не реализована.*

## Цель проекта
Целью данного Ansible проекта является создание автоматизированного механизма для настройки сетевых параметров в операционных системах на базе **Debian**. При помощи **Ansible** и с использованием службы **networking** и файла **/etc/network/interfaces**, планируется обеспечить быструю и надежную настройку сетевых интерфейсов на различных узлах.

## Особенности проекта
1. **Гибкая конфигурация**: Проект будет предоставлять возможность выбора различных типов настройки сетевых интерфейсов, включая **bonding-интерфейсы** или **стандартные интерфейсы**.
2. **Dummy-интерфейсы**: Планируется включение или исключение **dummy-интерфейсов** в зависимости от потребностей.
3. **Централизованное управление**: Проект будет ориентирован на одновременную настройку нескольких хостов, что позволит упростить и ускорить процесс настройки сетевой инфраструктуры.
4. **Масштабируемость**: Предполагается, что проект будет легко масштабируемым и способным обслуживать большое количество хостов.
## Как будет работать проект
При запуске **Ansible playbook**, планируется использование модулей **Ansible** для конфигурирования сетевых параметров на целевых хостах. Проект будет читать предварительно определенные переменные, определяющие тип и параметры настройки сетевых интерфейсов, и применять соответствующие изменения на целевых узлах.

## Пример запуска
<code>ansible-playbook -i inventory/hosts site.yml -e "bond_ip=192.168.0.10 bond_netmask=255.255.255.0 dummy_ip=10.0.0.1 dummy_netmask=255.0.0.0 bond_slaves={{ ['eth3', 'eth5'] }} interfaces_txqueuelen={{ [1000, 2000] }} bond_dns_servers={{ ['8.8.8.8', '9.9.9.9'] }} bond_gateway=192.168.0.254"</code>
