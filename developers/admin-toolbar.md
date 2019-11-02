# Admin Toolbar

![Admin Toolbar](../.gitbook/assets/admintoolbar.jpg)

At admin panel since osclass version 3.0, there is a toolbar which is visible around the admin panel, can have shortcuts to actions like: add a new listing, show pending updates, ...

Developers can add to the toolbar whatever they want, with hooks, and calling AdminToolbar functions like add\_menu\($array\)

```php
 AdminToolbar::newInstance()->add_menu( array(...) );
```

```php
 /**
   * Add a node to the menu.
   *   
   * @todo implement parent nodes
   *
   * @param array $args - The arguments for each node.
   * - id         - string    - The ID of the item.
   * - title      - string    - The title of the node.
   * - href       - string    - The link for the item. Optional.
   * - meta       - array     - Meta data including the following keys: html, class, 
   *                                 onclick, target, title, tabindex.
 */
 function add_menu( $array ) 
```

#### Example, adding link to frontend

```php
 /**
  * Add webtitle with link to frontend 
  */
 function osc_admin_toolbar_menu()
 {
     AdminToolbar::newInstance()->add_menu( array(
                 'id'        => 'home',
                 'title'     => ''.  osc_page_title() .'',
                 'href'      => osc_base_url(),
                 'meta'      => array('class' => 'user-profile'),
                 'target'    => '_blank'
             ) );
 }
```

```php
 osc_add_hook( 'add_admin_toolbar_menus', 'osc_admin_toolbar_menu'    , 0 );
```

