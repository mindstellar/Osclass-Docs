# Stop checking for updates from Osclass.

Updated 16/09/2019 to fix auto update for older plugins \(Google Maps and Google Analytics\).

Scroll down to see updated part \(between warning messages\).

Open the following file:

```text
oc-includes/osclass/utils.php
```

Locate this code:

```text
$uri = osc_market_url($type, $update_uri);
```

Replace it with this code:

Locate this code:

```text
$url = osc_market_url($section, $element);$data = json_decode(osc_file_get_contents($url, array('api_key' => osc_market_api_connect())), true);
```

Replace it with this code:

Locate this code:

```text
$download_post_data = array('api_key' => osc_market_api_connect());
```

Replace it with this code:

```text
$download_post_data = array();
```

Locate this code:

```text
$url = osc_market_url($section, $code);$data = osc_file_get_contents($url, array('api_key' => osc_market_api_connect()));$data = json_decode(osc_file_get_contents($url, array('api_key' => osc_market_api_connect())), true);
```

Replace it with this code:

```text
return array('error' => 2, 'message' => __('Market updating not available.'), 'data' => $data);
```

Locate this code:

```text
if(osc_market_external_sources())
```

Replace it with this code:

```text
if(osc_market_external_sources() && strpos($update_uri, 'osclass.org') === false)
```

**Note**! The upper replacement must be done on all occurrences of the code \(it appears 2 times\).

Locate this code:

```text
if(!osc_market_external_sources()
```

Replace it with this code:

```text
if(!osc_market_external_sources() || strpos($update_uri, 'osclass.org') !== false)
```

​

Open the following file:

Locate this code:

```text
$data = json_decode(osc_file_get_contents(osc_market_url($section, $code), array('api_key' => osc_market_api_connect())), true);
```

Replace it with this code:

```text
echo json_encode(array('error' => 3, 'error_msg' => __('Market updating not available.')));
```

Locate this code:

```text
$data = osc_file_get_contents('https://osclass.org/latest_version_v1.php?callback=?');
```

Replace it with this code:

```text
echo json_encode(array('error' => 1, 'msg' => __('Version could not be checked')));
```

