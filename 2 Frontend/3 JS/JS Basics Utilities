# Js Basics and Utilities

## Basics
It is important to not pollute the global scope. All the javascript files will be compiled at once, also in pages where the html element doesn't exist. This was why the console showed a reference error.

To protect this from happening, you wrap the code in an IIFE

```js
(function() {
  /* code */
})();
```
```js
(() => {
  /* code */
})();
```

```js
(function doSomething() {
  /* code */
})();
```

### Use constants

when they are wrapped in a IIFE they don't pollute the global scope.

### Foreach

when you want to select more than one element, you will get a nodelist, but to perform operations you need them as a pseudo array or as an object. You can use foreach to select multiple elements in the right way.


## selecting different html elements through data-name

    let elementName = Element.tagName;

La proprietà  **`tagName`** di sola lettura dell'interfaccia [`Element`](https://developer.mozilla.org/it/docs/Web/API/Element "Element è la classe base più generale da cui ereditano tutti gli oggetti in un Document. Ha solo metodi e proprietà comuni a tutti i tipi di elementi. Classi più specifiche ereditano da Element.")  restituisce il nome del tag dell'elemento su cui è chiamato. Ad esempio, se l'elemento è un [`<img>`](https://developer.mozilla.org/it/docs/Web/HTML/Element/img "L'elemento HTML <img> incorpora un'immagine nel documento. È un elemento sostituito."), la sua proprietà `tagName` è `"IMG"`

! notare all caps.

puoi quindi selezionare i differenti tag name e dare differenti event listner:

per esempio un SELECT avrà bisogno di un "on change" event

mentre un button o input avranno bisongo di "click" event

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTMxMTY5MTMyNiwxOTYzNTEyMTcyLC0xMj
Q0OTMzMDI4LDk0MTY5OTI3XX0=
-->