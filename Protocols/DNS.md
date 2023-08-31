# DNS

DNS-сервер — это специализированный компьютер (или группа), который хранит IP-адреса сайтов.

Основное предназначение DNS-серверов — хранение информации о доменах и ее предоставление по запросу пользователей, а также кэширование DNS-записей других серверов.

Resolver - DNS сервер провайдера 

Приоритет обращения:

1. Запрос в браузер, если в кеше системы/браузера остались значения для этого доменного имени, то получаем адрес
2. Браузер обращается к ресольверу(resolver),
3. 
4. 

## DNS record

__A__ - Address record(IPv4)
__AAAA__ - Address record(IPv6)
__CNAME__ - Canonical Name record
__MX__ - Mail Exchanger record
__NS__ - Nameserver record
__PTR__ - Pointer record
__SOA__ - Start of Authority record
__SRV__ - Secver location record
__TXT__ - Text record