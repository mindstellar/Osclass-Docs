# Debug PHP Errors

The **`OSC_DEBUG`** constant, added in version 2.3, controls the display of php errors and warnings. If this setting is not defined in config.php, the default value is false.

When the **`OSC_DEBUG`** is false, the error reporting level is `E_ALL ^ E_NOTICE ^ E_USER_NOTICE`. In that case, we're not showing notice and strict php errors. However, if we set the constant to true, the error reporting level is `E_ALL | E_STRICT` and `display_error` value is **1**.

The **`OSC_DEBUG_LOG`** constant, added in version 2.3, logs these errors to a file called debug.log in oc-content. If Apache doesn't have write permissions, you may need to create the file first and set the appropriate permissions \(i.e. use 666\).

```php
/**
 * Copy this code to config.php file
 * This will disable notice and strict errors
 */
define('OSC_DEBUG', false) ;
```

```php
/**
 * Copy this code to config.php file
 * This will show all error notices and warnings on the site
 */
define('OSC_DEBUG', true) ;
```

```php
/**
 * Copy this code to config.php file
 * This will log all error notices and warnings to a file called debug.log in oc-content
 */
define('OSC_DEBUG', true) ;
define('OSC_DEBUG_LOG', true) ;
```

