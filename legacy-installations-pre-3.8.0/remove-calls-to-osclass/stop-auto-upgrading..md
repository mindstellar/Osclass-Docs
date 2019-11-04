# Stop auto upgrading.

This will stop automatic upgrading of Osclass, plugins, themes, and languages as the auto-upgrade function makes a call to osclass.org.

Open the following file:

```text
oc-includes/osclass/cron.php
```

Locate this code:

Replace it with this code:

```text
// osc_do_auto_upgrade();
```

This function \("osc\_do\_auto\_upgrade\(\);"\) first checks for the latest version of Osclass by making a request to osclass.org. After that it updates the plugins, themes and languages.

We commented this function instead of removing as you may wish to modify it to update your plugins, themes and languages without updating Osclass.

`osc_do_auto_upgrade()` is located in utils.php.

