## Часть 1. Установка ОС

- Информация о версии ОС.

![image-20240131225856089](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240131225856089.png)



## Часть 2. Создание пользователя

- Вывод команды cat /etc/passwd  после добавления нового пользователя "runcelgh"(изначальный пользователь seymourghis)

![image-20240131231343007](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240131231343007.png)



## Часть 3. Настройка сети ОС

- Изменение hostname'а.

![image-20240131232042178](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240131232042178.png)

- Установка временной зоны.

![image-20240131232845143](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240131232845143.png)

- Список названий сетевых интерфейсов 

![image-20240131233209178](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240131233209178.png)

- Интерфейс **lo** - это локальная петля, которая имеет IP-адрес 127.0.0.1 и предназначена для сетевого доступа к своему же компьютеру

- Ip адрес текущего устройства

![image-20240201001203509](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240201001203509.png)

- **Dynamic Host Configuration Protocol (DHCP)** — протокол, позволяющий автоматически настраивать сетевые параметры компьютера, такие как IP-адрес, маска подсети, шлюз по умолчанию и DNS-серверы.

- Внешний адрес шлюза

![image-20240201002509913](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240201002509913.png)

- Внутренний адрес шлюза

![image-20240201002718538](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240201002718538.png)

- Заданные статично в конфигурационный файл ip gw и DNS(сам файл 00-installer-config.yaml был изменён через vim)

![image-20240203164413362](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240203164413362.png)

- После изменения конфигурации обязательно нужно выполнить команду netplan apply



- Пинг на 1.1.1.1 и ya.ru для проверки сети

![image-20240203164724394](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240203164724394.png)



## Часть 4. Обновление ОС

![image-20240203193435073](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240203193435073.png)



## Часть 5. Использование команды sudo

- Добавляем пользователя runcelgh в группу sudo выполняя: sudo usermod -G sudo runcelgh 
- С помощью команды sudo -i -U runcelgh проверяем может ли пользователь вызывать sudo

![image-20240203200852400](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240203200852400.png)



- sudo — это утилита, предоставляющая привилегии root для выполнения административных операций в соответствии со своими настройками. Она позволяет легко контролировать доступ к важным приложениям в системе. По умолчанию, при установке Ubuntu первому пользователю (тому, который создаётся во время установки) предоставляются полные права на использование sudo. Т.е. фактически первый пользователь обладает той же свободой действий, что и root.

![image-20240203201745351](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240203201745351.png)



## Часть 6. Установка и настройка службы времени

- Часовой пояс UTC+7

![image-20240203202740121](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240203202740121.png)

- Вывод timedatectl show

![image-20240203202546735](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240203202546735.png)

## Часть 7. Установка и использование текстовых редакторов

- VIM



![image-20240203203048139](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240203203048139.png)

- Для выхода с сохранением ":wq"

  

![image-20240203203542883](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240203203542883.png)

- Для выхода без сохранения "q!"



![image-20240204170318666](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204170318666.png)

- Для поиска вниз используется "/word_to_find", вверх используется "?word_to_find"
- Также для поиска одного символа можно использовать "f"



![image-20240204171220369](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204171220369.png)

- Для поиска и замены существует конструкция ":%s/word_to_change/new_word"



- Nano

![image-20240204171921013](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204171921013.png)

- Для сохранения сочетание клавиш ctrl+o
- Для закрытия ctrl+x

![image-20240204172045648](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204172045648.png)

- Для закрытия без сохранения изменений нужно просто закрыть редактор сочетанием из прошлого пункта и отказаться от сохранения нажав "n"

![image-20240204172148496](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204172148496.png)

![image-20240204172611426](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204172611426.png)

- Для поиска в нано используется сочетание клавиш ctrl+w после чего нужно ввести искомый текст и нажать enter(при этом что бы дальше листать совпадения можно использовать как повторное применение ctrl+w, enter так и alt+w)



![image-20240204174524882](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204174524882.png)

- Для поиска и замены использовать ctrl+\(сначала запрашивает что искать, потом на что менять и проходится по всем совпадениям предлагая заменить, можно менять по одному а можно сразу все)



- JOE

![image-20240204174904692](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204174904692.png)

![image-20240204175025841](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204175025841.png)

- Для выхода - ctrl+k и затем q, редактор предложит сохранить изменения если они были таким образом для выхода с сохранением жмём y или n что бы отказаться от сохранения изменений

![image-20240204175128823](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204175128823.png)

![image-20240204180030456](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204180030456.png)

- Для поиска ввести ctrl+k затем f и искомый текст



![image-20240204180126693](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204180126693.png)

- То же для поиска и замены только, при поиске выбрать пункт Replace и указать заменяемый текст



