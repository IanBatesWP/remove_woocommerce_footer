# Edit WooCommerce Footer


[From mjepson on WordPress.org](https://wordpress.org/support/topic/how-to-remove-remove-designed-by-woothemes-from-footer/?replies=51)

```php
<?php

add_action( 'init', 'custom_remove_footer_credit', 10 );

function custom_remove_footer_credit () {
    remove_action( 'storefront_footer', 'storefront_credit', 20 );
    add_action( 'storefront_footer', 'custom_storefront_credit', 20 );
} 

function custom_storefront_credit() {
	?>
	<div class="site-info">
		<!-- &copy; gives us the (c) copyright sign -->
		<!-- You can use php code to pull your site name with this: <?php echo get_bloginfo( 'name' ) ?> -->
		<!-- Instead, I will just hard code my footer with HTML -->
		<p> &copy; IanBateswp.com. </p>
	</div>
	<?php
}

?>
```
