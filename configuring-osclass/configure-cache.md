# Configure Cache

{% hint style="info" %}
NOTE: before enabling cache make sure you have installed and enabled the cache extension.
{% endhint %}

### **APC / APCu**

You need to edit your config.php file and the following line

```php
   define('OSC_CACHE', 'apc');
```

### **MEMCACHE**

You need to know ip and port of the machine/s where memcached service is installed and then add the following lines to the file config.php

```php
   define('OSC_CACHE', 'memcache');
   $_cache_config[] = array(
       'default_host'      => '127.0.0.1',
       'default_port'      => 11211,
       'default_weight'    => 1
   );
```

