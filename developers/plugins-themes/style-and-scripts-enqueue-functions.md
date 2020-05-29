# Style and scripts enqueue functions

## Using the Enqueue functions <a id="firstHeading"></a>

### Why use them?

The enqueue functions are used for loading your javascript and css files. The reason they were added is because many plugins make use of javascript frameworks such as JQuery, JQuery-ui, and fancybox just to name a few. There is a high chance that these javascript files could be loaded multiple times and that is where the enqueue functions come into play. The enqueue functions help to reduce the chances of the same file getting loaded more than once.

### The Enqueue functions

**javascript related functions**

`osc_enqueue_script($id)` - Enqueue script

`osc_remove_script($id)` - Remove script from the queue, so it will not be loaded

`osc_register_script($id, $url, $dependencies = null)` - Add script to be loaded

`osc_unregister_script($id)` - Remove script from the queue, so it will not be loaded

`osc_load_scripts()` - Print the HTML tags to make the script load

**css related functions**

`osc_enqueue_style($id, $url)` - Add style to be loaded

`osc_remove_style($id)` - Remove style from the queue, so it will not be loaded

`osc_load_styles()` - Print the HTML tags to make the style load

**Good naming practices**

If you're going to use another js library/file which is not in oc-load \(for example fancybox, or any other jquery plugin\) please, use a "good" name. 

If you're going to use "Jquery My plugin", do not register it as "my\_extrange\_name", because if someone else could be registering it with a different name and then it would be loaded twice.

### Examples

**registering a javascript file**
```php
osc_register_script('jCarouselLite', osc_base_url() . 'oc-content/plugins/carousel_for_osclass/js/jCarouselLite.js', 'jquery');
```

**Enqueueing the script**
```php
osc_enqueue_script('jCarouselLite');
```

**Enqueueing a style**

```php
osc_enqueue_style(
    'carouselCss',
    osc_base_url() . 'oc-content/plugins/carousel_for_osclass/css/slideshow.css')
 );
```

{% hint style="info" %}
You may have noticed that i did not register the style and that is because it is not required and there is no function to do so.
{% endhint %}

**Ok now onto a real life example.** 

To use these functions you will want to create a function for this example I am going to use ex\_load\_scripts\(\) please use a unique function name in your plugin if you are planning on releasing it otherwise we could end up with conflicting function names.

```php
   function ex_load_scripts() {
       osc_register_script('jCarouselLite', osc_base_url() . 'oc-content/plugins/carousel_for_osclass/js/jCarouselLite.js', 'jquery');
       osc_enqueue_script('jCarouselLite');
       osc_enqueue_style('carouselCss', osc_base_url() . 'oc-content/plugins/carousel_for_osclass/css/slideshow.css');
   }
```

Once you add that code you will then need to add the following hook to your index.php file of your plugin.

```php
   osc_add_hook('init', 'ex_load_scripts');
```

To load the script on the admin side you would use this hook

```php
   osc_add_hook('init_admin', 'ex_load_scripts');
```

That is all that you have to do to get your javascript and css files working in 3.1.+

For theme developers a good example can be found in the head.php file of the modern theme.

### Pre registered scripts

Osclass pre registers some of the more common javascript files.

Here is the list of pre registered javascript files.

```php
osc_register_script('jquery', osc_assets_url('js/jquery/jquery.min.js'));
osc_register_script('jquery-migrate', osc_assets_url('js/jquery-migrate/jquery-migrate.min.js'), array('jquery'));
osc_register_script('jquery-ui', osc_assets_url('js/jquery-ui/jquery-ui.min.js'), 'jquery');
osc_register_script('jquery-treeview', osc_assets_url('js/jquery-treeview/jquery.treeview.js'), 'jquery');
osc_register_script('jquery-nested', osc_assets_url('js/jquery-ui-nested/jquery-ui-nested.js'), 'jquery-ui');
osc_register_script('jquery-validate', osc_assets_url('js/jquery-validation/jquery.validate.min.js'), 'jquery');
osc_register_script('jquery-validate-additional', osc_assets_url('js/jquery-validation/additional-methods.min.js'), 'jquery-validate');
osc_register_script('jquery-spectrum', osc_assets_url('js/spectrum/spectrum.js'), 'jquery');
osc_register_script('tiny_mce', osc_assets_url('js/tinymce/tinymce.min.js'));

//Legacy js libraries
osc_register_script('tabber', osc_assets_url('osclass-legacy/js/tabber-minimized.js'), 'jquery');
osc_register_script('colorpicker', osc_assets_url('osclass-legacy/js/colorpicker/js/colorpicker.js'));
osc_register_script('php-date', osc_assets_url('osclass-legacy/js/date.js'));
osc_register_script('jquery-fineuploader', osc_assets_url('osclass-legacy/js/fineuploader/jquery.fineuploader.min.js'), 'jquery');
```

