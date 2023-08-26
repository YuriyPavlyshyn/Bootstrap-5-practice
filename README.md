# Bootstrap 5 (фремворк)
---
Файл "index2.html" -> містить практично всі можливі елемементи фреймворку 
(готові для використання в практичних умовах)
---
### Завантаження та підключення
~~~
!!! Даний фремворк потрібен у тому разі коли у нас немає створеного макету сайту.

!!! Фреймворк використовує підхід: "mobile-first".

!!! Інсталювати пакети та модулі bootstrap через Node.js для проекту:
npm install bootstrap
(фактично застосовує усі пакети, - тоді коли увесь проект грунтується лише на 
даному фреймворку)

!!! Встановлення bootstrap у своїх програмах на базі Node.js із пакетом "yarn":
yarn add bootstrap

!!! IE в bootstrap 5 не підтримується, якщо з ресурсом працюватиме значна кількість 
юзерів, що користуються IE -> використовувати Bootstrap 4.

!!! Перед початком налаштування проекту використовувати усі плагіни bootstrap  
(підключати), однак мінімізовані версії файлів.
~~~
### Підключення фреймворку через CDN (за допомогою зовнішніх серверів)
~~~
1. Заходимо на офіційний сайт фреймворку - https://getbootstrap.com/docs/5.3/
getting-started/introduction/
2. Копіюємо таблицю стилів зі сторінки:
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel=
"stylesheet"integrity="sha384-4bw+/aepP/YC94hEpVNVgiZdgIC5+VKNBQNGCHeKRQN+PtmoHDEXuppvnDJzQIu9" 
crossorigin="anonymous">
3. Вставляємо дану лінку в <head> HTML документу
4. Копіюємо "Bundle" для JS:
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/js/bootstrap.bundle.min.js"
integrity="sha384-HwwvtgBNo3bZJJLYd8oVXjrBZt8cqVSpeBNS5n7C8IVInixGAoxmnlMuBnhbgrkm"
crossorigin="anonymous"></script>
5. Вставляємо перед закриваючим тегом <body> в HTML документі.

Якщо ми хочемо підключати в проекті свої стилі їх потрібно підключати в <head>, після таблиці 
стилів bootstrap, які там підключені:
<link rel="stylesheet" href="site/css/style2.css">

Bootstrap 5 використовує бібліотеку: "Popper", яка автоматично підключається з підключеням 
"Bundle JS". 

<meta name="viewport" ...> -> потрібен для того щоб сайт коректно працював на усіх пристроях, 
у тому числі мобільних.

Reboot - для покращеного кросбраузерного рендерингу ми використовуємо Reboot, щоб виправити 
неузгодженості між браузерами та пристроями, надаючи при цьому дещо більш впевнені скидання 
типових елементів HTML. У фремворку застосовується бібліотека "Reboot", яка скидає 
налаштування стилів за замовчуванням, встановлює свої стилі, які працюватимуть одинаково на
різних пристроях.
~~~

### Визначення терміну - "CDN"
~~~
CDN (Content Delivery Network) - це мережа з серверів, які розташовані в різних точках 
світу. 
Вона потрібна для прискореного доставлення, або розподілу статичного контенту сайту, 
такого як: зображення, аудіо записи, відео та інших файлів.
к працює CDN?
Дана мережа працює наступним чином:
Ви завантажуєте свій контент (сайт) в мережу CDN;
Він передається між локальними серверами мережі CDN;
При завантаженні контенту користувачем, він отримає його з найближчого сервера.

Яким чином CDN допоможе прискорити роботу сайту?
Сервери CDN розташовані по всій планеті. Вони можуть містити закешовані дані вашого сайту, 
і чим ближче до них знаходиться користувач, що починає завантаження сайту, тим швидше він 
отримає потрібні файли.

Висновок: чим ближче розміщені дані до користувача, тим швидше він їх отримає.

