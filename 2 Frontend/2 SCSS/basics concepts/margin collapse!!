# Margin collapse

If the modules above are placed next each other in the HTML markup, then we might expect there to be  `75px`  (`25px`  from the top module plus  `50px`  from the bottom module) between them vertically, right?

Well, in this edition of  _CSS Survival of the Fittest_, we only get 50 of those pixels. It's like the bigger margin straight up ate the other one and left nothing behind.

Go ahead and measure. The space between those two modules amounts to the 50px of the  `module__bottom`  and kicks the margin from  `module__top`  to the curb.

A natural reaction might be to keep increasing the smaller margin until it makes a difference. But alas, when both margins are positive numbers:

`bigger margin = total vertical margin`

Those of you more mathematically minded than the likes of myself may cleverly ask: what about negative margins? The answer is that it does have a significant impact and reduces the margin between the two elements.

`50px + (-25px) = 25px`

[https://css-tricks.com/what-you-should-know-about-collapsing-margins/](https://css-tricks.com/what-you-should-know-about-collapsing-margins/)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MTc2NTM1MTEsMzAzNTc2MzgzXX0=
-->