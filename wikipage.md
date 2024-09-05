<p>
  <ac:structured-macro ac:macro-id="6c917443-c190-4fde-9e0b-509af7ff7aab" ac:name="toc" ac:schema-version="1"/>
</p>
<p>
  <br/>
</p>
<p>
  <br/>
</p>
<ac:structured-macro ac:macro-id="34105c4f-bf4a-4698-9179-ceaad1b60b43" ac:name="panel" ac:schema-version="1">
  <ac:rich-text-body>
    <p>Fiddler - прокси, который работает с HTTP трафиком между Вашим компьютером и удаленным сервером, и позволяет инспектировать и менять его.</p>
    <p>С помощью анализа и редактирования трафика можно тестировать клиент и сервер независимо друг от друга, обеспечивать тестовые данные для различных кейсов, а также эмулировать различные ошибки/задержки при сетевом взаимодействии.</p>
    <p>
      <strong>
        <a href="https://www.telerik.com/download/fiddler">Скачать Fiddler Classic</a>
      </strong> (не перепутайте с Fiddler Everywhere <ac:emoticon ac:emoji-id="1f642" ac:name="slightly smiling face"/> )</p>
  </ac:rich-text-body>
</ac:structured-macro>
<p>
  <br/>
</p>
<h1>Общая настройка приложения</h1>
<p>Запустить <strong>Fiddler</strong>
  <br/>Перейти в меню <strong>Tools - Options... - Connections</strong>
</p>
<p>
  <ac:image>
    <ri:attachment ri:filename="image-2023-11-29_21-19-58.png"/>
  </ac:image>
</p>
<p>В поле <strong>Fiddler listens on port</strong> по умолчанию стоит порт 8888, можно оставить его же или указать любой свободный порт, например, 7777.</p>
<p>Снять чек-бокс<strong> Act as system proxy on startup</strong> (если он отмечен - Fiddler при запуске будет работать как системный прокси и перехватывать запросы большинства браузеров и других программ, что может повлиять на их работу). При необходимости можно включить обратно, поставив чек-бокс в меню <strong>File - Capture Traffic</strong>, клавишу <strong>F12</strong> или кнопку <strong>Capturing </strong>в левом нижнем углу.</p>
<p>
  <strong>Bypass Fiddler Classic for URLs that start with </strong>- сюда указываем хосты, трафик которых нужно игнорировать (например, если сервер начинает возвращать ошибку при включенном проксировании)</p>
<p>
  <span style="color: rgb(255,0,0);">
    <strong>После выполнения настроек перезапустить приложение</strong>
  </span>
</p>
<p>
  <br/>
</p>
<p>
  <br/>
</p>
<ac:structured-macro ac:macro-id="0b40b394-6480-4bdb-819e-b1f29fd3cac8" ac:name="info" ac:schema-version="1">
  <ac:parameter ac:name="title">Зашифрованный трафик</ac:parameter>
  <ac:rich-text-body>
    <p>Если в рамках проекта необходимо тестирование/перехват зашифрованного траффика по https, то необходимо выполнить следующую настройку (при этом могут быть проблемы с приложениями, использующими https, например, скайп на компьютере может отваливаться):</p>
    <ul>
      <li>Перейти в меню <strong>Tools - Options... - HTTPS</strong>,</li>
      <li>отметить чек-боксы <strong>Capture HTTPS CONNECTs</strong> и <strong>Decrypt HTTPS traffic</strong> - для того, чтобы Fiddler по умолчанию показывал зашифрованный трафик</li>
    </ul>
  </ac:rich-text-body>
</ac:structured-macro>
<p>В основном окне Fiddler включить режимы <strong>Stream</strong> и <strong>Decode</strong> для удобного отображения сессий.</p>
<p>
  <ac:image ac:height="97">
    <ri:attachment ri:filename="image-2023-10-9_19-6-51.png"/>
  </ac:image>
</p>
<p>
  <span style="color: rgb(255,0,0);">
    <strong>После выполнения настроек перезапустить приложение</strong>
  </span>
</p>
<p>
  <br/>
</p>
<p>
  <strong>Если сайт поддерживает tls выше версии 1.0, дополнительно добавить настройку:</strong>
</p>
<p>
  <strong>
    <ac:image>
      <ri:attachment ri:filename="image-2023-11-29_18-41-13.png"/>
    </ac:image>
  </strong>