Що дає використання CDN ?
Збільшення швидкості завантаження сайту для великої кількості користувачів одночасно;
Зниження ризику DDoS-атак;
Велика стійкість сайту до сплесків активності;
Скорочення витрат трафіку користувачів;
Зменшення навантаження на веб-хостинг;
Покращення показників сайту в пошукових системах.
~~~
### Підключення фремворку локальним шляхом через відносний шлях
~~~
1. Заходимо на офіційний сайт фреймворку із документацією - 
https://getbootstrap.com/docs/5.3/getting-started/download/.
2. Натискаємо на "Download source" (для того щоб працювали усі модулі фреймворка).
3. Після скачування за архівованого файлу, розпаковуємо його. Він дуже великий і 
всього його не потрібно додавати до папкки проекту !
4. Створюємо в папці проекту папку з іменем "JS".
5. Заходимо в розархівований файл -> dist -> js, вибираємо та копіюємо файл 
(це фактично файл із всіма модулями фреймворку Java Script):
"bootstrap.bundle.min.js" (poper).
6. В папку "JS" вставляємо файл - "bootstrap.js".
7. Знову заходимо в заархівований файл -> dist -> css, вибираємо та копіюємо файл:
"bootstrap.min.css" (це файл з усіма стилями фреймворку).
8. В папці проекту створюємо папку "css" та вставляєм туди файл:
bootstrap.css.
9. Розархівований файл видаляємо (він більше не потрібний - він дуже великий і забере
багато місця для сайту).
10. В лінці на bootstrap, що була вставлена в <head>, забираємо значення в "href=""",
вставлємо туди шлях до css/bootstrap.css., розділ "integrity" - повністю видаляємо.
11. Розділ "crossorigin" - теж видаляємо.
Так має виглядати лінка:
<link href="site/css/bootstrap.css" rel="stylesheet"> (тут не ставимо "./" 
перед назвою папки).
12. В скрипті все видаляємо та в "src" вставляємо шлях до даного файлу:
js/bootstrap.js (тут не ставимо "./" перед 
назвою папки).
Так має виглядати посилання на JS:
<script src="site/js/bootstrap.js"></script>

!!! Це фактично ми підключимо стилі локально та не будемо залежати від зовнішнього 
джерела.
~~~
### Флоу скачування та застосування іконок
~~~
!!! Окремий спеціальний сайт з іконками для даного фреймворку (типить просто не реально)
https://icons.getbootstrap.com/
1. Заходимо на сайт - https://icons.getbootstrap.com/
2. Обираємо іконку та клікаємо на неї
3. Клікаємо на неї
4. Внизу з правої частини екрану копіюємо її: Copy HTML
5. Вставляємо з буферу обміну в структуру HTML документу
<link rel="stylesheet" href="site/css/fontello.css"> - підключаємо 
скачані іконки.
<link rel="stylesheet" href="node_modules/bootstrap-icons/font/
bootstrap-icons.css">
Після залиття папки з іконками bootstrap-icons через node команду: 
npm i bootstrap-icons на локальному 
рівні підключаємо bootstrap-icons.css та можемо використовувати 
шрифти іконок, наприклад: 
<i class="bi bi-xbox"></i>

!!! Підключення favicon:
<link rel="shortcut icon" href="site/img/favicon.ico" type="image/x-icon">.
~~~
### Інформація про контейнери
~~~
https://getbootstrap.com/docs/5.0/layout/containers/
~~~
__Основні брейкпоінти:__

Breakpoint          | Class infix        | Dimensions
:-------------------|:-------------------|:-------------|
X-Small	            | None	         | <576px
Small	            | sm		 | ≥576px
Medium	            | md		 | ≥768px
Large	            | lg		 | ≥992px
Extra large	    | xl		 | ≥1200px
Extra extra large   | xxl	         | ≥1400px
~~~
@media (min-width: 768px) and (max-width: 991.98px) { ... } - визначення 
одного сегменту розмірів екрана з використанням мінімальної та максимальної 
ширини точки зупину

