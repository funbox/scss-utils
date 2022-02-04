# @funboxteam/scss-utils

**scss-utils** — набор вспомогательных SCSS-миксинов.

## Мотивация

В наших проектах много стилей, и самих проектов тоже достаточно много. Чтобы шарить знания и наработки и
избежать копипасты, мы решили выделить наиболее используемые SCSS хэлперы в отдельный пакет.

## Установка

```shell
npm install --save-dev --save-exact @funboxteam/scss-utils
```

## Состав библиотеки

- **[button-style-reset](./button-style-reset.scss)** — локальный сброс стилей тега button;
- **[placeholder](./placeholder.scss)** — вендорные псевдо-элементы для подсказки в текстовом поле;
- **[text-cut](./text-cut.scss)** — однострочная обрезка троеточием;
- **[multiline-text-cut](./multiline-text-cut.scss)** — многострочная обрезка троеточием;
- **[visually-hidden](./visually-hidden.scss)** — визуальное скрытие, чтобы элемент оставался доступным для юзер-агентов;
- **[get-unicode-string](./get-unicode-string.scss)** — функция получения последовательности Юникод. Нужна для обхода проблемы автоматической конвертации значения свойства `content` в нечитаемый символ Юникод. Решение взято из [ишью](https://github.com/sass/sass/issues/659#issuecomment-64819075) на Гитхабе.


## Использование

### Прямое подключение

Импортировать нужный хэлпер в SCSS-файл, в котором он будет использоваться:

```scss
@import '../../../node_modules/@funboxteam/scss-utils/visually-hidden';
```

*Можно пользоваться упрощенным вариантом, если его поддерживает сборка:*

```scss
@import '~@funboxteam/scss-utils/visually-hidden';
```

Инклудить по необходимости:

```scss
.button__text {
  @include visually-hidden;
}
```

### Подключение через [scss-imports-loader](https://github.com/funbox/scss-imports-loader)

В большинстве проектов используется scss-imports-loader, config-файл которого расположен по адресу `config/scss-imports.js`.

Импортировать нужный хэлпер в `config/scss-imports.js`:

```js
module.exports = [
  // ...
  'node_modules/@funboxteam/scss-utils/placeholder',
  'node_modules/@funboxteam/scss-utils/visually-hidden',
  'node_modules/@funboxteam/scss-utils/button-style-reset',
  'node_modules/@funboxteam/scss-utils/multiline-text-cut',
  // ...
];
```

Инклудить по необходимости:

```scss
.button__text {
  @include visually-hidden;
}
```

## Примеры

Пример использования функции **get-unicode-string**:

```scss
.list__item {
  &::before {
    content: get-unicode-string('2022'); // В браузере отобразится символ «•»
  }
}
```

[![Sponsored by FunBox](https://funbox.ru/badges/sponsored_by_funbox_centered.svg)](https://funbox.ru)
