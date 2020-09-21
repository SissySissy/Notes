# Scroll up button

### html
    <div class="footer-arrow">
    		<button type="button">
    			<i class="pr-icon">up</i>
    		</button>
    	</div>
    
### css   
        
    .footer-arrow	{
    	display: block;
    	align-self: flex-end;
    }
    

### JS    
    const scrollBack = document.querySelector('.footer-arrow button');
    
    function scrollTop() {
      const scrollOptions = {
        top: 0,
        behavior: 'smooth'
      }
      window.scrollTo( scrollOptions );
    }
    
    if(scrollBack) {
    	scrollBack.addEventListener("click", scrollTop);
    }
    
    
    // ??
    const newsletterResponse = document.querySelector('.mc4wp-response');
    
    if(newsletterResponse && newsletterResponse.childElementCount > 0) {
    	const scrollOptions = {
        top: 9999999,
        behavior: 'auto'
      }
    	window.addEventListener('initPosts', () => {
    		window.setTimeout(() => {
    			window.scrollTo(scrollOptions);
    		}, 100);
    	})
    }

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MjA2NDA4NjAsLTExMTE5Mjc3MjldfQ
==
-->