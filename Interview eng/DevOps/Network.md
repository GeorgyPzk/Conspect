# OSI model (Basic Reference Model Open Systems Interconnection model)

## Levels model

1. Физический уровень (Physical layer)
2. Канальный уровень (Data link layer)
3. Сетевой уровень (Network layer)
4. Транспортный уровень (Transport layer)
5. Сеансовый уровень (Session layer)
6. Уровень представления (Presentation layer)
7. Прикладной уровень (Application layer)

- На седьмом уровне информация представляется в виде данных, на первом - в виде бит. 

- Уровни модели OSI можно условно разделить на две группы:

    - __Media Layers__ (L1, L2, L3) занимаются передачей информации (по кабелю или беспроводной сети), используются сетевыми устройствами, такими как коммутаторы, маршрутизаторы и т.п.

    - __Host Layers__ (L4, L5, L6, L7) используются непосредственно на устройствах, будь то стационарные компьютеры или мобильные устройства.

- Каждый уровень имеет свои PDU (Protocol Data Unit), представляемые в той форме, которая будет понятна на данном уровне и, возможно, на следующем до преобразования. Работа с чистыми данными происходит только на уровнях с пятого по седьмой.

- Модель OSI служит инструментом при диагностике сетей.

__Инкапсуляция__ - процесс, когда информация отправляется и переходит из данных в биты. Происходит с 7 до 1 уровня. На 1 уровне она максимальная.

__Декапсуляция__ - процесс, обратный инкапсуляции, когда информация из битов переходит в данные. 

### 1 - Physical layer

Первый уровень оперирует битами. Они передаются средствами передачи данных(провода, Wi-Fi, 4G, Blutooth)

### 2 - Data link layer

- Второй уровень решает проблему адресации при передаче информации. Канальный уровень получает биты и превращает их в кадры (frame, также «фреймы»). 

- На втором уровне OSI работают коммутаторы, их задача — передать сформированные кадры(frame) от одного устройства к другому, используя в качестве адресов только физические MAC-адреса.

- У канального уровня есть два подуровня — это MAC и LLC.

- На канальном уровне активно используется протокол ARP (Address Resolution Protocol — протокол определения адреса).

### 3 - Network layer

- Выполняет задачу маршрутизации. Для этой задачи были созданы устройства третьего уровня — маршрутизаторы (их еще называют роутерами).

- Маршрутизаторы получают MAC-адрес от коммутаторов с предыдущего уровня и строят маршрут от одного устройства к другому

### 4 - Transport layer

- Выполняет задачу транспортировки пакетов.

- Использует Протоколы: TCP, UDP

### 5 - Session layer

- Отвечает за поддержку сеанса или сессии связи.

- Оперирует чистыми данными, как и L6, L7. 

- Примером работы пятого уровня может служить видеозвонок по сети. Во время видеосвязи необходимо, чтобы два потока данных (аудио и видео) шли синхронно. Когда к разговору двоих человек прибавится третий — получится уже конференция. Задача пятого уровня — сделать так, чтобы собеседники могли понять, кто сейчас говорит.

### 6 - Presentation layer

- Отвечает за преобразование протоколов и кодирование/декодирование данных.

- Занимается представлением картинок (в JPEG, GIF и т.д.), а также видео-аудио (в MPEG, QuickTime). А помимо этого → шифрованием данных, когда при передаче их необходимо защитить.

### 7 - Application layer

-  Application layer -  это то, чем взаимодействуют пользователи, своего рода графический интерфейс всей модели OSI, с другими он взаимодействует по минимуму.

### Недостатки

- Вторым недостатком называют плохую технологию. Как основной довод в пользу того, что OSI — это плохая технология, приводят распространенность стека TCP/IP. Протоколы OSI часто дублируют другу друга, функции распределены по уровням неравнозначно, а одни и те же задачи могут быть решены на разных уровнях. 

- Не отражает действительность. В таких утверждениях есть доля истины, ведь уже на момент появления OSI другие компании были больше готовы работать с получившей широкое распространение моделью TCP/IP.

- Разделение на 7 уровней излишне. Уровни 5,6 избыточны.



# OSI model (Basic Reference Model Open Systems Interconnection model)

## Levels model

1. Physical Layer
2. Data Link Layer
3. Network Layer
4. Transport Layer
5. Session Layer
6. Presentation Layer
7. Application Layer

- At the L7, information is represented as data, while at the first level(L1), it is represented as bits.

- The OSI model levels can be divided into two groups:

    - __Media Layers__ (L1, L2, L3) are responsible for transmitting information (over cables or wireless networks) and are used by network devices such as switches, routers, and so on.

    - __Host Layers__ (L4, L5, L6, L7) are used on devices(computers or mobile devices).

- Each level has its Protocol Data Unit (PDU). Working with raw data only occurs at levels five through seven.

- The OSI model serves as a diagnostic tool for networks.

- __Encapsulation(инкапсуляция)__ is the process when information is sent and transform __from data to bits__. It exist from level 7 to level 1. At level 1, maximum form.

- __Decapsulation__ is the reverse process of encapsulation, where information transitions __from bits to data__.

### 1 - Physical Layer
- The first level operates with bits. They are transmitted using data transmission media (cables, Wi-Fi, 4G, Bluetooth).

### 2 - Data Link Layer
- The second level solve problem of addressing during information transmission. The Data Link Layer receives bits and converts them into frames.

- Their task being to pass the __formed frames__ from one device to another, using only physical MAC addresses as addresses.

- The Data Link Layer has __two sublevels__, which are __MAC__ and __LLC__.

- The ARP protocol (Address Resolution Protocol) is actively used at the Data Link Layer.

### 3 - Network Layer

- Solve __routing tasks__. Devices of the third level, known as __routers__, were created for this purpose.

- __Routers__ receive MAC addresses from switches on the previous level and __build a route__ from one device to another.

### 4 - Transport Layer

Performs packet transport tasks.

Uses Protocols: TCP, UDP.

### 5 - Session Layer

Responsible for supporting a communication session.

Operates with raw data, like L6 and L7.

An example of the fifth level's work could be a video call over the network. During a video call, it is necessary for two data streams (audio and video) to be synchronized. When a third person joins the conversation, it becomes a conference. The fifth level's task is to make it clear who is currently speaking.

### 6 - Presentation Layer

Responsible for protocol conversion and data encoding/decoding.

Deals with the representation of images (in JPEG, GIF, etc.) as well as audio-video (in MPEG, QuickTime). Additionally, it handles data encryption when protection is necessary during transmission.

### 7 - Application Layer

The Application Layer is what users interact with, serving as a kind of graphical interface for the entire OSI model. It interacts minimally with the other layers.

## Drawbacks

The second drawback is attributed to poor technology. As the main argument in favor of OSI being a poor technology, people often mention the prevalence of the TCP/IP stack. OSI protocols often duplicate each other, functions are unevenly distributed across layers, and the same tasks can be solved at different levels.

It doesn't reflect reality. There is some truth to these claims, as by the time OSI was introduced, other companies were more prepared to work with the widely adopted TCP/IP model.

The division into 7 layers is excessive. Levels 5 and 6 are redundant.


[Soure](https://selectel.ru/blog/osi-for-beginners/)