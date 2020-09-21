
# Animations

## principles

```scss
.container .alert  {  
/* This timing applies on the way OUT */  transition-timing-function: ease-in;
 /* Quick on the way out */  transition:  0.2s;
 /* Hide thing by pushing it outside by default */  transform:  translateY(130%);
  }  

// shown class
 .container.alert-is-shown .alert  { 
  /* This timing applies on the way IN */  transition-timing-function: ease-out;
  /* A litttttle slower on the way in */  transition:  0.25s;
  /* Move into place */  transform:  translateY(0); 
   }
```
The animation timings we're using here are also in "rule" territory, as Val  [generally described](http://valhead.com/2016/05/05/how-fast-should-your-ui-animations-be/): 0.1-0.2s for simple interface movements, and up to 0.5s for more complex or larger movements.

In summary:

-   `ease`  is pretty nice, but you might want to customize some easings that feel right for your brand
-   `ease`  and  `ease-in-out`  have soft edges on both sides, but sometimes it's more appropriate to use ease-in or ease-out
-   You don't have to use a single easing for both directions of an animation, you can switch it up
-   You can change duration also


**transition: all 0.3s ease;**
all in this case means all the properties, so it includes top, bottom, color etc.
it's not all the children!!

so it has to be applied on the div that changes


## visibility

if the parents of the animation object changes its visibility, you should give it a delay! because even if the animation is playing you won't see the results

	visibility: hidden;
	transition: visibility .3s;
	
	.active	{
	visibility: visible;
	}

## translate

	transform: translateX(100%);

## little animations

	animation:  
	[animation-name] 
	[animation-duration]
	[animation-timing-function]
	[animation-delay]
	[animation-iteration-count]
	[animation-direction]
	[animation-fill-mode]
	[animation-play-state];

## examples

### easing
`ease`, `linear`, `ease-in`, `ease-out`, `ease-in-out`, `initial`, `inherit`

## animatin simple div

	transition: all 0.3s ease;
transition: transform 0.4s;
	transition-timing-function: ease;

## Stutter animation

```scss
// Loop from 1-9.
@for $i from 1 through 9 {
  .tile {
    
    // :nth-child(1-9) 
    &:nth-child(#{$i}) {
      
      // Delay the animation. Delay increases as items loop.
      animation-delay: $i * (1s / 18);
    }
  }
}
```

## Cubic beziers


## Scroll bar hidden on animation page jumps
When centering a page with CSS like `margin: 0 auto;`, there's a small gotcha: the page will 'jump' a little on certain browsers when navigating between short and long pages.

fix:
This has the side-effects that it will hide the right part of the page as the scrollbar hides that part, and it will disable horizontal scrolling. So I personally would not use it.

I've run into this problem myself and I've found two ways to solve it:

1.  Always force the scrollbar to be present:  `body { overflow-y: scroll; }`  Setting it on the  `html`  doesn't work in all browsers or might give  _double_  scroll bars if the scrollbar does appear.
    
2.  Add a class that adds ~30 pixels to the right margin of your page if there is no scrollbar.


```css
html {
    width:100vw;
    overflow-x:hidden;
}
```

### tweaking animatinos performance


[https://www.sitepoint.com/check-css-animation-performance-with-the-browsers-dev-tools/](https://www.sitepoint.com/check-css-animation-performance-with-the-browsers-dev-tools/)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MzY1MjE3NDcsLTU2NjAwNzU3MSwyMD
kxODk5MjkwLDQ0NzA3MTE2MSwxMzkwOTA1Mzk4LC0xMTc2NzMz
Nzk5LDkyOTEwMDIwOCwtMTY3MzY0MTUyNCwyMTAzNTAwMDQ3LD
E1NTA0ODg2ODQsMzI1NjIyNjI3LDQxNDQ4ODk4OV19
-->



### easing functions



https://gist.github.com/gre/1650294



example of use:



*function* ease(t){

​        *return* t<.5 ? 2*t*t : -1+(4-2*t)*t;

​    }