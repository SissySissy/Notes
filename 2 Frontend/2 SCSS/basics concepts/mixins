# Sass Mixins Functions

## basics

### best way to declare variables:
per rimanere efficente separa i colori dai link. 
in questo modo puoi riusare colori etc etc.

Here are some golden rules for nesting:

-   Never go more then 3 levels deep.
-   Ensure the CSS output is clean and reusable.
-   Use nesting when it makes sense to, not as a default option.

```sass
$orange: #ffa600; 
$grey: #f3f3f3; 
$blue: #82d2e5;

$link-primary: $orange;
$link-secondary: $blue;
$link-tertiary: $grey;

$radius-button: 5px;
$radius-tab: 5px;
```

### curious example
you can declare variables inside brackets to have it scoped.
sing string interpolation, we can create new selectors with the variable.

    $block:  ".MyComponent";

    #{$block} { 
     &-title {
       #{$block}--xmasTheme & {
         }
      }
	}

## mixin
```scss
@mixin layout($cols, $margin) {
  &.col-#{$cols} {
    min-width: calc((100% / #{$cols}) - #{$margin}*2);
    @media screen and (max-width: )
  }
} 
```
You can call the mixin using **@include**
```scss
.column {
  @include mess(3, 14px);
}
```

## placeholders
Unlike mixins, [placeholders](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#placeholder_selectors_) can be used multiple times without adding any duplicate code. This makes them a much friendlier option for outputting DRY CSS:
```sass
%bg-image {
    width: 100%;
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
}

.image-one {
    @extend %bg-image;
    background-image:url(/img/image-one.jpg");
}

.image-two {
    @extend %bg-image;
    background-image:url(/img/image-two.jpg");
}
```

### @each

creating classes through each and interpolation

```scss
$colors: {
	youtube: red,
	twitter: blue,
	evernote: green,
};

@each $name, $color in $colors {
	.#{$name} {
		color: $color;
	}
}

```

more useful example with font-size
```scss
$font-sizes: {
	h1:48px,
	h2 36px,
	h3 24px,
	h4 18px,
	p:18px,
};

@each $tag, $size in $font-sizes {
	#{$tag} {
		font-size: $size;
	}
}

```

### counter


### button mixin sane example

- first define general button styles in a placeholder
- create a mixin with a logic eg: color on hover becomes lighter
- crea pulsanti con classi speciali e colori speciali

```sass
/* PLACEHOLDER 
============================================= */

%btn {
    padding: 10px;
    color:#fff;
    curser: pointer;
    border: none;
    shadow: none;
    font-size: 14px;
    width: 150px;
    margin: 5px 0;
    text-align: center;
    display: block;
}

/* BUTTON MIXIN 
============================================= */

@mixin  btn-background($btn-background) {
    @extend %btn;
    background-color: $btn-background;
    &:hover {
        background-color: lighten($btn-background,10%);
    }
}

/* BUTTONS
============================================= */

.cta-btn {
    @include btn-background(green);
}

.main-btn {
    @include btn-background(orange);
}

.info-btn {
    @include btn-background(blue);
}
```

## functions

```sass
@function calculate-width ($col-span) {
    @return 100% / $col-span 
}

.span-two {
    width: calculate-width(2); // spans 2 columns, width = 50%
}

.span-three {
    width: calculate-width(3); // spans 3 columns, width = 33.3%
}
```

## Sass list functions

**`length($list)`**: returns the length of  `$list`.

**`nth($list, $index)`**: returns the value at  `$index`  position in  `$list`  (throw an error if index is greater than the list length).

**`index($list, $value)`**: returns the first index of  `$value`  in  `$list`  (or  `null`).

**`append($list, $value[, $separator])`**: appends  `$value`  to the end of  `$list`  using  `$separator`  as a separator (using the current one if not specified).

**`join($list-1, $list-2[, $separator])`**: appends  `$list-2`  to  `$list-1`  using  `$separator`  as a separator (using the one from the first list if not specified).

**`zip(*$lists)`**: combines several list into a comma-separated list where the nth value is a space-separated lists of all source lists nth values. In case source lists are not all the same length, the result list will be the length of the shortest one.

## iterate arrays in scss


## Other readings

[https://css-tricks.com/sass-techniques-from-the-trenches/](https://css-tricks.com/sass-techniques-from-the-trenches/)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4OTk5MzA2OTIsMTYxOTc0ODkyMiwtMT
UyNzc4MDM3OSwtMTg0OTgxODU5MywtMTUwMjU3MjM4MCwtMTY3
NzMzMDcwNywtMjExMzQzODg0NCwxODMwMzEzMzQ2XX0=
-->