</p>
<h1>Настройка фильтров</h1>
<p>Для того чтобы Fiddler показывал не все подряд проходящие через него запросы, можно настроить фильтры.</p>
<p>Открываем вкладку <strong>Filters</strong>, отмечаем чек-бокс <strong>Use Filters</strong>
</p>
<p>
  <u>
    <strong>Примеры фильтров:</strong>
  </u>
</p>
<ul>
  <li>Чтобы показывать запросы только для определенных хостов - в блоке <strong>Hosts </strong>в фильтре хоста выбираем пункт <strong>Show only the following Hosts</strong>, в поле фильтра добавляем список хостов, разделенных точкой с запятой (можно указывать IP-адрес или доменное имя, а также порты)</li>
</ul>
<p>
  <ac:image ac:height="187">
    <ri:attachment ri:filename="image-2023-10-9_19-11-3.png"/>
  </ac:image>
</p>
<ul>
  <li>Чтобы показывать только запросы, содержащие в URI определенный текст (например "mobilebanking") - в блоке <strong>Request Headers</strong> отмечаем чек-бокс <strong>Show only if URL contains</strong> и вписываем нужное значение</li>
</ul>
<p>Аналогичным образом можно настроить и другие фильтры</p>
<p>Чтобы применить фильтры, нажимаем на кнопку <strong>Actions</strong>, выбираем <strong>Run Filterset now</strong>
</p>
<p>
  <strong>
    <ac:image ac:height="242">
      <ri:attachment ri:filename="image-2023-10-9_19-11-25.png"/>
    </ac:image>
  </strong>
</p>
<h1>Просмотр запросов/ответов</h1>
<ac:structured-macro ac:macro-id="0bb7f60b-a38a-4028-8103-bce45505a29e" ac:name="info" ac:schema-version="1">
  <ac:rich-text-body>
    <p>Не забыть включить чек-бокс в меню <strong>File - Capture Traffic</strong>, или нажать клавишу <strong>F12,</strong> или нажать кнопку <strong>Capturing </strong>в левом нижнем углу</p>
  </ac:rich-text-body>
</ac:structured-macro>
<p>Для просмотра трафика необходимо в правой части экрана Fiddler открыть вкладку <strong>Inspectors</strong>
</p>
<p>В левой части экрана Fiddler отображаются HTTP сессии.</p>
<p>В правой верхней части отображаются запросы клиента к серверу, в правой нижней части - ответы сервера клиенту.</p>
<p>
  <ac:image ac:height="400">
    <ri:attachment ri:filename="image-2023-10-9_19-14-32.png"/>
  </ac:image>
</p>
<p>Различные режимы отображения в верхней и нижней панелях можно переключать вкладками, например:</p>
<ul>
  <li>
    <strong>TextView </strong>- показывает тело запроса</li>
  <li>
    <strong>Headers </strong>- показывает заголовки</li>
  <li>
    <strong>JSON </strong>- показывает json структуру в виде дерева (если в теле передаются данные в формате JSON)</li>
  <li>
    <strong>Raw </strong>- показывает запрос целиком в текстовом виде без какого-либо форматирования (включает стартовую строку, заголовки и тело).</li>
</ul>
<p>В режиме Raw, если тело достаточно длинное, то оно может отображаться не полностью. Чтобы отобразить его целиком, надо нажать правой кнопкой на содержимое запроса/ответа, и выключить пункт <strong>AutoTruncate </strong>(чтобы не обрезалось), и отметить пункт <strong>Word Wrap</strong> (чтобы переносились длинные строки).</p>
<p>Также можно выделять сессии в списке цветами для удобства. Для этого нажимаем на сессию в списке и нажимаем <strong>Ctrl+1</strong> (или другую цифру). Разные цифры выделяют разными цветами, 0 - снимает выделение.</p>
<p>
  <ac:image>
    <ri:attachment ri:filename="image-2023-10-9_19-17-55.png"/>
  </ac:image>
</p>
<h1>Перехват и редактирование запросов/ответов</h1>
<ac:structured-macro ac:macro-id="9055bb83-38b2-4a81-82a2-51a572c2318a" ac:name="info" ac:schema-version="1">
  <ac:rich-text-body>
    <p>Не забыть включить чек-бокс в меню <strong>File - Capture Traffic</strong>, или нажать клавишу <strong>F12,</strong> или нажать кнопку <strong>Capturing </strong>в левом нижнем углу</p>
    <p>
      <a href="https://www.telerik.com/blogs/breakpoints-in-fiddler">Подробнее о брейкпоинтах</a>
    </p>
  </ac:rich-text-body>
