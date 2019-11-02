---
description: Osclass update instructions.
---

# Updating Osclass

## Automatic Update

### N/A

{% hint style="danger" %}
Work in progress
{% endhint %}

## Manual Update

These are short instructions, we're going to extend them in the future. If you experience problems you should report them on [Osclass forums](https://forums.osclasscommunity.com).

For these instructions, it is assumed that your Osclass URL is `http://example.com/`.

### Step 1: Take a backup

You should take a backup of your database and files. All your data is held in the database, so you will need to have a copy just in case you change your mind after upgrading and need to go back. The same reasons are sustained to make a backup of oc-content folder.

### Step 2: Replace Osclass files

* Get the [latest Osclass](https://github.com/navjottomer/Osclass/releases). \(zip or tar.gz\)
* Unpack the zip file that you've downloaded.
* Using FTP or you SSH, upload the new files. You should replace all the old Osclass files with the new ones: oc-admin and oc-includes directories and sub-directories, and in the root directory \(ajax.php, contact.php, index.php, item.php and so on\). Do NOT delete config.php file.
* Be careful when copying the oc-content directory. You should make sure that you only copy the files from inside this directory, rather than replacing your entire oc-content directory. If you have customized the default theme without renaming it, make sure not to overwrite those files, otherwise you will lose your changes. \(Though you might want to compare them for new features or fixes...\)

### Step 3: Update your installation

If you have permalinks enabled, you should disable them before updating Osclass. Then, update your installation. Just enter to the oc-admin \(http://www.example.com/oc-admin/\) and it will appear a button to update your database if it's necessary.

Visit `http://www.example.com/oc-admin/index.php?page=upgrade&action=upgrade-funcs`. If a database upgrade is necessary, Osclass will update your database to be compatible with the last code. If some new values in t\_preference are necessary, it will update too.

## Final steps

Your update is complete. Remember to activate permalinks if you have disabled before. It wasn't too difficult, was it? If anything goes wrong, you should let us know.

