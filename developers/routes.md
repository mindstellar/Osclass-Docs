# Routes

### What are the routes for?

You could extend Osclass with plugins, and sometimes you need to create a special page, for example to show more options to your users. 

In previous versions, the url will look like: 

`domain.tld/index.php?page=custom&file=your_plugin/page.php` 

Which isn't the prettiest url you could see, and also the file path are visible which is not a problem, but it's not good. In 3.2 we added "routes" that will transform that ugly url into a more beauty one, like: 

`domain.tld/your_plugin_page`  

They even works with regular expressions to accept variables on the url.

### The route functions

To make routes works, we first need to create them:

```php
/**
* $id - Shortname of the route
* $regexp - Regular expression of the url
* $url - Required to be able to create the nice-looking url
* $file - file that will be loaded
*/
osc_add_route($id, $regexp, $url, $file)

Later we just need to get the url:
```

Later we just need to get the url:

```php
/**
* $id - Shortname of the previously created route
* $args - Optional, only required if your url accept parameters
*/
//For public routes
osc_route_url($id, [$args])

//For routes in the admin panel
osc_route_admin_url($id, [$args])
```

### Examples

Here is an example

```php
// Create route
osc_add_route(
     'dynamic-route',
     'dynamic-route/([0-9]+)/(.+)',
     'dynamic-route/{my-numeric-param}/{my-own-param}',
     osc_plugin_folder(__FILE__).'mydynamicroute.php'
   );
// Show link to it
echo osc_route_url(
         'dynamic-route', 
         array(
               'my-numeric-param' => '12345', 
               'my-own-param' => 
               'my-own-value'
               )
    );
```

### Notes

* Parameters in the $url should be enclosed between "{" and "}", example "{parameter}"
* Parameters should have the same name \(case sensitive\) in both, osc\_add\_route and osc\_route\_url
* Additionally, any file located in a folder called "admin" will be opened in admin panel, but show a 404 error in the public site

{% hint style="danger" %}
Remember that regular expressions could be tricky, make them truly unique so they will not collide with any other rule.
{% endhint %}

### Example plugin

An example plugin could be found in github : [https://github.com/osclass/osclass-plugins/tree/routes\_example](https://github.com/osclass/osclass-plugins/tree/routes_example)

