# Auto-update themes and plugins

In version 3.0, we introduced an auto-upgrade system for plugins and themes, along with some neat features. To make your plugins and themes able to use this new feature, you need to use the Update URI param on the description of your creations. The Update URI should be unique per theme/plugin and reply a JSON response with the following format:

```php
{
dt_mod_date: "YYYY-MM-DD HH:MM:SS",
dt_pub_date: "YYYY-MM-DD HH:MM:SS",
e_type: "{TYPE}",
i_total_downloads: "XYZ",
s_banner: "banner.jpg",
s_banner_path: "http://www.domain.tld/path/to/banner/",
s_compatible: "2.3,2.4,3.0,3.1,3.1.1,3.1.2",
s_contact_name: "My name",
s_description: "My description, HTML accepted",
s_source_file: "http://www.domain.tld/path/to/my_plugin.zip",
s_title: "Title",
s_update_url: "http://www.domain.tld/path/to/update/cheker.php",
s_version: "A.B.C",
}
```

  
**s\_version**: Any alphanumeric string is ok, but we encourage only-numeric ones to be able to check is a version is greater or not than the installed one, preferred A.B.C style, as "1.0.2" or "2.1.0"

  
**e\_type**: e\_type **has to be** one of these options THEME or PLUGIN or "LANGUAGE"

