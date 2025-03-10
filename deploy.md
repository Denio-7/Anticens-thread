        
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Предисловие**

VPS - это удалённый компьютер (сервер), через который ты будешь ходить в интернет для обхода блокировок. Арендовать VPS можно здесь за рубли: https://vps.today или тут за крипту: https://bitcoin-vps.com (https://kycnot.me для любителей манянимной крипты). Соответственно выбираем из иностранных. Мощность компьютера здесь не важна. Смотрим прежде всего на скорость интернета и объём трафика. Общая последовательность действий такова. Регистрируешься у выбранного провайдера VPS, оплачиваешь один из тарифов. Инструкция адаптирована для ОС Ubuntu или Debian, поэтому выбирай одну из них при оформлении. На почту придёт письмо с IP-адресом сервера, логином и паролем (именно к серверу, а не к аккаунту на сайте).

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Простое создание собственного сервера ShadowsocksRust + Xray**

- Ты купил VPS и уже пришло письмо с IP-адресом, логином и паролем сервера.
- Скачиваешь: https://github.com/simple-2ch/thread/raw/main/Files/PuTTY.exe
- Запускаешь PuTTY.exe. В поле Host Name (or IP address) вводишь IP-адрес твоего сервера и нажимаешь Open.
- Откроется черное окно и окно подтверждения подключения, где нужно нажать Accept.
- В появившуюся строку "login as:" вводишь логин сервера из письма, нажимаешь Enter. Копируешь пароль к серверу.
- В строке "имя_пользователя@айпи_адрес's password:" нажимаешь левую кнопку мыши, затем правую кнопку мыши, далее Enter.
- Появится строка типа "имя_пользователя@название_сервера:"
- Вводишь **`sudo su`** и нажимаешь Enter. Если спросит пароль нажимаешь правую кнопку мыши, затем Enter.
- Копируешь строку: **`bash <(wget -qO- "https://github.com/simple-2ch/thread/raw/main/Files/Deploy.sh")`**
- В черном окне нажимаешь левую кнопку мыши, затем правую кнопку мыши, далее Enter. Ждёшь...
- На красном фоне появится строка типа `ss://Y2hhY2...../?plugin=xray%3bmode=grpc`, аккуратно выделяешь её левой кнопкой мыши.
- Открываешь любой текстовый файл на своём компьютере, жмёшь Ctrl+V, видишь копию строки, сохраняешь. **Сервер готов.**
- Скачиваешь: https://github.com/simple-2ch/thread/raw/main/Files/ShadowsocksXray.zip
- Извлекаешь содержимое архива, запускаешь Shadowsocks.exe, открывшееся окно закрываешь.
- В правом нижнем углу экрана должна появиться серая стрелка, кликаешь по ней правой кнопкой мыши.
- Наводишь на Серверы, кликаешь Импорт адреса из буфера обмена, подтверждаешь добавление, последующие окна закрываешь.
- Наводишь на Системный прокси-сервер, кликаешь Для всей системы.

**Готово!** Здесь https://browserleaks.com/ip должен увидеть адрес арендованного сервера. Черное окно закрываешь и подтверждаешь закрытие. Отправлять трафик других программ через созданный сервер можно с помощью этого: https://rutracker.org/forum/tracker.php?nm=proxifier Что-то не работает? Спрашивай в треде, прикладывая скриншоты. Если работает, тоже отпиши для статистики.

**Настройка на Android** <br>
Устанавливаешь: https://github.com/shadowsocks/shadowsocks-android/releases/latest (shadowsocks--universal-vX.X.X.apk) и плагин https://github.com/teddysun/xray-plugin-android/releases/latest (xray-plugin-universal-vX.X.X.apk). Далее перекидываешь свой ключ на смартфон, копируешь его. Открываешь приложение Shadowsocks, нажимаешь на + , выбираешь Импортировать из буфера обмена, кликаешь на строку сервера. Активный ключ пометится слева зелёной полоской. Нажимаешь на перечёркнутую стрелку. Приложение Shadowsocks имеет ещё много разных настроек, которые ты можешь изучить сам. 

**Настройка на Linux** <br>
Клиент с GUI для Линуксогоспод: https://github.com/spyophobia/shadowsocks-gtk-rs и плагин https://github.com/teddysun/xray-plugin/releases/latest (xray-plugin-linux-amd64-vX.X.X.tar.gz). Вы у мамы умненькие поэтому разберётесь самостоятельно. 

**Настройка на MacOS** <br>
Устанавливаешь: https://github.com/shadowsocks/ShadowsocksX-NG/releases/latest и скачиваешь плагин https://github.com/teddysun/xray-plugin/releases/latest (для M1, M2 и т.д.: xray-plugin-darwin-arm64-vX.X.X.tar.gz) или (для Intel: xray-plugin-darwin-amd64-vX.X.X.tar.gz). Плагин нужно переименовать в xray и положить в директорию ~/Library/Application Support/ShadowsocksX-NG/plugins/ Подробнее об этом здесь: https://github.com/shadowsocks/ShadowsocksX-NG/wiki/SIP003-Plugin

**Настройка на iOS** <br>
Возможно заработает с Shadowrocket (https://github.com/teddysun/xray-plugin/issues/1 смотрим перевод заголовка). Ждём подтверждения от пользователей Apple GayPhone.

P.S. <br>
Если мучает паранойя, то можешь скачать необходимые программы с официальных источников или магазинов приложений, собрав всё самостоятельно. Пароль доступа случайно генерируется ядром линукса при развёртывании. Простой доступ к ключу получаешь только при завершении создания сервера в строке на красном фоне. При его потере, легче будет повторно выполнить вышеуказанную инструкцию с генерацией нового ключа.

PuTTY: https://ru.wikipedia.org/wiki/PuTTY <br>
Shadowsocks: https://github.com/shadowsocks/shadowsocks-rust <br>
Xray: https://github.com/teddysun/xray-plugin <br>
Скрипт: https://github.com/simple-2ch/thread/raw/main/Files/Deploy.sh <br>
Клиент Windows: https://github.com/shadowsocks/shadowsocks-windows/releases/latest (Shadowsocks-X.X.X.X.zip) <br>
Плагин Windows: https://github.com/teddysun/xray-plugin/releases/latest (xray-plugin-windows-amd64-vX.X.X.tar.gz )