</ac:structured-macro>
<p>Для редактирования запросов/ответов необходимо установить брейкпоинт. Это можно сделать разными способами:</p>
<ul>
  <li>Ввести соответствующую команду в черное поле под списком сессий</li>
  <li>Установить с помощью фильтра (вкладка <strong>Filters</strong>, раздел <strong>Breakpoints</strong>)</li>
  <li>Установить с помощью скрипта</li>
  <li>Нажать кнопку <strong>Break </strong>в левом нижнем углу (Стрелка вверх - брейкпоинт перед запросом, стрелка вниз - брейкпоинт после получения ответа)</li>
</ul>
<p>
  <strong>
    <ac:image ac:height="79" ac:thumbnail="true">
      <ri:attachment ri:filename="image-2023-10-9_20-16-41.png"/>
    </ac:image>
  </strong>
</p>
<ul>
  <li>Включить правило в меню <strong>Rules </strong>→ <strong>Automatic BreakPoints</strong>
  </li>
</ul>
<p>
  <strong>
    <ac:image ac:height="250">
      <ri:attachment ri:filename="image-2023-10-9_19-30-37.png"/>
    </ac:image>
  </strong>
</p>
<p>
  <br/>
</p>
<p>Примеры команд для установки брейкпоинтов через командную строку:</p>
<p>
  <ac:image ac:height="99">
    <ri:attachment ri:filename="image-2023-10-9_20-24-17.png"/>
  </ac:image>
</p>
<ul>
  <li>"<strong>bpm</strong> [method]" - на запрос по HTTP методу (POST, GET и т.д.), например "bpm post" - будут останавливаться все запросы с методом POST</li>
  <li>"<strong>bpu </strong>[string]" - на запрос по URI, содержащему указанною строку, например "bpu mobilebanking" - будут останавливаться все запросы, у которых в URI содержится строка "mobilebanking"</li>
  <li>"<strong>bpafter </strong>[string]" - на ответ по URI, содержащему указанною строку</li>
</ul>
<p>Чтобы снять брейкпоинт, нужно ввести команду без параметра, например "bpm", "bpu", "bpafter".</p>
<p>После ввода команды нажимаем Enter. Под строкой ввода отобразится текст о том, что брейкпоинт был установлен/снят.</p>
<p>
  <ac:image ac:height="101">
    <ri:attachment ri:filename="image-2023-10-9_20-24-41.png"/>
  </ac:image>
</p>
<p>
  <a href="https://docs.telerik.com/fiddler/knowledge-base/quickexec">Подробнее о командах</a>
</p>
<p>
  <br/>
</p>
<h2>Брейкпоинт до выполнения запроса</h2>
<p>Позволяет изменить данные запроса перед его выполнением. Для этого выполняем:</p>
<ul>
  <li>В левой панели кликаем по перехваченному запросу</li>
  <li>В правой панели на вкладке <strong>Inspectors</strong> редактируем необходимые заголовки или тело запроса (на соответствующих вкладках в верхней половине правой панели)</li>
  <li>Нажимаем <strong>Break on Response</strong> - если дополнительно хотим установить брейкпоинт после получения ответа</li>
  <li>Нажимаем <strong style="letter-spacing: 0.0px;">Run to Completion</strong>
    <span style="letter-spacing: 0.0px;"> - если хотим получить ответ в браузере</span>
  </li>
</ul>
<p>
  <ac:image ac:height="400">
    <ri:attachment ri:filename="image-2023-10-9_20-15-29.png"/>
  </ac:image>
</p>
<p>
  <br/>
</p>
<h2>Брейкпоинт после получения ответа</h2>
<p>Позволяет изменить данные полученного ответа перед отправкой в браузер. Для этого выполняем:</p>
<ul>
  <li>В левой панели кликаем по перехваченному запросу</li>
  <li>В правой панели на вкладке <strong>Inspectors</strong> редактируем необходимые заголовки или тело ответа (на соответствующих вкладках в нижней половине правой панели)</li>
  <li>Нажимаем <strong>Run to Completion</strong>
  </li>
</ul>
<p>
  <u>
    <strong>
      <ac:image ac:height="400">
        <ri:attachment ri:filename="image-2023-10-9_20-27-37.png"/>
      </ac:image>
    </strong>
  </u>
