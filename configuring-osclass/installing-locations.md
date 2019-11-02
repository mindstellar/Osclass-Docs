# Installing Locations

## Installing new locations <a id="firstHeading"></a>

### Via Admin panel

Under General Settings &gt; Locations you could install new locations \(countries, regions and cities\).

### Manually

Installing new locations could be a very-long process due to the big amount of data being transferred. You could raise your **max\_execution\_limit** on the PHP.ini file or install new locations manually.

* Download the .sql you want to from our [GitHub Repository](https://github.com/navjottomer/Osclass-Extras/tree/master/locations)
* Change /\*TABLE\_PREFIX\*/ for whatever your prefix is. \(If using the OSClass' import functionality it's not needed to modify anything\)
* Import it to your database \(via OSClass' import system -Admin panel &gt; Tools &gt; Import-, phpMyAdmin, command line,... \)

{% hint style="warning" %}
**Note:** If you already installed a country or a region you should not installed it again.
{% endhint %}

