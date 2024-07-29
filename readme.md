### Учебный проект: Книжный интернет-магазин на Google API

#### В рамках проекта необходимо:

1. **Сверстать главную страницу интернет-магазина Bookshop.**  
   Макет находится [здесь](https://www.figma.com/file/8XxPADjILtnlah4yWI0CLb/bookshop?node-id=0%3A1&t=IgjAXYdKMUHiJ6Pp-0).

2. **Подключить Google Books API**, чтобы данные о книгах подгружались с сервера.

3. **Подключить созданный вами ранее слайдер.**

4. **Поработать над правильной организацией проекта:**
   - Реализовать модульную структуру.
   - Подключить Webpack.
   - Настроить сборку с минификацией.
   - Применить пройденные вами ранее инструменты оптимизации.

---

### Функциональные требования

В рамках проекта нужно создать одну (главную) страницу книжного магазина. На странице должен быть следующий набор элементов:

1. **Шапка сайта**  
   Шапка содержит логотип, навигацию и набор кнопок. Ссылки в меню можно оставить пустыми, так как реализация остальных страниц сайта в проекте не предусмотрена. Кнопки авторизации, поиска и корзины неактивны. Однако при добавлении товара в корзину у иконки должен появиться бейджик с количеством товара в корзине. При прокрутке сайта шапка должна оставаться закреплённой в верхней части экрана.

2. **Слайдер**  
   Под шапкой сайта располагается слайдер. Чтобы сократить время разработки, рекомендуется использовать слайдер, который был создан в предыдущих модулях по JavaScript. Слайдер автоматически пролистывает изображения каждые 5 секунд, а после последнего изображения вновь переключается на первое. Перелистывать изображения можно также с помощью точек под слайдером. Справа от слайдера располагаются цветные блоки, которые нужно сверстать как ссылки (адреса можно оставить пустыми).

3. **Список категорий и список книг**  
   Под слайдером в левой части экрана располагается список категорий. Активная категория должна быть выделена визуально. По умолчанию в качестве активной выбрана первая категория в списке. Клик на неактивную категорию делает её активной, и список книг перезагружается, чтобы отобразить книги из этой категории. Список книг подгружается из Google Books API в соответствии с выбранной категорией. Для списка книг необходимо реализовать ленивую загрузку: сначала подгружаются первые 6 книг, по клику на кнопку «Load more» — ещё 6, и так далее.

4. **Карточка книги**  
   В карточке книги должна быть отображена следующая информация:
   - Обложка (если API не возвращает обложку, подставить плейсхолдер).
   - Автор (если авторов несколько, перечислить через запятую).
   - Заголовок.
   - Рейтинг: от 1 до 5 звёздочек плюс общее количество отзывов (если нет рейтинга, не показывать эту строчку).
   - Описание (если текст в описании занимает больше 3-х строк, обрезать и добавить многоточие).
   - Цена с указанием валюты (если нет цены, не показывать эту строчку).
   - Под описанием каждой книги должна быть кнопка «Buy now», при клике на которую товар добавляется в корзину. При повторном нажатии на кнопку товар убирается из корзины. Информация о книгах, добавленных в корзину, должна сохраняться в localStorage.

---

### Технические требования

1. В проекте необходимо использовать как минимум 2 инструмента оптимизации разработки (помимо npm и Webpack). Можно выбрать из списка:
   - Методология БЭМ.
   - CSS-препроцессор Sass (или аналог).
   - Шаблонизатор pug или аналог.
   - Webpack Dev Server.
   - Линтер.

2. К проекту необходимо подключить Webpack. Ожидается, что:
   - Сборка завершается успешно и без ошибок.
   - CSS-файлы также являются частью сборки.
   - CSS подключается отдельным файлом (не в теге `<style>`).
   - JS и CSS-файлы минифицируются в процессе сборки.

3. Для создания проекта необходимо использовать npm. В папке проекта должны быть файлы `package.json` и `package-lock.json`. В `package.json` необходимо прописать скрипт `npm run build`, который будет запускать сборку проекта. Папку `node_modules` добавлять в репозиторий не нужно.

4. JS-файлы в проекте должны быть разделены на модули (ES6), структура файлов должна быть логичной и понятной.

5. Книжный магазин должен быть реализован по принципу SPA, то есть все действия пользователя (подгрузка книг, переключение категории) должны происходить без перезагрузки страницы.

---

### Требования к верстке и CSS

1. Использовать селекторы по тегу и id для задания стилей нельзя, используйте классы.

2. При наведении курсора на любые кликабельные элементы должен появляться `cursor: pointer`.

3. Соблюдайте семантическую верстку. В приложении должны присутствовать разделы `<header>`, `<main>` и `<nav>`. Ссылки должны быть прописаны в теге `<a>`, кнопки реализованы элементом `<button>` и т. д. Не забывайте про обязательный атрибут `alt` у изображений.

4. Приложение должно корректно отображаться на различных разрешениях. Дизайна для мобильной версии в макете нет, поэтому постарайтесь реализовать её самостоятельно, перегруппировав элементы так, чтобы они помещались на маленьком экране.

5. Верстка должна соответствовать макету. Добиваться Pixel-Perfect соответствия не обязательно, но основные моменты должны быть соблюдены: цветовая гамма, шрифты, размеры, отступы.