</p>
<h1>Возврат заранее установленных ответов (Autoresponder)</h1>
<p>Fiddler может возвращать заранее подготовленные ответы автоматически, без отправки запроса на сервер. Для этого нужно создать определенное правило, на которое будет проверяться запрос, и задать ответ для такого запроса - <a href="https://docs.telerik.com/fiddler/knowledge-base/autoresponder">подробнее</a>.</p>
<p>Чтобы создать правило, открываем вкладку <strong>Autoresponder</strong>, в нижней части интерфейса заполняем блок <strong>Rule Editor:</strong>
</p>
<ul>
  <li>
    <strong>Request URL Pattern</strong> - задается правило в виде строки, по которому должен выбираться запрос клиента, на который будет установлен заранее подготовленный ответ. </li>
  <li>
    <strong>Local file to return</strong> - поле для выбора ответа из стандартных заготовленных ответов или создания собственного</li>
</ul>
<p>Для URL и тела можно использовать префиксы EXACT:, NOT:, REGEX:</p>
<p>
  <ac:image ac:height="212">
    <ri:attachment ri:filename="image-2023-10-9_20-40-14.png"/>
  </ac:image>
</p>
<h2>Активация правил</h2>
<ac:structured-macro ac:macro-id="79582c8d-8fd8-4aad-a50b-ed5309367313" ac:name="info" ac:schema-version="1">
  <ac:rich-text-body>
    <p>Не забыть включить чек-бокс в меню <strong>File - Capture Traffic</strong>, или нажать клавишу <strong>F12,</strong> или нажать кнопку <strong>Capturing </strong>в левом нижнем углу</p>
  </ac:rich-text-body>
</ac:structured-macro>
<p>Чтобы активировать автоматический возврат ответов, необходимо отметить чек-бокс <strong>Enable rules</strong>, а также чек-боксы требуемых правил.<br/>Попадающие под правила запросы не дойдут до сервера, Fiddler сам вернет на них заранее заданные ответы.</p>
<p>Запросы, не попадающие ни под одно правило, зависят от чек-бокса <strong>Unmatched requests passthrough</strong>. Если он отмечен, запросы дойдут до сервера как обычно, если не отмечен - запросы будут заблокированы (получат ответ "404 Fiddled")</p>
<h2>Настройка собственного ответа</h2>
<ul>
  <li>нажать <strong>Add Rule</strong>
  </li>
  <li>ввести правило в <strong>Request URL Pattern</strong>
  </li>
  <li>в поле <strong>Local file to return</strong> выбрать пункт <strong>Create New Response...</strong> </li>
</ul>
<p>
  <ac:image ac:height="400">
    <ri:attachment ri:filename="image-2023-10-9_20-42-25.png"/>
  </ac:image>
</p>
<ul>
  <li>нажать <strong>Save</strong> - открывается редактор ответа. В редакторе ответа выбираем нужный статус-код и подставляем тело ответа:</li>
</ul>
<p>
  <ac:image ac:height="250">
    <ri:attachment ri:filename="image-2023-10-9_20-45-38.png"/>
  </ac:image>
  <ac:image ac:height="250">
    <ri:attachment ri:filename="image-2023-10-9_20-47-25.png"/>
  </ac:image>
</p>
<ul>
  <li>нажать <strong>Save </strong>в окне редактора</li>
  <li>закрыть окно редактора</li>
  <li>включить чек-бокс <strong>Enable rules</strong>
  </li>
  <li>включить чек-бокс для созданного правила</li>
</ul>
<p>
  <ac:image ac:height="250">
    <ri:attachment ri:filename="image-2023-10-9_20-56-10.png"/>
  </ac:image>
</p>
<p>
  <u>
    <strong>Проверка выполненной настройки:</strong>
  </u>
</p>
<p>
  <ac:image ac:height="250">
    <ri:attachment ri:filename="image-2023-10-9_20-57-47.png"/>
  </ac:image>
</p>
<h2>Примеры правил</h2>
<p>
  <strong>Подходит любой запрос с методом POST:</strong>
</p>
<ac:structured-macro ac:macro-id="ad378951-4971-4379-a0a8-ec4e65df99e6" ac:name="code" ac:schema-version="1">
  <ac:plain-text-body><![CDATA[method:post]]></ac:plain-text-body>
