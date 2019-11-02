# Administrator Menus

Usually plugin and themes needs to add menus in the Administrator panel for provide access to screens. The best way is adding a menu section in the Administration menu that allows the user to access the screens.

There are some functions for manipulate the Administration Menu.

![Admin Menu](../.gitbook/assets/adminmenu.jpg)

#### hAdminMenu helper

Add menu page to Administration Menu.

```php
 osc_add_admin_menu_page( 
   $menu_title, 
   $url,
   $menu_id,
   $icon_url = null, 
   $capability = null,
   $position = null )
```

Add submenu page to Administration Menu page given a menu parent identifier.

```php
 osc_add_admin_submenu_page( 
   $menu_id, 
   $submenu_title, 
   $url, 
   $submenu_id, 
   $capability = null, 
   $icon_url = null )
```

Remove menu page from Administrator Menu.

```php
 osc_remove_admin_menu_page($id_menu);
```

Remove submenu page given parent menu page identifier.

```php
 osc_remove_admin_submenu_page( $menu_id, $submenu_id )
```

#### Adding submenus to existings menus

![](../.gitbook/assets/menusubmenu.jpg)

Helpers can add submenus to existing menus, like:Submenu Listings

{% hint style="info" %}
Helpers are available for these pages: 

* Listings
* Categories
* Pages
* Appearance
* Plugins
* Settings
* Tools
* Users
* Statistics
{% endhint %}

```php
 osc_admin_menu_items( 
   $submenu_title, $url, $submenu_id, $capability = null, $icon_url = null )
 osc_admin_menu_categories( 
   $submenu_title, $url, $submenu_id, $capability = null, $icon_url = null )
 osc_admin_menu_pages( 
   $submenu_title, $url, $submenu_id, $capability = null, $icon_url= null)
 osc_admin_menu_appearance( 
   $submenu_title, $url, $submenu_id, $capability = null, $icon_url = null )
 osc_admin_menu_plugins( 
   $submenu_title, $url, $submenu_id, $capability = null, $icon_url = null )
 osc_admin_menu_settings( 
   $submenu_title, $url, $submenu_id, $capability = null, $icon_url = null )
 osc_admin_menu_tools( 
   $submenu_title, $url, $submenu_id,$capability = null, $icon_url = null )
 osc_admin_menu_users( 
   $submenu_title, $url, $submenu_id, $capability = null, $icon_url = null )
 osc_admin_menu_stats( 
   $submenu_title, $url, $submenu_id, $capability = null, $icon_url = null )
```

Examples:

```php
 osc_add_admin_menu_page( 
   __('Listing'),                                             // menu title
   osc_admin_base_url(true).'?page=items',                    // menu url
   'items',                                                   // menu id
   'moderator'                                                // capability
 ) ; 
```

```php
 osc_add_admin_submenu_page( 
   'items',                                 // menu id
   __('Manage listings'),                   // submenu title   
   osc_admin_base_url(true).'?page=items',  // submenu url
   'items_manage',                          // submenu id
   'moderator'                              // capability
 ) ;
   ...
```