## Часть 8. Установка и базовая настройка сервиса SSHD

- sudo apt-get install ssh для установки sshd
- sudo systemctl enable ssh для включения автостарта и systemctl status ssh для проверки работы

![image-20240204181243370](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204181243370.png)

- sudo nano /etc/ssh/sshd_config и замена port 22 на port 2022
- systemctl restart sshd - перезапуск службы для обновления порта

![image-20240204210744619](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204210744619.png)

- ps утилита которая позволяет отображать процессы запущенные на машине, также здесь используется флаг -C который позволяет отобразить процессы по названию в нашем случае sshd

![image-20240204211515737](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240204211515737.png)

- Вывод netstat -tan

- netstat - утилита для вывода информации о сетевых подключениях, портах и процессах которые их используют
- флаг - a(all) отображает все подключенные и ожидаемые сокеты
- флаг -t(TCP) ограничивает отображение только до TCP сокетов
- флаг -n(numeric)показывает IPv4 адреса в точечно-десятичном формате

- proto - используемый протокол - в нашем случае TCP(*Transmission Control Protocol* — протокол управления передачей)
- recv-q - очередь приёма, то есть входящие байты которые были получены, буферизованы и ожидают локальной обработки процессом который использует это подключение
- send-q - очередь отправления. то есть байты ожидающие отправки
- local address - это данные об адресе локального конца соединения(в нашем случае 0.0.0.0 означает маршрут по умолчанию)
- foreign address - адрес и порт удалённого конца соединения 
- state - состояние локального сокета(LISTEN- этот сокет ожидает запроса на подключение)





## Часть 9. Установка и использование утилит top, htop

-  Утилиты уже были установлены в системе

### Top

![image-20240205161335421](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205161335421.png)

- uptime - 7 min
- 2 пользователя

- общая нагрузка - 0.08 0.11 0.08
- общее кол-во процессов - 113
- загрузка ЦП:  0.2%
- загрузка памяти: 661.8/6139.7
- pid процесса занимающего больше всего памяти - 370(нажать M для сортировки по %MEM)

- pid процесса, занимающего больше всего процессорного времени - 1708(нажать P для сортировки по %CPU)

### Htop

- сортировка по PID командой htop --sort-key PID

![image-20240205170628633](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205170628633.png)



- сортировка командой htop --sort-key PERCENT_CPU

![image-20240205170724036](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205170724036.png)

- сортировка командой htop --sort-key PERCENT_MEM

![image-20240205170954632](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205170954632.png)

- сортировка командой htop --sort-key TIME

![image-20240205171046285](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205171046285.png)

- фильтрация по sshd через: f4 и ввод sshd

![image-20240205171427015](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205171427015.png)

- фильтрация по sshd через: f3 и ввод syslog

![image-20240205174334122](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205174334122.png)

- нажав f2 можно попасть в меню настройки утилиты где мы и добавим отображение hostname, clock, uptime

![image-20240205174552642](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205174552642.png)





## Часть 10. Использование утилиты fdisk

- /dev/sda2 - размер 25 ГБ, 52422656 секторов, swap - 4 ГБ



## Часть 11. Использование утилиты df

- размер - 25623780
- занято - 7033884
- свободно - 17262948
- процент использования - 29 
- единица измерения 1 килобайт

![image-20240205181712086](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205181712086.png)

#### Добавим флаги -Th

- размер - 25 Гб
- занято  - 6.8 Гб
- свободно - 17 Гб
- процент использования - 29
- тип файловой системы - ext4

![image-20240205182145188](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205182145188.png)



## Часть 12. Использование утилиты du

- /home - 168 Кб

![image-20240205182903124](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205182903124.png)

- /var - 722 Мб

![image-20240205182839152](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205182839152.png)

- /var/log - 61 Мб

![image-20240205182819086](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205182819086.png)

- sudo du -h /var/log/*

![image-20240205183012019](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205183012019.png)



## Часть 13. Установки и использование утилиты ncdu

- установка

![image-20240205183140797](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205183140797.png)

- ncdu ../../

![image-20240205183422488](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205183422488.png)

- /home -164 KiB
- /var - 717.3 MiB
- /var/log - 60.8 MiB

![image-20240205183535961](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205183535961.png)





## Часть 14. Работа с системными журналами

- sudo cat /var/log/dmesg
- sudo cat /var/log/syslog
- sudo cat /var/log/auth.log

- последний вход

![image-20240205184948796](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205184948796.png)

- отчёт о рестарте 

![image-20240205185311067](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205185311067.png)



## Часть 15. Использование планировщика заданий CRON

- логи исполнения uptime

![image-20240205193306771](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205193306771.png)

- отображение отсутствия заданий CRON

![image-20240205193604908](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20240205193604908.png)