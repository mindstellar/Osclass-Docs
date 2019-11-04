# Delete Connect Market from Admin toolbar.

## Delete Connect Market from Admin toolbar.

Removing the line of code listed below will remove "Connect Market" from your Admin toolbar \(header part\).

Open the following file:

```text
oc-includes/osclass/classes/AdminToolbar.php
```

Locate and remove this code:

```text
osc_add_hook( 'add_admin_toolbar_menus', 'osc_admin_toolbar_market_connect'     , 0 );
```

