# Keydown Event

The `keydown` and [`keyup`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keyup_event "The keyup event is fired when a key is released.") events provide a code indicating which key is pressed, while [`keypress`](https://developer.mozilla.org/en-US/docs/Web/API/Document/keypress_event "The keypress event is fired when a key that produces a character value is pressed down.") indicates which _character_ was entered. For example, a lowercase "a" will be reported as 65 by `keydown` and `keyup`, but as 97 by `keypress`. An uppercase "A" is reported as 65 by all events.

### Escape Event

```js
eventTarget.addEventListener("keydown", event => {
  if (event.isComposing || event.keyCode === 229) {
    return;
  }
  // do something
});
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNzE2OTY3OV19
-->