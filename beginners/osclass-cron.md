# Osclass Cron

## What is Cron?

Cron is a time-based job scheduler in Unix-like computer operating systems. Cron enables users to schedule jobs \(commands or shell scripts\) to run periodically at certain times or dates. It is commonly used to automate system maintenance or administration. Osclass has a built-in functionality in case your system has no cron daemon, you could enable/disable it from the admin panel, general settings &gt; cron. It's recommended to read more about [CRON on the wikipedia](http://en.wikipedia.org/wiki/Cron). 

It's also recommended to use your system's CRON instead of the built-in functionality of Osclass, since you will get better results with the first one. We use this functionality to run a few jobs as sending email alerts or counting number of items per category.

## CRON in Osclass

As said before, we need some 'jobs' to be done from time to time, from sending email alerts, to count number of items per category or allow plugins as sitemap perform other actions.

In an ideal world, every server would have CRON enabled, and you would be able to set as many cronjobs as you want. But because we know that it's not always true, we offer this built-in functionality.

## Configure CRON with Osclass

### Inbuilt Cron

To use the built-in functionality you need to **check** the Auto-cron option on the admin panel, under Settings  Cron. 

![600px-Settings\_cron\_check](https://user-images.githubusercontent.com/1062985/66152289-cb99fd80-e636-11e9-8b83-a2d9d86d0b8d.png)

### System Cron

To use your system's CRON functionality you need to **uncheck** the Auto-cron option on the admin panel, under _Settings &gt; Cron settings_.

![](https://user-images.githubusercontent.com/1062985/66152288-cb99fd80-e636-11e9-9a9b-7456b64c1e9c.png)

Cron is only available on Unix or Unix-like system \(Linux, OSX, Free BSD\). 

Most of the web servers out there are running a Linux distribution, so it should be no problem at all. Windows systems have several alternatives to CRON which work in different ways. Usually, you need to SSH your server \(access via SSH\) and type on the command line/terminal this

```bash
crontab \-e
```

You will enter your "cronjob list" on a terminal editor \(usually vi, vim, nano or emacs\). Then it depends on the editor to save, close, edit the file itself, etc.

Most hosting companies will not offer SSH access, and those who do it, some of them will not offer you the possibility to modify the CRON, but offer you a workaround via admin panel to do it. For example, Dreamhost \(under Goodies &gt; Cron\) offers you an "easy wizard" to run cronjobs, but limits to one cronjob per user \(via terminal/SSH you have no limits\).

We can not provide you with more information since it highly depends on your hosting company/server.

A cron job needs a time interval/time and a command to be executed, something like \(really, more detailed on the wiki, I will not talk about the different time options\)

```bash
\* \* \* \* \* command params
```

In our case, we want to execute a php file, we need to have installed php-cli or php-cgi versions, which are the executables of PHP. 

{% hint style="info" %}
NOTE: Some server will only have the apache mod version of PHP since performance is slower with the mod version and also have a few fewer features, It's strange that some server doesn't have it, but it could happen! ask your hosting company!
{% endhint %}

Well, we need to run the CLI \(command-line interface or executable\) version of PHP, we need to use the full path \(your phpinfo could help you on this, or ask your hosting provider!\) then, we need to pass as a parameter or argument the PHP file, use full path again \(NOTE: Usually, shared server use the home directory to hold their users and websites, so your path will be /home/your\_username/public\_html, again, "public\_html" is one of the most used folders, but it could be different, as website, yourdomain.com or anything. Also, if you own a private server, your web path is probably /var/www\)

#### Crontab \(if you could access ssh\)

Access your server via SSH, type

```text
crontab \-e
```

The whole cron-job should look like this

```bash
0 * * * * usr/local/php5/bin/php /home/your\_username/public\_html/index.php \-p cron \-t hourly
0 0 * * * usr/local/php5/bin/php /home/your\_username/public\_html/index.php \-p cron \-t daily
0 0 * * 0 usr/local/php5/bin/php /home/your\_username/public\_html/index.php \-p cron \-t weekly
```

{% hint style="info" %}
**Didn't understand crontab expressions?**

Checkout : [Crontab Guru](https://crontab.guru/) A easy to use online tool for creating crontab scheduler expressions
{% endhint %}

Set to run at every hour o'clock \(path of the PHP executable could be different\)

{% hint style="warning" %}
Some hostings don't offer the possibility to set cron tasks manually, instead, they offer their clients a wizard or an option on their admin panel to set up the tasks.
{% endhint %}

### **Dreamhost**

In your admin panel go to "Goodies &gt; Cron jobs &gt; add new cron job", since Dreamhost only allow you to use one cronjob per user, it's better to use this instead :

```bash
wget domain.com/index.php?page\=cron \-O /dev/null
```

and select "Hourly"

### **Hostgator**

Enter your Cpanel, scroll down to "Advanced", click on "Cron Jobs". If you want to know if there's any error, enter your email.

Enter the following command:

```bash
wget domain.com/index.php?page\=cron \-O /dev/null
```

Select to run "Once an hour \(0 \* \* \* \*\)", and you're done!

## Different setups

* Best case scenario

You are able to run one or many cron-jobs. In that case, execute oc-includes/osclass/cron.php in your cron-job '_each hour_.'

Remember to uncheck **General Settings &gt; Cron &gt; Auto-cron**.

* Auto-cron

If you are not able to set any cronjob, don't want to or don't know how to set it, just check

**General Settings &gt; Cron &gt; Auto-cron** and you're done.

