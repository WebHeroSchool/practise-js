### Создание объектов
- [1] Для создания объекта используйте фигурные скобки. Не создавайте объекты через конструктор new Object.

```javascript
// плохо
const item = new Object();

// хорошо
const item = {};
```
### Именование
- [2] Не используйте зарезервированные слова в качестве ключей объектов. 

```javascript

function getKey(k) {
    return `a key named ${k}`;
}

// плохо
var superman = {
    default: { clark: 'kent' },
    private: true
};

// хорошо
var superman = {
    defaults: { clark: 'kent' },
    hidden: true
};
```

### Создание массивов
- [3] Для создания массива используйте квадратные скобки. Не создавайте массивы через конструктор new Array.

```javascript
// плохо
    var items = new Array();

// хорошо
    var items = [];
```
### Свойства
- [4.1]Используйте точечную нотацию для доступа к свойствам и методам.

```javascript
const luke = {
    jedi: true,
    age: 28,
};

// плохо
const isJedi = luke['jedi'];

// хорошо
const isJedi = luke.jedi;
```

- [4.2] Используйте нотацию с [], когда вы получаете свойство, имя для которого хранится в переменной.

```javascript
const luke = {
    jedi: true,
    age: 28,
};

function getProp(prop) {
    return luke[prop];
}

const isJedi = getProp('jedi');
```
### Переменные
- [5.1] Объявляйте переменные, которым не присваивается значение, в конце. Это удобно, когда вам необходимо задать значение одной из этих переменных на базе уже присвоенных значений.

```javascript
// плохо
let i;
const items = getItems();
let dragonball;
const goSportsTeam = true;
let len;

// хорошо
const goSportsTeam = true;
const items = getItems();
let dragonball;
let i;
let length;
```
- [5.2] Объявляйте переменные по одной. Объявление каждой локальной переменной объявляет только одну переменную: такие объявления, как let a = 1, b = 2; не используются.

```javascript
// bad
let a = 1, b = 2, c = 3;

// good
let a = 1;
let b = 2;
let c = 3;
```
### Пробелы
- [6.1]Используйте пробелы между параметрами и не используйте между именем функции и скобкой.

```javascript
// плохо
function edit (name,age) {
    // тело функции 
}

// хорошо
function edit(name, age) {
    // тело функции
}
```
- [6.2]При создании анонимной функции необходимо использовать пробел перед скобкой;

```javascript
// плохо
function(name,age) {
    // тело функции
}

// хорошо
function (name, age) {
    // тело функции
}
```
- [6.3]Используйте пробелы вокруг операторов.

```javascript
// плохо
    if (age<100) {
    // тело цикла
}

// хорошо
if (age < 100) {
    // тело цикла
}
```
### Кавычки
- [7] Всегда в коде скрипта используйте одинарные кавычки, если не требуется иного. Двойные кавычки допустимы, если в этой же строке необходимо использовать апостроф (') или одинарные кавычки для других целей.

```javascript
// плохо
var example = "строка";

// хорошо
var example = 'строка';
var phrase = "you're next";
```

### Стрелочные функции предпочтительны
- [8]Стрелочные функции придают краткость синтаксису и исправляют многие сложности, с ним связанные. Отдавайте предпочтение стрелочным функциям, а не ключевым словам, особенно для вложенных функций.

```javascript
// плохо
[1, 2, 3].map(function (x) {
    const y = x + 1;
    return x * y;
});

// хорошо
[1, 2, 3].map((x) => {
    const y = x + 1;
    eturn x * y;
});
```
### Используйте строки шаблона вместо конкатенации
- [9]Используйте строки шаблона (отделенные с помощью `), а не сложную конкатенацию строк, особенно если задействованы несколько строковых литералов. Строки шаблона могут охватывать несколько строк.
```javascript
// bad
function sayHi(name) {
    return 'How are you, ' + name + '?';
}

// bad
function sayHi(name) {
    return ['How are you, ', name, '?'].join();
}

// bad
function sayHi(name) {
    return `How are you, ${ name }?`;
}

// good
function sayHi(name) {
    return `How are you, ${name}?`;
}
```
### Больше не используйте var
- [10]Объявляйте все переменные с помощью const или let. По умолчанию используется const, за исключением случаев, кгда нужно переназначить переменную. Ключевое слово var не должно использоваться.

```javascript
/// bad
var example = 42;

// good
let example = 42;
```