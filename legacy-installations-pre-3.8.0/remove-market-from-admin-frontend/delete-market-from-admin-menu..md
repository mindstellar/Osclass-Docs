# Delete Market from Admin menu.

```text
oc-includes/osclass/classes/AdminMenu.php
```

```text
$this->add_menu( __('Market'), osc_admin_base_url(true) .'?page=market', 'market', 'administrator');if( !osc_is_moderator() ) {    $connected = osc_check_market_connect();    if(!$connected) {        $this->add_submenu( 'market', __('Connect Market'), osc_admin_base_url(true) . "?page=market&open_market_connect=true", 'market_connect', 'administrator');    }}$this->add_submenu( 'market', __('Themes'), osc_admin_base_url(true) .'?page=market&action=themes', 'market_view_themes', 'administrator');$this->add_submenu( 'market', __('Plugins'), osc_admin_base_url(true).'?page=market&action=plugins', 'market_view_plugins', 'administrator');$this->add_submenu( 'market', __('Languages'), osc_admin_base_url(true).'?page=market&action=languages', 'market_view_languages', 'administrator');
```

```text
$this->add_submenu( 'appearance', __('Market'), osc_admin_base_url(true).'?page=market&action=themes', 'appearance_market', 'administrator');
```

```text
$this->add_submenu( 'plugins', __('Market'), osc_admin_base_url(true).'?page=market&action=plugins', 'plugins_market', 'administrator');
```

