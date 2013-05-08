# Forms Boilerplate

Здесь будут агрегироваться все лучшие практики, применимые к разработке форм в вебе на **основе нативных технологий**. А так же начальный лэйаут для быстрого старта и примеры самых часто используемых форм в формате **открытого для совместной разработки** проекта.

Первая версия документа будет оформлена только в текстовом виде, но в ближайшее время будет переведена на движок для документирования вёрстки. Всё содержимое проекта будет оформлено в удобной, структурированной среде.

## Основная цель

Поддерживать актуальную информацию о поддержке и возможностях нативных веб-форм в едином месте, соблюдая высокие качественные критерии.

## Критерии качества

Все приведённые в этом проекте техники разработки должны иметь следующие качественные показатели:

* Максимальное внедрение нативных решений
* Наилучший User Experience для большей аудитории
* Качество, надёжность и хорошая производительность
* Доступность (Accessibility)

Иными словами, качество форм должно удовлетворять потребности большого веб проекта на продакшн уровне.

## План работ

1. Информация о возможностях и поддержке HTML5 тегов, полей и атрибутов
2. Наборы часто используемых полей и их комбинация на основе лучших практик
3. Стартовая вёрстка/конструктор с базовым оформлением для разработки форм
4. Перенос контента проекта в среду для организации документаций по вёрстке - [Source](http://sourcejs.ru)
5. Готовые решения форм, с полифилами и валидацией
6. Перевод на английский язык

Вектор развития проекта зависит от вас, оставляйте свои отзывы и запросы в разделе [Issues](https://github.com/operatino/FBP).

# HTML5 поля и атрибуты

## Типы полей

	<input type=" … ">

### Готово к использованию

#### tel, number
Безболезненно можно использовать во всех браузерах, нет дополнительной стилизации полей, если браузер не понимает новый тип поля, воспринимает его как

	<input type=text>

Почти на всех мобильных платформах при фокусе на поле такого типа показывается специальная клавиатура.

![image](https://dl.dropbox.com/u/6594451/Projects/FBP/ios.jpg)

Поля имеют встроенную нативную валидацию:

* **num** - пропускает только цифровые значения
* **tel** - пропускает цифры и буквы

Для поля "number" доступны следующие атрибуты:

     min, max, step = number

#### url
Так же безболезненно рисуется во всех браузерах и падает в type=text, при непонимании браузера.

В некоторых браузерах при заполнении поля делает подсказки из истории браузера.

Имеет нативную валидацию, проверяет правильность введенного URL.

#### email
Этот тип поля внешне работает также, как и предыдущие и тоже имеет нативную валидацию.

Известны проблемы с валидацией почтовых доменах в локализированных зонах с double-bite кодировкой (.рф и подобные), лечатся с помощью атрибута:

	pattern="[^ @]*@[^ @]*"

#### list
С помощью "list" можно реализовать поддержку поля с авто заполнением нативными средствами.

![image](https://dl.dropbox.com/u/6594451/Projects/FBP/auto.jpg)

	<input type="text" list="autocomplete" value="Авто" class="big-input">
	<datalist id="autocomplete">
		<option value="Автозаполнение" label="Подсказка">
		<option value="Автомобиль">
	</datalist>

Поддержка во всех современных браузерах, только с некоторыми различиями в логике предлажения вариантов заполнения. В Firefox происходит поиск по сочетаниям букв в подсказке, в Chrome по точному вхождени с начала слова.

### Не рекомендуется к использованию без полифилов

#### range

Пока не поддерживается в Firefox, но в Nightly сборках уже присутствует. Позволяет вывести поле в виде ползунка, для которого можно выставить минимальное и максимальное занчение, а также шаг выбора значения:

     min, max, step = number

#### date

Нативная реализация календаря, который появляется при фокусе на поле. Пока не поддерживается в Firefox, и плохо отображает формат даты, все браузеры кроме Chrome выводят дату в формате yyyy-mm-dd.

# Полезные ссылки

* Презентация «[Формы в вебе](http://rhr.me/pres/forms/)», из которой выросла идея проекта Forms Boilerplate
* [HTML5 Boilerplate](http://html5boilerplate.com/) - идейный вдохновитель
* [HTML5 please](http://html5please.com/) - используйте технологии будущего уже сегодня

