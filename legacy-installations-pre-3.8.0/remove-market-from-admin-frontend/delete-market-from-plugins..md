# Delete Market from Plugins.

Open the following file:

```text
oc-admin/themes/modern/plugins/index.php
```

Locate and remove this code:

```text
<li><a href="#market" onclick="window.location = '<?php echo osc_admin_base_url(true) . '?page=market&action=plugins'; ?>'; return false; "><?php _e('Market'); ?></a></li>
```

​

Open the following file:

```text
oc-admin/themes/modern/plugins/add.php
```

Locate and remove this code:

```text
<div class="flashmessage flashmessage-info flashmessage-inline" style="display:block;">    <p class="info"><?php printf( __('Download more plugins at %s'), '<a href="'.osc_admin_base_url(true) . '?page=market&action=plugins">Market</a>'); ?></p></div>
```

