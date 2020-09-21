# Z-Index


- it works only when the object is positioned (abs, relative, fixed, sticky) not on static which is default. 
- normal order is background, natural stacking, children items.
- The Z-index can also take global values such as inherit, initial, unset. Inherit gets the property value of the parent element. Initial gets the default property that comes with the DOM. Unset takes either the value of the parent or the default property. Unset will take the parent property if the parent element has a value that matches i.e it can either act as initial or inherit depending on if the parent value has a value that fits it.
- z-index stacking order is relative to the parent element
- 
-You may not run into this issue often, but another aspect of stacking order is that some CSS properties like `transform` or `opacity` will put the element into its own, new [stacking context](https://www.w3.org/TR/css-color-3/#transparency).What this means is that adding the `transform` to the `.cat-bottom` element makes it behave as if it had a `z-index` of 0

- Each nested index has to adhere to the current index of its parent and then will have its own index inside of it if it has a position property. What? Well, because its parent has a z-index of 4 within ITS parent element (that body element) Div #4 has to obey that in regard to anything outside of its parent
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk0NTc4OTEwMSwtNjQ4MjU5NDA1LC0zOD
UwMDYzMjIsLTEzMzAxMDQzNV19
-->