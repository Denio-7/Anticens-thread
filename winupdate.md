        
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Предисловие**
   
Данный способ пускает трафик по пути Система->Клиент прокси->Локальный прокси сервер->Интернет. По какой-то причине это приводит к разблокировке обновлений шиндоус без необходимости менять IP-адрес. Поскольку все события происходят на локалхосте, шифрование отключено для максимальной производительности. Ссылки на софт из архивов внизу. Пока проверено только на Windows 10 LTSC.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Обход блокировок обновлений Windows**

- Скачиваешь: https://github.com/simple-2ch/thread/raw/main/Files/WindowsUpdate.zip
- Извлекаешь содержимое архива в корень диска С или любую папку путь к которой не содержит пробелов.
- В извлечённой папке WindowsUpdate запускаешь create-sslocal.bat от имени Администратора.
- В окне NSSM service installer указываешь путь к файлу ssserver.exe и жмёшь Install service
![alt text](https://github.com/simple-2ch/thread/blob/main/Files/img/wu1.jpg?raw=true)
- Если всё успешно, в консоле получаешь такой вывод:
![alt text](https://github.com/simple-2ch/thread/blob/main/Files/img/wu2.jpg?raw=true)
- Скачиваешь: https://github.com/simple-2ch/thread/raw/main/Files/ShadowsocksV2Ray.zip
- Извлекаешь содержимое архива, запускаешь Shadowsocks.exe, открывшееся окно закрываешь.
- Копируешь строку: **`ss://bm9uZToxMjM0NTY3ODk@127.0.1.1:8035/#Windows+Update`**
- В правом нижнем углу экрана должна появиться серая стрелка, кликаешь по ней правой кнопкой мыши.
- Наводишь на Серверы, кликаешь Импорт адреса из буфера обмена, подтверждаешь добавление, последующие окна закрываешь.
- Наводишь на Системный прокси-сервер, кликаешь Для всей системы.
- Заходишь в приложение настройки и проверяешь обновления. Должно начаться скачивание.

Если паранойя не отпускает, bat файлы можно открыть блокнотом и копипастить команды консоль, запущенную от имени Администратора. Для удаления сервиса запустить delete-sslocal.bat и удалить папку WindowsUpdate.

ssserver.exe: https://github.com/shadowsocks/shadowsocks-rust/releases/tag/v1.15.3 <br>
nssm.exe: https://nssm.cc/download <br>
Клиент Windows: https://github.com/shadowsocks/shadowsocks-windows/releases/latest (Shadowsocks-X.X.X.X.zip) <br>
Плагин Windows: https://github.com/shadowsocks/v2ray-plugin/releases/latest (v2ray-plugin-windows-amd64-vX.X.X.tar.gz)
