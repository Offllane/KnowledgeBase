Лексическое окружение -- это невидимый (скрытый) объект, который создается автоматически для любого блока, скрипта или функции в JS.

Данный объект состоит из двух частей:
1. Объект с переменными в текущей [[Scope (область видимости)|области видимости]].
2. Ссылка на внешнее (родительское) лексическое окружение.

```js
const x = 1;  
  
const logToConsole = function () {  
    const i = 'Hi';  
    console.log(i);  
}
```
Здесь два лексических окружения:
1. Глобальное, оно содержит
	ссылка: null
	переменные: { x: 1, y: function }
	 (это лекс окружение имеет доступ только к своим переменным)

2. Локальное (внутри logToConsole):
	ссылка: глобальное лекс. окр.
	переменные: { i: 'Hi' }
	(это лекс окружение имеет доступ ко всем переменным)

>[!note] Лексическое окружение функций создается только тогда, когда функция была вызвана

>[!note] При каждом новом вызове функций создается новое локальное лексическое окружение
