# Delete featured products from Admin.

You may think this change fits better in "Remove Market from admin frontend." section, but featured products make a call to Osclass to get the product list.

Open the following file:

Locate and remove this code:

```php
$aFeatured = array();
$out_featured = osc_file_get_contents(osc_market_featured_url('plugins', 3));
$array_featured_plugins = (array) json_decode($out_featured, true);​
$out_featured = osc_file_get_contents(osc_market_featured_url('themes', 3));
$array_featured_themes = (array) json_decode($out_featured, true);​​
$this->_exportVariableToView("aFeatured", 
array_merge($array_featured_plugins, $array_featured_themes));
```

​

Open the following file:

```text
oc-admin/themes/modern/main/index.php
```

Remove each one of this blocks of code:

```php
$aFeatured            = __get('aFeatured');
```

```php
osc_register_script('market-js', 
osc_current_admin_theme_js_url('market.js'), array('jquery', 'jquery-ui'));
osc_enqueue_script('market-js');​
osc_add_hook('admin_header','add_market_jsvariables');
```

```markup
<style>    
.mk-item {
          width: 90%;
          margin:5%;        
          margin-top: 3%;    
        }    
.mk-item-plugin {        
                  height: 225px;    
                }    
.mk-item .mk-info {
        width:auto;    
        }
 .mk-item-plugin .banner , .mk-item-theme .banner {
         width: 90%;        
         height: 155px;        
         border-radius: 5px 5px 0 0;        
         -webkit-border-radius: 5px 5px 0 0;        
         -moz-border-radius: 5px 5px 0 0;    
         }​    
 .mk-item-plugin .mk-info {        
         height: 40px;
         padding: 170px 15px 15px;
         }
 ​</style>
```

```php
<div class="grid-row grid-first-row grid-50">
    <div class="row-wrapper">
        <div class="widget-box  widget-box-project">
            <div class="widget-box-title"><h3><?php _e('Featured products'); ?></h3></div>
            <div class="widget-box-content widget-box-content-no-wrapp">
                <?php foreach($aFeatured['themes'] as $p) {
                    drawMarketItem($p);
                } ?>
                <?php foreach($aFeatured['plugins'] as $p) {
                    drawMarketItem($p);
                } ?>
            </div>
        </div>
    </div>
</div>
<div class="grid-row grid-50">
    <div class="row-wrapper">
        <div class="widget-box">
            <div class="widget-box-title"><h3><?php _e('Market'); ?></h3></div>
            <div class="widget-box-content widget-box-content-no-wrapp">
                <div id="banner_market"></div>
            </div>
        </div>
    </div>
</div>
```

```javascript
<script type="text/javascript">
    $(function(){
        $.getJSON(
            '<?php echo osc_admin_base_url(true); ?>?page=ajax&action=dashboardbox_market',
            function(data){
                if(data.error===0) {
                    $('<a href="'+oscEscapeHTML(data.url)+'" target="_blank"><div style="height: 100%; width: 100%; background: url('+oscEscapeHTML(data.banner)+') no-repeat;"></div></a>').insertAfter('#banner_market');
                }else {
                    $('<p style="text-align:center; padding-top:15px;"><?php _e('Has been a problem loading the contents, sorry for the inconvenience'); ?></p>').insertAfter('#banner_market');
                }
            });
        });
</script>
```

