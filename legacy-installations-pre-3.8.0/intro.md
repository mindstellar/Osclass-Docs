# Introduction

If you don't want to upgrade to new Osclass 3.9.0, you can use use this guide to remove Osclass Market from your current installation.

{% hint style="info" %}
This guide was made by [webmods-croatia](https://github.com/webmods-croatia) and was originally posted on docs.osclasscommunity.com which is now moved here.
{% endhint %}

## About the guide. <a id="about-the-guide"></a>

This guide covers most, if not all, changes required to un-tie your site from Osclass Market

If you know some changes that we forgot, post it on our forums or contact us via the links above.

## Verifying that this works. <a id="verifying-that-this-works"></a>

As a test if this mods were successful, we put `error_log('cURL:'.$url);` in `osc_file_get_contents()` function.

We visited admin homepage, plugins, themes and language pages, settings page, we checked for updates, we ran cron, etc.

There wasn't a single cURL log that says that a request has been made to Osclass.

Also, all this changes were made on a live site as the guide was written. There were no problems, errors and warnings.

