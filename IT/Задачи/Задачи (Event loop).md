#### Что выведет код?
```js
log(1);

setTimeout(() => {
  console.log(2);
}, 0);

Promise.resolve().then(() => {
  console.log(3);
});

console.log(4);
```
>[!faq]- Ответ
>1 4 3 2

### Что выведет код?
```js
log(1);

setTimeout(() => {
  log(2);
  Promise.resolve().then(() => {
    log(3);
  });
}, 0);

setTimeout(() => {
  log(4);
}, 0);

Promise.resolve().then(() => {
  log(5);
});

Promise.resolve().then(() => {
  log(6);
});

log(7);
```
>[!faq]- Ответ
> 1 7 5 6 2 3 4

### Что выведет код?
```js
log(1);

setTimeout(() => {
  log(2);
  Promise.resolve().then(() => {
    log(3);
  });
}, 0);

setTimeout(() => {
  log(4);
}, 0);

Promise.resolve().then(() => {
  log(5);
});

queueMicrotask(() => {
  log(6);
});

log(7);

setTimeout(() => {
  log(8);
  queueMicrotask(() => {
    log(9);
  });
}, 0);
```
>[!faq]- Ответ
> 1 7 5 6 2 3 4 8 9