Різні контейнери:
Bootstrap поставляється з трьома різними контейнерами:
.container, який встановлює max-widthдля кожної відповідної точки зупинки
.container-fluid, який знаходиться width: 100% на всіх точках зупину
.container-{breakpoint}, width: 100% до вказаної точки зупинки
~~~
__Таблиця із відображенням контейнерів із відступами для різних 
розширень екрану:__
|    | Дуже малий | Малий | Середній | Великий
:----|:-----------|:------|:---------|:---------|
|    | <576 пікселів | ≥576 пікселів | ≥768 пікселів | Великий
container | 100% | 540 пікселів | 720 пікселів | 960 пікселів
container-sm | 100% | 540 пікселів | 720 пікселів | 960 пікселів
container-md | 100% | 100% | 720 пікселів | 960 пікселів
container-lg | 100% | 100% | 100% | 960 пікселів |
container-xl | 100% | 100% | 100% | 100% |
container-xxl | 100% | 100% | 100% | 100% |
container-fluid | 100% | 100% | 100% | 100% |

|    | X large | XX-великий 
:----|:-----------|:------|
|    | ≥1200 пікселів | ≥1400 пікселів 
container | 1140 пікселів | 1320 пікселів 
container-sm | 1140 пікселів | 1320 пікселів
container-md | 1140 пікселів | 1320 пікселів
container-lg | 1140 пікселів | 1320 пікселів
container-xl | 1140 пікселів | 1320 пікселів 
container-xxl | 100% | 1320 пікселів
container-fluid | 100% | 100% 
~~~
!!! Макет сітки може максимально складатися з 12 стовпців та 6 підрівнів
~~~
### Основа: використання сітки під час побудови макету лейауту
~~~
https://getbootstrap.com/docs/5.0/layout/grid/
(Основа побудови макету лейауту сторінки)

Інформація про сітку:

<div class="container">
  <div class="row">
    <div class="col">
      Column
    </div>
    <div class="col">
      Column
    </div>
    <div class="col">
      Column
    </div>
  </div>
</div>

Наведений вище приклад створює три стовпці однакової ширини на всіх пристроях 
і вікнах перегляду за допомогою наших попередньо визначених класів сітки. 
Ці стовпці розташовані по центру сторінки з батьківським .container.

Колони неймовірно гнучкі. Для кожного рядка доступно 12 стовпців шаблону, 
що дозволяє створювати різні комбінації елементів, які охоплюють будь-яку 
кількість стовпців. Класи стовпців вказують на кількість стовпців шаблону 
для охоплення (наприклад, col-4охоплює чотири). widths встановлюються у відсотках, 
тому ви завжди матимете однаковий відносний розмір.

<div class="container">
  <div class="row row-cols-2">
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="col">Column</div>
  </div>
</div>

В даному випадку створюємо два рядки по дві колонки
!!! Більше прикладів за посиланням на документацію вище
~~~
### Побудова колонок
~~~
https://getbootstrap.com/docs/5.0/layout/columns/

Інформація про створення та редагування колонок

<div class="container">
  <div class="row align-items-start"> - розміщення колонки 
  вертикально зверху
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
  </div>
  <div class="row align-items-center"> - розміщення колонки 
  вертикально по середині
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
  </div>
  <div class="row align-items-end"> - розміщення колонки 
  вертикально внизу
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
    <div class="col">
      One of three columns
    </div>
  </div>
</div>

<div class="container">
  <div class="row">
    <div class="col align-self-start"> - задання ідентичних 
    властивостей безпосередньо колонкам а не рядкам
      One of three columns
    </div>
    <div class="col align-self-center">
      One of three columns
    </div>
    <div class="col align-self-end">
      One of three columns
    </div>
  </div>
</div>

Різні варіанти розташування по горизонталі:
<div class="container">
  <div class="row justify-content-start">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-center">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-end">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-around">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-between">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
  <div class="row justify-content-evenly">
    <div class="col-4">
      One of two columns
    </div>
    <div class="col-4">
      One of two columns
    </div>
  </div>
