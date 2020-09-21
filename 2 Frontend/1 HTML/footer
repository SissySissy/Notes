    <?php
    $copyright = get_field('copyright', 'option');
    $sociallinks = get_field('social_media_channels','option');
    
    ?>
    
    <footer id="colophon" class="site-footer shift" role="contentinfo">
    
    <div class="container footer-content">
    	<div class="footer-newsletter" id="newsletter">
    		<?php
    			if( function_exists( "mc4wp_show_form" ) ) {
    				mc4wp_show_form();
    			}?>
    	</div>
    
    	<div class="site-info" itemscope itemtype="http://schema.org/WebSite">
    		&copy;
    		<?php echo $copyright; ?>
    		<?php echo get_theme_mod( 'copyright_identity' ); ?>
    		<span class="sep"> • </span>
    		<span itemprop="copyrightHolder" >
    			<?php printf( __( '%1$s by %2$s', 'atomic' ), 'coded', '<a target="_blank" rel="noreferrer" class="textlink" href="http://duotones.ch">duotones</a>' ); ?>
    		</span>
    	</div><!-- .site-info -->
    
    	<div class="footer-impressum">
    		<?php if( get_field('imprint_page', 'options') ){ ?>
    			<a class="textlink" href="<?php the_field('imprint_page', 'options')['url']; ?>">Impressum</a>
    		<?php } ?>
    		<?php if( get_field('imprint_page', 'options') && get_field('data_privacy_statement_page', 'options') ){ ?>
    			<span>|</span>
    		<?php } ?>
    		<?php if( get_field('data_privacy_statement_page', 'options') ){ ?>
    			<a class="textlink" href="<?php the_field('data_privacy_statement_page', 'options')['url']; ?>">Datenschutz</a>
    		<?php } ?>
    	</div>
    	
    	
    </div>
    </footer><!-- #colophon -->
    
    ---------------------------------------------
    
    
    /// SOCIAL MEDIA
    	
    	<div class="socialmedia-buttons">
    				<?php foreach($sociallinks as $social) : ?>
    					<a class="btn ghost" href="<?php echo $social['url']; ?>">
    						<i class="noetzel-icons"><?php echo str_replace('icon-', '', $social['channel']);?></i>
    					</a>
    				<?php endforeach;?>
        </div>
    ______________________________________________
    
    @import 'variables';
    
    .site-footer	{
    	background-color: $white;
    }
    
    .footer-content	{
    	display: flex;
    	align-items: center;
    	flex-direction: column;
    	padding-bottom: $space-unit * 4;
    	text-align: center;
    }
    
    .footer-newsletter	{
    	width: 100%;
    	max-width: 432px;
    	margin-top: $space-unit * 2;
    
    	.input-group {
    		display: flex;
    		margin-bottom: $space-md;
    
    		input {
    			margin: 0 $space-sm;
    
    			&:last-child {
    				margin-right: 0;
    			}
    
    			&:first-child {
    				margin-left: 0;
    			}
    		}
    	}
    
    
    	button	{
    		@extend %textlink;
    
    		padding: 0;
    		font-family: $font-quaternary;
    		font-size: 16px;
    		line-height: 1.7;
    		background: none;
    
    		i	{
    			margin-left: 4px;
    			font-size: 16px;
    			vertical-align: text-bottom;
    		}
    	}
    
    }
    
    .site-info	{
    	margin-top: $space-unit * 2;
    	font-family: $font-secondary;
    	font-size: 18px;
    	font-weight: 600;
    	color: $primary;
    }
    
    
    .footer-impressum	{
    	margin-top: $space-unit;
    	font-size: 14px;
    	color: $primary;
    
    	a {
    		font-family: $font-quaternary;
    	}
    
    	span	{
    		margin: 0 4px;
    	}
    }
    
    
    
    @media screen and (max-width: 425px) {
    	.footer-impressum	{
    		font-size: 16px;
    	}
    
    	.site-info	{
    		margin-top: $space-unit;
    	}
    }
    
    
    ------------------------------------------------------
    
    
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
eyJoaXN0b3J5IjpbLTE3MDI5MzYwNjBdfQ==
-->