

### Inheritance
```javascript
class Programmer extends Person { 
  constructor(name, programmingLanguage) {
    super(name);
    this.programmingLanguage = programmingLanguage;
  }

  writeCode() {
    console.log(this._name + ' is coding in ' + this._programmingLanguage + '.');
  }
}
```

### Get and Set

we use getters to access properties while we use setters to change them.

eg: having a property fullName

```javascript
const person = {
	firstName: "John",
	lastName: "Snow",
	get fullName()	{
		return `${person.firstName} ${person.lastName}`
	},
	set fullName(value) {
		const parts = value.split(" ");
		this.firstName = parts[0];
		this.lastName = parts[1];
	}
};

// using the setters to change the values at once
person.fullName = "Aegon Targaryan";

console.log(person.fullName);
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE2MTM3OTQyMSwtMTIzOTA5MTM3OCwtMT
U4OTY0MDYxNSw3MzA5OTgxMTZdfQ==
-->