</div>

<div class="container">
  <div class="row">
    <div class="col-9"></div> - задання розміру колонок відносно 
    до 12-ти колонкової струтури сітки 
    <div class="col-4"></div>
    <div class="col-6"></div>
  </div>
</div>

Більше прикладів за посиланням на документацію зверху
~~~
### Задання відступів між колонками
~~~
https://getbootstrap.com/docs/5.0/layout/gutters/

Інформація про задання відступів між колонками:
<div class="container px-4">
  <div class="row gx-5"> - задання відступів по горизонталі між колонками
    <div class="col">
     <div class="p-3 border bg-light">Custom column padding</div>
    </div>
    <div class="col">
      <div class="p-3 border bg-light">Custom column padding</div>
    </div>
  </div>
</div>

gy-4 - задання відступів по вертикалі  між колонками
g-0 - видалити будь - які відступи між колонками

Більше прикладів за посиланням на документацію зверху
~~~
### Інформація стосовно контенту
~~~
https://getbootstrap.com/docs/5.0/content/reboot/

Сторінка за замовчуванням:
Елементи <html>та <body> оновлено, щоб забезпечити кращі стандартні 
значення для всієї сторінки. 
Більш конкретно:
Глобально встановлюється box-sizing для кожного елемента, включаючи 
*::before та *::after, до border-box. Це гарантує, що оголошена 
ширина елемента ніколи не буде перевищена через відступ або рамку.
База не font-size оголошена на <html>, але 16px передбачається 
(браузер за замовчуванням). 
font-size: 1rem застосовано <body> для легкого адаптивного масштабування 
типу за допомогою медіа-запитів, дотримуючись уподобань користувача 
та забезпечуючи більш доступний підхід. 
Цей параметр за замовчуванням браузера можна змінити, змінивши 
$font-size-root змінну.
Також <body> встановлює глобальні font-family, font-weight, 
line-heightта color. 
Це пізніше успадковується деякими елементами форми, щоб запобігти 
невідповідності шрифтів.
Для безпеки <body>оголошено background-color, за замовчуванням #fff.

Нативний (рідний) стек шрифтів:
font-family-sans-serif:
  // Cross-platform generic font family (default user interface font)
  system-ui,
  // Safari for macOS and iOS (San Francisco)
  -apple-system,
  // Windows
  "Segoe UI",
  // Android
  Roboto,
  // Basic web fallback
  "Helvetica Neue", Arial,
  // Linux
  "Noto Sans",
  "Liberation Sans",
  // Sans serif fallback
  sans-serif,
  // Emoji fonts
  "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", 
  "Noto Color Emoji" !default;

