# Radio buttons

## bubbling event

you want to add a decorative element to the selected radio button input
in a group of radio inputs

- use bubbling event on the main window (attention! it won't work when there is something on a parent container that prevents bubbling events!!)
- use `e.srcElement` to be sure that you target the input that fired the event. not like the `target`  that could be like the label.
- contains x classlist
- in html the normal way to group radio buttons is throuh the same name. this is why you should use that selector as the safest way to loop through a radio buttons group `e.srcElement.name` 
- you can use this name as a variable and pass that through a string literal `input[name="${name}"]`
- add an remove the class from its parent (label element in this case)
- **aria**-**describedby**  attribute on the input is used to indicate the **ID** of an elements that **describe** the object (such as a paragraph above the radio buttons group that describes the role of these buttons to screen reader).

```javascript
(() => {
	window.addEventListener('change', (e) => {
		if(e.srcElement.parentNode.classList.contains('button-radio')) {
			const name = e.srcElement.name;
			document.querySelectorAll(`input[name="${name}"]`).forEach((el) => {
				if(el.checked) {
					el.parentNode.classList.add('active');
				} else {
					el.parentNode.classList.remove('active');
				}
			})
		}
	});
})();
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUzMDIzNDkxNSw1MzEwOTg0MDBdfQ==
-->