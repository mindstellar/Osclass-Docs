# Increase PHP memory limit

### Increasing memory allocated to PHP

Released with version 2.3, the **OSC\_MEMORY\_LIMIT** option allows you to specify the maximum amount of memory that can be consumed by PHP. This setting may be necessary when you see a message such as "Allowed memory size of X bytes exhausted".

This setting increase PHP memory for OSClass, so it wouldn't affect other applications. By default, the memory allocated is set to 32MB. If PHP has been allocated 128MB, there is no need to set this value to 128M because OSClass checks if PHP has been allocated more memory than the entered value.

This setting may not work if your host doesn't allow for increasing the PHP memory limit. In that case, contact your host to increase the PHP memory limit.

Increase PHP Memory to 128MB \(add this define constant in config.php\)

```php
define('OSC_MEMORY_LIMIT', '128M') ;
```