Фактично reboot перевизначає певні налаштування за замовчуванням на 
такі які передбачені фреймворком, передивитися усі деталі можна за 
посиланням на документацію наведеним вище.
~~~
### Інформація стосовно стилізації тексту
~~~
https://getbootstrap.com/docs/5.0/content/typography/ 
https://getbootstrap.com/docs/5.0/utilities/text/
Розділ містить інформацію про стилізацію тексту, у тому числі інформацію 
про класи фреймворка які заміняють певні теги HTML
~~~
### Інформація стосовно зображень
~~~
https://getbootstrap.com/docs/5.0/content/images/
Розділ містить інформацію про позиціонування зображень
~~~
### Інформація стосовно таблиць
~~~
https://getbootstrap.com/docs/5.0/content/tables/
Розділ містить інформацію про стилізацію таблиць
~~~
### Контейнери для зображень
~~~
https://getbootstrap.com/docs/5.0/content/figures/
Розділ містить інформацію про деякі вбудовані стилі для контейнера 
зображень - "figure"
~~~
### Стилізація форм та їхніх елементів
~~~
Цілий ряд розділів присвячено стилізації форм та їхнім внутрішнім елементам:
https://getbootstrap.com/docs/5.0/forms/overview/
https://getbootstrap.com/docs/5.0/forms/form-control/
https://getbootstrap.com/docs/5.0/forms/select/
https://getbootstrap.com/docs/5.0/forms/checks-radios/
https://getbootstrap.com/docs/5.0/forms/range/
https://getbootstrap.com/docs/5.0/forms/input-group/
https://getbootstrap.com/docs/5.0/forms/floating-labels/
https://getbootstrap.com/docs/5.0/forms/layout/
https://getbootstrap.com/docs/5.0/forms/validation/
~~~
### Компоненти (адаптивні елементи)
~~~
Розділ "Components" присвячений відображенню усіх можливих та готових 
елементів, які можна викокристовувати у фреймворку.
https://getbootstrap.com/docs/5.0/components/accordion/
https://getbootstrap.com/docs/5.0/components/alerts
https://getbootstrap.com/docs/5.0/components/badge/
https://getbootstrap.com/docs/5.0/components/breadcrumb/
https://getbootstrap.com/docs/5.0/components/buttons/
https://getbootstrap.com/docs/5.0/components/button-group/
https://getbootstrap.com/docs/5.0/components/card/
https://getbootstrap.com/docs/5.0/components/carousel/
https://getbootstrap.com/docs/5.0/components/close-button/
https://getbootstrap.com/docs/5.0/components/collapse/
https://getbootstrap.com/docs/5.0/components/dropdowns/
https://getbootstrap.com/docs/5.0/components/list-group/
https://getbootstrap.com/docs/5.0/components/modal/
https://getbootstrap.com/docs/5.0/components/navs-tabs/
https://getbootstrap.com/docs/5.0/components/navbar/
https://getbootstrap.com/docs/5.0/components/offcanvas/
https://getbootstrap.com/docs/5.0/components/pagination/
https://getbootstrap.com/docs/5.0/components/popovers/
https://getbootstrap.com/docs/5.0/components/progress/
https://getbootstrap.com/docs/5.0/components/scrollspy/
https://getbootstrap.com/docs/5.0/components/spinners/
https://getbootstrap.com/docs/5.0/components/toasts/
https://getbootstrap.com/docs/5.0/components/tooltips/
У папці проекту містяться файли: "index2.html" та "style2.css", -> на 
сторінці відображено основні варіанти тих чи інших елементів, які відносяться 
до різних груп, однак це не всі можливі варіанти. При потребі застосування на
стоірнці чи веб-сайті тих чи інших елементів потрібно перейти в розділи 
документації, які описані вище.  
~~~
### ФІксація елементів в різних частинах екрану
~~~
https://getbootstrap.com/docs/5.0/helpers/position/
~~~
### Розтягування лінка на весь елемент
~~~
https://getbootstrap.com/docs/5.0/helpers/stretched-link/
Фактично, таким чином увесь елемент стає клікабельним та 
натискаючи на нього можна перейти за посиланням тегу <a>.
~~~
### Обрізання тексту і заміна його частини "..."
~~~
https://getbootstrap.com/docs/5.0/helpers/text-truncation/
~~~
### API та Sass () 
~~~
https://getbootstrap.com/docs/5.0/utilities/api/
~~~
### Бекграунд
~~~
https://getbootstrap.com/docs/5.0/utilities/background/
~~~
### Бордери
~~~
https://getbootstrap.com/docs/5.0/utilities/borders/
~~~
### Кольори
~~~
https://getbootstrap.com/docs/5.0/utilities/colors/
~~~
### Різні варіанти відображення елементів (display)
~~~
https://getbootstrap.com/docs/5.0/utilities/display/
~~~
### Флексбокс
~~~
https://getbootstrap.com/docs/5.0/utilities/flex/
~~~
### Флоат
~~~
https://getbootstrap.com/docs/5.0/utilities/float/
~~~
### Різна взаємодія з елементами
~~~
https://getbootstrap.com/docs/5.0/utilities/interactions/
~~~
### Overflow (перелив)
~~~
https://getbootstrap.com/docs/5.0/utilities/overflow/
~~~
### Позиціонування елементів (position)
~~~
https://getbootstrap.com/docs/5.0/utilities/position/
~~~
### Розміри елементів - ширина та висота (width/height)
~~~
https://getbootstrap.com/docs/5.0/utilities/sizing/
~~~
### Відступи (padding/margin)
~~~
https://getbootstrap.com/docs/5.0/utilities/spacing/
~~~
### Вертикальне вирівнювання (vertical-align)
~~~
https://getbootstrap.com/docs/5.0/utilities/vertical-align/
~~~
### Видимість елементів (visible/invisible)
~~~
https://getbootstrap.com/docs/5.0/utilities/visibility/
~~~
### Загальні правила, які використовуються в фреймворку
~~~
https://getbootstrap.com/docs/5.0/extend/approach/
~~~
###
~~~
~~~

