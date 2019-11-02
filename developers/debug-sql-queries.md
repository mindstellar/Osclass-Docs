# Debug SQL Queries

{% hint style="warning" %}
**Note**: This will have a performance impact on your site, so make sure to turn this off in your production site.
{% endhint %}

The **`OSC_DEBUG_DB`** constant, added in version 2.3, saves the database queries to an array and at the end of the execution the queries are displayed at the end the page. The information saves each query: the sql string, how long that query took to execute, the sql number error and string if there has been some sql error.

The **`OSC_DEBUG_DB_LOG`** constant, added in version 2.3, logs the sql queries to a file called queries.log in oc-content. If you want to debug the sql queries of the AJAX calls or cron, you must use `OSC_DEBUG_DB_LOG` because we can't print these at the end of the page. If **Apache** doesn't have write permissions, you may need to create the file first and set the appropriate permissions \(i.e. use 666\).

The **`OSC_DEBUG_DB_EXPLAIN`** constant, added in version 2.3, run an **`EXPLAIN`** query for each select query and logs the result to a file called **explain\_queries.log** queries. It should be used only during the development of OSClass, themes or plugins to see the performance of the queries. Remember, if Apache doesn't have write permissions, you may need to create the file first and set the appropriate permissions \(i.e. use 666\).

```php
/**
 * Copy this code to config.php file
 *
 * This will show SQL queries at the bottom of the site
 */
define('OSC_DEBUG_DB', true) ;
```

```php
/**
 * Copy this code to config.php file
 *
 * This will log all sql to a file called queries.log in oc-content.
 * 
 * If Apache doesn't have write permissions, you may need to create the file first 
 * and set the appropriate permissions (i.e. use 666).
 */
define('OSC_DEBUG_DB', true) ;
define('OSC_DEBUG_DB_LOG', true) ;
```

```php
/**
 * Copy this code to config.php file
 *
 * This will run a EXPLAIN sql query for each SELECT sql statement.
 * The results will be logged to a file called explain_queries.log in oc-content.
 * 
 * If Apache doesn't have write permissions, you may need to create the file first 
 * and set the appropriate permissions (i.e. use 666).
 */
define('OSC_DEBUG_DB_EXPLAIN', true) ;
```

