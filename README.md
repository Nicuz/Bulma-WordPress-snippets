## Some useful snippets for using Bulma components on WordPress

> Tested on WordPress 4.9.4 with PHP 7.1.7

<p align="center">
  <a href="https://bulma.io"><img src="https://raw.githubusercontent.com/jgthms/bulma/master/docs/images/bulma-banner.png" alt="Bulma: a Flexbox CSS framework" style="max-width:100%;" width="350" height="184"></a>
</p>

---
### Custom walker menu 

<p align="center">
  <img src="https://raw.githubusercontent.com/Nicuz/Bulma-WordPress/master/img/bulma_walker_navbar_end.png" style="max-width:100%;">
</p>

#### HOW-TO:
* Copy and paste [the code](https://github.com/Nicuz/Bulma-WordPress/blob/master/bulma_walker.php) in you functions.php
* Declare a navbar component in your desired page (e.g. header.php)
```html
<nav class="navbar is-transparent">
  <div class="navbar-brand">
    <a class="navbar-item" href="https://bulma.io">
      <img src="https://bulma.io/images/bulma-logo.png" alt="Bulma: a modern CSS framework based on Flexbox" width="112" height="28">
    </a>
    <div class="navbar-burger burger" data-target="navbarExampleTransparentExample">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </div>

  <div id="navbarExampleTransparentExample" class="navbar-menu">
    <div class="navbar-end"> //you can also use the navbar-start class
      <?php wp_nav_menu(array(
        'theme-location' => 'nav-menu', //change it according to your register_nav_menus() function
        'depth' => 2,
        'container' => 'navbar-end',
        'items_wrap' => '%3$s',
        'walker' => new bulma_walker(),
      ));
      ?>
    </div>
  </div>
</nav>
```

* Create a menu from Appearance>Menu
* Check the right menu name and save it
---

### Custom paginate_links() 

<p align="center">
  <img src="https://raw.githubusercontent.com/Nicuz/Bulma-Wordpress/master/img/bulma_paginate_links_first_page.png" style="max-width:100%;" width="500" height="48">
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/Nicuz/Bulma-Wordpress/master/img/bulma_paginate_links.png" style="max-width:100%;" width="500" height="48">
</p>

#### HOW-TO:
* Copy and paste [the code](https://github.com/Nicuz/Bulma-Wordpress/blob/master/bulma_pagination.php) in you functions.php
* Declare a navigation component in your desired page (e.g. index.php)
```html
<nav class="pagination is-centered" role="navigation" aria-label="pagination">
  <?php echo bulma_pagination(); ?>
</nav>
```
* Enjoy