### Додаткова інформація
~~~
!!! В папку проекту завантажено папку з прикладами різних готових елементів
лейауту сторінки.
Папка: "bootstrap-5.3.1-examples" (тут можна взяти готові елементи із структурою 
HTML розмітки та стилізацією CSS)

!!! Встановлено плагін в VS Code із сніпетами bootstrap - "Bootstrap 5 & 
Font Awesome Snippets (v1.2.5)".
!!! При введенні "b5" в HTML - зявиться цілий список готових елементів із 
розміткою та можливістю порядкового обрання значень для тих чи інших атрибутів
та контенту.

!!! Додано наступні файли в папку -> site -> font:
- fontello.eot;
- fontello.svg;
- fontello.ttf;
- fontello.woff;
- fontello.woff2;

!!! Папки:
"css", "font", "img", "js" -> переміщено в папку "site".
Файли fontello.css та папку font з файлами розширення ми отримали після 
завантаження іконок з сайту https://fontello.com/ (іконки можна
було отримати і з інших джерел та з іншим флоу).

!!! Копіювання посилання на відео з "Youtube":
1. Заходимо на потрібне відео
2. Знизу натискаємо на кнопку "Поділитися"
3. Копіюємо в модальному вікні посилання знизу:
https://youtu.be/bTiAfLbmsnY?si=U8vcsuSPg2UPEe7j
4. Для того щоб відео зробити адаптивним переходимо  за адресою:
https://embedresponsively.com/
5. Вставляємо скопійоване посилання у поле введення
6. Натискаємо кнопку: "Embed"
7. Копіюємо згенерований код
8. Вставляємо посеред структури модалки в HTML, а саме в <div>
з класом "modal-body"

!!! Другий варіант:
1. Заходимо на потрібне відео
2. Знизу натискаємо на кнопку "Поділитися"
3. Натискаємо кнопку "Вставити"
4. Копіюємо елемент з правої сторони
5. Вставляємо в розмітку

m-auto -> задати автоматичний margin для елемента
mt-lg-5 -> "mt: margin-top", "lg: великий екран", "5: заданий відступ"

Тригер - це електронна логічна схема, яка має два стійки стани, в яких
може перебувати, доки не зміняться відповідним чином сигнали
керування.

!!! За замовчуванням вертикальне прокручування починається з 75vh !!!
~~~
### Висновки:
---
~~~
1. Окрім передбачених, значно обмежених по своїй функціональності класах,
можна серед бутстраповських класів створювати особисті класи, якими 
додатково стилізувати у власному CSS файлі -> style.css.
2. Уся робота в bootstrap грунтується на використанні сіток - Grid.
3. По факту усі компоненти bootstrap є адаптивними, тобто створеними для 
респонсів.
4. Якщо використовувати структуру для елемента:
<div class="container">
  <div class="row row-cols-2">
    <div class="col">
    ... element ...
    </div>
  </div>
