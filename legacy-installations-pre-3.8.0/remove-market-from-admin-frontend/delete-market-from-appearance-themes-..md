# Delete Market from Appearance \(themes\).

Open the following file:

```text
oc-admin/themes/modern/appearance/index.php
```

Locate and remove this code:

```text
<li><a href="#market" onclick="window.location = '<?php echo osc_admin_base_url(true) . '?page=market&action=themes'; ?>'; return false; "><?php _e('Market'); ?></a></li>
```

Locate this code:

```text
echo '<p>' . sprintf(__("Change your site's look and feel by activating a 
theme among those available. You can download new themes from the <a href=\"%s\">market</a>. <strong>Be careful</strong>: if your theme has been customized, you'll lose all changes if you change to a new theme."), osc_admin_base_url(true) . '?page=market&action=themes') . '</p>'
```

Replace it with this:

```text
echo '<p
>' . __("Change your site's look and feel by activating a theme among those available. You can download new themes from the <a href=\"%s\">market</a>. <strong>Be careful</strong>: if your theme has been customized, you'll lose all changes if you change to a new theme."). '</p>';
```

Open the following file:

```text
oc-admin/themes/modern/appearance/add.php
```

Locate and remove this code:

```text
<div class="flashmessage flashmessage-info flashmessage-inline" style="display: block;">    <p class="info"><?php printf( __('Download more themes at %s'), '<a href="'.osc_admin_base_url(true) . '?page=market&action=themes">Market</a>'); ?></p></div>
```

