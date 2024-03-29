# Архитектура OS Linux

[some link](https://serverspace.ru/support/help/struktura-fajlovoj-sistemy-linux/)

Архитектура ОС UNIX - многоуровневая. На нижнем уровне работает ядро операционной системы. Функции ядра доступны через интерфейс системных вызовов, образующих второй уровень. На следующем уровне работают командные интерпретаторы, команды и утилиты системного администрирования, коммуникационные драйверы и протоколы, - все то, что обычно относят к системному программному обеспечению. Наконец, внешний уровень образуют прикладные программы пользователя, сетевые и другие коммуникационные службы, СУБД и утилиты.

1. Ядро (лежит в /boot)
2. Интерфейс системных вызовов(обращается к ядру)
3. Командные интерпретаторы, команды и утилиты системного администрирования
4. Программы пользователя и другое

Ядро - лежит в /boot/

Загрузчик - 

## Файловая система 

`/etc` - конфигурационные файлы большинства системных утилит и программ. Редактирование их приносит изменения для всех пользователей.

`/dev` - файлы физических устройств(аппаратного обеспечения). Для каждой папки свое устройство. Ввести `df` посмотреть информацию о устройствах

`/proc` - хранятся файлы с состоянии системы, данные о ядре. Например данные о процессоре, частоту (нагрузку, вроде, посмотреть нельзя, скорее что то вроде логов).
/proc/net/dev - список сетевых интерфейсов и статистику по ним.

`/sys` -  содержит информацию об инициализированных устройствах.
Заряд батареи cat `/sys/class/power_supply/BAT0/charge_full`. 
Классификация по шине `/sys/bus`. Основной каталог `/sys/devices`.

`/lib` - содержит библиотеки

`/var` - содержит переменные для системы и приложений

Программы в Linux не могут обращаться к ядру системы напрямую. Но для получения информации от ядра есть несколько директорий с помощью которых любая программа или пользователь могут получить данные о состоянии компьютера и ядра. Это файловая система proc и sys.

# Зачем нужны Unix(Linux) системы

Unix система первая многопользовательская система. Много либов для сервером, удобно работать на серверах.

# Сontainerization Linux

## Контейнеры в Linux без Docker

### Linux upstream containers(namespaces + cgroups)

__Namespace__ - гарантируют, что процесс будет работать с собственным представлением системы. Существует несколько типов пространств имен:

- Файловая система (mount, mnt) – изолирует файловую систему

- UTS (UNIX Time-Sharing, uts) – изолирует хостнейм и доменное имя

- Идентификатор процессов (process identifier, pid) – изолирует процессы

- Сеть (network, net) – изолирует сетевые интерфейсы

- Межпроцессное взаимодействие (ipc) – изолирует конкурирующее взаимодействие процессами

- Пользовательские идентификаторы (user) – изолирует ID пользователей и групп

__Cgroups__ — аббревиатура от Linux «control groups». Определяется как функция ядра Linux, контролирующая распределение ресурсов для пользовательских процессов. Гарантируют, что процесс не будет конкурировать за ресурсы, зарезервированные за другими процессами. Они ограничивают (контролируют) объем ресурсов, который процесс может потреблять – ЦПУ, ОЗУ, пропускную способность сети и др.

__chroot__ - может использоваться для изоляции, но лучше mount namespace(выше безопасность). Операция изменения корневого каталога в Unix-подобных операционных системах. Программа, запущенная с изменённым корневым каталогом, будет иметь доступ только к файлам, содержащимся в данном каталоге. Поэтому, если нужно обеспечить программе доступ к другим каталогам или файловым системам (например, /proc), нужно заранее примонтировать в целевом каталоге необходимые каталоги или устройства.



# Netstat

[link](https://itproffi.ru/otslezhivanie-sostoyaniya-seti-v-linux-komanda-netstat/)

`netstat -nap` - показывает список сетевых процессов. Список программ и их хостов в сети.

`netstat -nap | grep LISTEN` - список открытых портов с подключением

`netstat -i` - состояние сетевых интерфейсов и счетчиков трафика

`netstat -а` - процессы, которые активных соединений не имеют, но слушают порты.

`sudo netstat -lp` - Активные соединения с интернетом (only servers). 
Чтобы иметь представление о конкретных процессах или демонах, слушающих соединения (порты) в системе, следует воспользоваться ключами -l и -p. `-l` выводит только слушающие порты, `-l` идентификации процесса/демона.

`netstat -s` - статистика сетевых протоколов

`netstat -r -n` - таблица маршрутизации


# Linux logs path

/var/log


# Soft Link/Hard link 

__Soft Link__ - указатель, который связывает имя файла с путем, содержит в себе имя файла и путь(каталог).(является файлом)

__Hard link__ - Файл в файловой системе - это в основном ссылка на индекс. Жесткая ссылка затем создает другой файл со ссылкой на тот же основной индекс. т.е. копирует значения файла.

Жесткие ссылки действительны только в одной файловой системе. Символьные ссылки могут охватывать файловые системы, так как они просто являются именем другого файла.


# Соединить 2 VM в одну сеть

В облаках есть функция `Add peering`, соединяет 2 локальные сети в одну. Можно секюрно пропинговать


# zombie process

Процесс не работающий, но отмечающийся в списке процессов. Может получиться, если например если кильнули основной процесс и остался дочерний, он и может стать zombie

# Ctrl+C Ctrl+Z

`Ctrl+C` - останавливает процесс. Послылает сигнал(SIGINT) программе на прерывание работы.

`Ctrt+Z` - ставит на паузу, он остается в системе, но замораживается. 

`Ctrl+D` - Выход из программы/терминала


# SWAP



# File permissions

`ls -l` - показать файлы и папки с правами

пример: drwxr-xr-x 6 archie users  4096 июл  5 17:37 Документы
`drwxrwxrwx+`

__Первый символ__ сообщает нам о типе, а именно '-' обозначает обычный файл, 'd' — каталог, 'p' — именованный канал, 'l' — символическую ссылку, 'c' и 'b' — символьные и блочные файлы устройств, 's' — сокет, 'D' - дверь.

__Второй блок символов__ - Разрешения, которые имеет владелец к файлу. (2,3,4 символы)

__Третий блок символов__ - Разрешения, которые имеет группа к файлу (5,6,7 символы)

__Четвертый блок символов__ - Разрешения, которые имеют все остальные пользователи к файлу. (8,9,10 символы)

__Последний символ__ - Одиночный символ, который указывает на применение альтернативного метода доступа. `Пробел` указывает на отсутствие альтернативного метода доступа. Символ `.` обозначает файл с контекстом безопасности, но без другого альтернативного метода доступа. Файл с любой другой комбинацией альтернативных методов доступа помечается символом `+`, например в случае

`-` - файл не может быть прочитан/изменен/выполнен.

`r` - файл можно прочитать. Не может выполнить ls в Документах, но если он знает имя существующего файла, то может изменять файлы, если позволяет разрешение.

`w` - файл может быть изменён. В случае папки - удалено, переименовано и удалено.

`x` - файл может быть выполнен.


## chmod

### chmod метод через разрешения
chmod кто=разрешения имя_файла

Кто:
u (user): пользователь, который является владельцем файла.
g (group): группа пользователей, которой принадлежит этот файл.
o (other): другие пользователи, то есть все остальные.
a (all): все сразу; используйте вместо ugo.

### chmod - Числовой метод

`chmod 754 filename`  

- __Первая цифра__ - права доступа для владельца(User)
- __Вторая цифра__ - права доступа для группы(Groupe)
- __Третья цифра__ - для всех остальных(world)


# Swappiness

Параметр vm.swappiness задаёт процент свободной оперативной памяти, при котором начинает использоваться раздел подкачки. Необходимо открыть файл `/etc/sysctl.conf`

По умолчанию vm.swappiness равен 60. Т.е. если осталось менее 40% свободной оперативной памяти, то начинает использоваться swap раздел.

# stdin, stdout и stderr

stdin - входной поток (команды)

stdout - выходной поток

stderr - поток out для ошибки

__Как перенаправить одновременно stderr и stdin?__ - думаю не спросят