</div>
Елементи відображатимуться на сторінці з відступами зправа та зліва.
Однак, якщо таку структуру сітки обгорнути у тег, до прикладу: "section"
і надати бекграунд саме йому, тоді фон розміститься не лише там де є
елемент, а й поза його межами, тобто на ширину усього вюпорта.
Якщо вище наведену структуру сітки забрати та вставити в розмітку 
готовий компонент фреймворку, тоді він займе все місце вюпорта та 
буде без відступів зправа та зліва.
При заданні для сітки значення "container-fluid", елемент 
розташується на всю ширину вюпорту.
5. Даний фреймворк класний тим, що завжди наявний адаптивний дизайн
у всіх його елементах.
6. Дуже великим плюсом є вже інтегрований JS для елементів, однак деяким 
елементам потрібно його прописувати із зразків у документації.
7. Адаптивність того чи іншого елементу легко коригується та нею можна легко 
маніпулювати.
8. Фреймворк свого роду, як конструктор, за доомогою якого можна
створювати сайти з спрощеною системою.
9. Дуже мал класів і не зявляються підсказки по них для автозаповнення
при початку їхнього введення.
10. Компоненти мають бути адаптивними та орієнтованими на мобільні пристрої
11. Компоненти мають бути створені за допомогою базового класу та розширені за допомогою 
класів-модифікаторів
12. Стани компонентів повинні відповідати загальній шкалі z-індексу
13. За можливості віддавайте перевагу реалізації HTML і CSS, а не JavaScript
14. По можливості використовуйте утиліти замість власних стилів
15. За можливості уникайте суворих вимог HTML (дочірні селектори)

~~~

__Посиланя на відео уроки:__

[![___Поислання на відео уроки:___](./site/img/logo.jpg)](https://www.youtube.com/watch?v=CvMxvb2D8Iw&t=16s)

_00:00_ __Введение Обзор, загрузка и подключение__
_04:00_ __Подключение Bootstrap 5 через CDN__
_05:55_ __Начало работы с Bootstrap 5__
_08:02_ __Знакомство с сеткой Bootstrap 5__
_09:39_ __Скачать Bootstrap 5 локально__
_11:04_ __Структура файлов Bootstrap 5__
_15:16_ __Подключение Bootstrap 5 локально__
_16:14_ __Сниппеты для Bootstrap 5 в VS Code__
_19:02_ __Подведение итогов__
_20:37_ __Шапка, модальное окно, градиент, треугольник, адаптивное видео__
_26:10_ __Документация: https://getbootstrap.com/docs/5.0/lay...__
_31:23_ __Плавная прокрутка до якоря на Bootstrap 5__
_35:15_ __Градиентный фон: https://www.colorzilla.com/gradient-e...__
_41:36_ __Генератор треугольников: https://morphismail.github.io/myInstr...__
_46:50_ __Адаптивное видео: http://embedresponsively.com/__
_50:07_ __Сетка 3 на 3 и иконки__
_01:07:37_ __Сетка 2 на 2__
_01:15:28_ __Как сделать Аккордеон на Bootstrap 5 https://getbootstrap.com/docs/5.0/com...__
_01:38:49_ __Адаптивные изображения на Bootstrap 5 https://getbootstrap.com/docs/5.0/con...__
_01:49:42_ __Практика и задание по работе с Bootstrap 5__
_01:56:42_ __Форма сбора средств Yoomoney https://yoomoney.ru/get__
_02:04:16_ __Завершение футера и Конкурс по Bootstrap 5__
_02:12:26_ __Обзор Документация Bootstrap 5 на русском__

___Файлы к уроку:___ ___https://drive.google.com/file/d/1g5BV...___
___Сайт по которому мы верстаем:___ ___https://morphismail.github.io/video_c...___
___Оффициальный сайт Bootstrap 5:___ ___https://getbootstrap.com/___
___Документация Bootstrap 5:___ ___https://getbootstrap.com/docs/5.0/get...___

