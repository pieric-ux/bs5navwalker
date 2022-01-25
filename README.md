# bs5navwalker
A custom WordPress nav walker class for Bootstrap 5 nav menus in a custom theme using the WordPress built in menu manager.

Add the following to your functions.php file.
```php
<?php
// Include custom navwalker
require_once('bs5navwalker.php');

register_nav_menus('header' => 'Header menu');
```

Create your nav menu somewhere in your theme.
```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
```
```php
        <?php wp_nav_menu([
           'menu' => 'header',
           'menu_class' => 'navbar-nav nav-justified w-100',    // Modify the class as desired
           'container' => 'div',
           'container_class' => 'collapse navbar-collapse',
           'container_id' => 'navbarSupportedContent',
           'theme_location' => 'header',
           'walker' => new bs5Navwalker()
            ]);
        ?>
    </nav>
```
