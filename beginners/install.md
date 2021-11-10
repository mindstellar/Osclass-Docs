---
description: Step By Step Installation Guide
---

# Install

## How to install Osclass?

To install Osclass you need to follow these easy steps:

***

1. Download the latest zip package of Osclass from [GitHub Release](https://github.com/mindstellar/Osclass/releases) and unpack it in your web-server root, i.e. `public_html` directory.
2. Execute the Osclass installation script by accessing index.php `oc-includes/osclass/install.php` from your browser:
   * If you’ve installed it in the domain’s root directory, you’ll have to go to: `http://example.com/index.php` or directly to **http://example.com/oc-includes/osclass/install.php**
   * If you’ve installed it in a subdirectory inside the domain, classifieds, for example, go to: `http://example.com/classifieds/index.php` or directly to `http://example.com/classifieds/oc-includes/osclass/install.php`\
     This will lead you to osclass inbuilt installer.
3. Follow Osclass installer instructions:
   *   **Step 3.1**

       ![Step-1](https://raw.githubusercontent.com/mindstellar/Osclass-Docs/master/.gitbook/assets/Installer-step-1.png)\
       Make sure the server has the required permissions to write in the files and directories specified. This will allow you to create a basic configuration file as well as upload images, documents, etc.
   *   **Step 3.2**

       ![Step-2](https://raw.githubusercontent.com/mindstellar/Osclass-Docs/master/.gitbook/assets/Installer-step-2.png)\
       Add your access details to the database. If you haven’t created it yet, the installer will ask for another account with permissions that will allow to do it for you.
   *   **Step 3.3**

       ![Step-3](https://raw.githubusercontent.com/mindstellar/Osclass-Docs/master/.gitbook/assets/installer-step-3.png)\
       Add the basic installation details and select your classifieds site’s country.
   *   **Step 3.4**

       ![Step-3](https://raw.githubusercontent.com/mindstellar/Osclass-Docs/master/.gitbook/assets/installer-step-3.png)&#x20;
   * Installation finished. Use the automatically-generated password to access your admin panel (example.com/oc-admin).

#### How to get the latest version?

Checkout our [GitHub Release](https://github.com/mindstellar/Osclass/releases) section to get latest version of osclass.

Do not use master branch for your deployment, it may include untested code. Only use zip file provided in our release section.