</ac:structured-macro>
<p>
  <strong>Подходит любой запрос, у которого URL содержит строку "rest/clientcharge/getCharges":</strong>
</p>
<ac:structured-macro ac:macro-id="f1b3acdd-4ecc-46be-b267-9ff511f031c3" ac:name="code" ac:schema-version="1">
  <ac:plain-text-body><![CDATA[rest/clientcharge/getCharges]]></ac:plain-text-body>
</ac:structured-macro>
<p>
  <strong>Подходит любой запрос, у которого URL содержит строку "rest/clientcharge/getCharges" и тело запроса содержит строку "chargeType":</strong>
  <br/>(первый пробел в правиле разделяет URL и тело)</p>
<ac:structured-macro ac:macro-id="40b4bd3d-6975-48d6-855b-6757fe8f0445" ac:name="code" ac:schema-version="1">
  <ac:plain-text-body><![CDATA[URLWithBody:rest/clientcharge/getCharges chargeType]]></ac:plain-text-body>
</ac:structured-macro>
<p>
  <br/>
  <strong>Подходит любой запрос у которого URL точно равен заданной строке и тело подходит под указанное регулярное выражение:</strong>
</p>
<ac:structured-macro ac:macro-id="9524bf79-8119-40ad-b483-6fae976162cc" ac:name="code" ac:schema-version="1">
  <ac:plain-text-body><![CDATA[URLWithBody:EXACT:http://wasrv.bscmsc.ru/bcsmbs/rest/clientcharge/getCharges REGEX:^.*BodyText.*$]]></ac:plain-text-body>
</ac:structured-macro>
<h2>Эмуляция ошибок транспортного уровня сети</h2>
<p>Хотя Fiddler не предназначен для этого, тем не менее с помощью него можно проверить пару простых кейсов. Для этого в <strong>Autoresponser </strong>можно создать правило со специальным ответом.</p>
<p>Само правило указываем любое (т.е. на какой запрос требуется оборвать соединение).</p>
<p>В качестве ответа устанавливаем соответствующую команду</p>
<p>
  <ac:image>
    <ri:attachment ri:filename="image-2023-10-9_21-26-42.png"/>
  </ac:image>
</p>
<h3>Обрыв соединения</h3>
<p>Fiddler пришлет на клиент TCP-пакет с флагом RST. Клиент выдаст "SocketException: Connection reset" или что-то подобное (зависит от реализации клиента)</p>
<ac:structured-macro ac:macro-id="7acd0619-2ec1-43c0-972f-78a7bbad519c" ac:name="code" ac:schema-version="1">
  <ac:plain-text-body><![CDATA[*reset]]></ac:plain-text-body>
</ac:structured-macro>
<h3>Закрытие соединения</h3>
<p>Fiddler пришлет на клиент TCP-пакет с флагом FIN. Клиент выдаст "IOException: unexpected end of stream" или что-то подобное (зависит от реализации клиента)</p>
<ac:structured-macro ac:macro-id="d744bf39-2b6d-4ba0-a61b-beb2a991487f" ac:name="code" ac:schema-version="1">
  <ac:plain-text-body><![CDATA[*drop]]></ac:plain-text-body>
</ac:structured-macro>
<p>
  <br/>Для работы с TCP (и другими протоколами) можно использовать другие инструменты для анализа трафика, например Wireshark.</p>
<h1>Отправка произвольных запросов (Composer)</h1>
<p>Fiddler может отправлять произвольные HTTP запросы</p>
<p>Для этого открываем вкладку <strong>Composer</strong>, выбираем раздел <strong>Raw </strong>или <strong>Parsed</strong>, вводим запрос и нажимаем кнопку <strong>Execute </strong>- запрос будет отправлен и отобразится в списке сессий.</p>
<p>Оба раздела <strong>Raw </strong>или <strong>Parsed </strong>работают одинаково, разница только в отображении + при отправке из раздела <strong>Parsed </strong>запросы могут сохраняться в историю (блок <strong>History </strong>справа), чтобы потом не вводить их заново.</p>
<p>В разделе <strong>Raw </strong>запрос вводится как есть в текстовом виде:</p>
<p>
  <ac:image>
    <ri:attachment ri:filename="image-2023-10-9_21-12-8.png"/>
  </ac:image>
</p>
<p>В разделе <strong>Parsed </strong>нужно отдельно выбрать HTTP метод, URL, версию протокола, заголовки и тело запроса</p>
<p>
  <br/>
</p>
