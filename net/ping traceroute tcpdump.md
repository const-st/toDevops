#### ping
-c N - количество запросов
-s M размер пакета в байтах
-D для каждого запроса проставлять timestamp
-I  iface> / ip с которого отправляем пинг
-O явно показать запрос без ответа
-i интервал запроса в секундах / частота
-a пинг с бипом )
-4/6 версия протокола
-f - интерфейс отправляет запросы с макс скоростью (sudo)
ping 181.121.45.13 -c 5 -s 800 -i 2 -D
[RIPE Atlas - RIPE Network Coordination Centre](https://atlas.ripe.net/results/maps/network-coverage/)
		--- 
#### traceroute/tracepath/mtr
порты по умолчанию в диапазон 33434-33534
-T -tcp
-u -udp
-P - порт
-I -iface
-a -ip address  с которого отправляются запросы

#### tcpdump
-i - выбрать интерфейс
-v/vv/vvv - уровень детализации
-host - фильтр по хостам src/dst
-port - по портам
-ip/udp/tcp/icmp/icmp6/proto N - по протоколу
-adn/or/not - операнды
-w -write куда то
`sudo tcpdump dst host 181.121.45.13`

