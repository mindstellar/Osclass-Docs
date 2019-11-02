---
description: Basic Instructions to configure mail server in Osclass
---

# Mail Server

## Setting up a mail server <a id="firstHeading"></a>

With Osclass you could configure your email server. Some shared hosting has limited mail servers, you should always check with your hosting company about it before. If you own your own dedicated server you probably know how to set up one, if not, you should perform some searches on the internet \(on a linux machine it's enough to install postfix and courier packages\).

Configuring Osclass to use your mail server is very easy, we also offer a pre-filled configuration to use with Google mail servers, you should notice Google offers a limited service and your emails could get marked as spam.

~~Want to see it in action? **Check out our video tutorial on How to set up your mail server.**~~

Mail server settings are located on Mail server option, under **General Settings**

## Custom mail server

* **Hostname:** usually **smtp.yourdomain.com** but it could be any domain or IP \(localhost by default\)
* **Server port:** This is the port where is your mail server \(it depends on the protocol: _**POP3 - port 110**_, _**IMAP - port 143**_, _**SMTP - port 25**_, _**HTTP - port 80**_, _**Secure SMTP \(SSMTP\) - port 465**_, _**Secure IMAP \(IMAP4-SSL\)**_ _**- port 585**_, _**IMAP4 over SSL \(IMAPS\) - port 993**_, _**Secure POP3 \(SSL-POP\) - port 995\)**_
* **Username:** This is optional, only in case your server need authentication
* **Password:** Same as Username
* **Encryption:** ssl, tls or left blank as possible values
* **Check box for SMTP authentication** check only if you're sure what you're doing

## Google mail server

You need a Google Mail account, assume yours' myname@gmail.com

* **Hostname:** smtp.gmail.com
* **Server port:** 465
* **Username:** your username before the @ \( "myname" \)
* **Password:** your password
* **Encryption:** ssl
* **Check box for SMTP authentication** checked

## Troubleshooting

### **I'm not receiving any emails** 

Check your configuration on the Osclass admin panel. Maybe you have misspelled some detail. If everything looks correct, then check your mail server is working properly. Contact you hosting company or check the mail server's log to know what is happening.

### **It was working correctly but suddenly it stopped and I don't receive anything** 

Your mail server has stopped for some reason or you're getting your emails marked as spam. Check your mail server is running and revise its log. If they are being marked as spam, you probably have sent too many emails in a very short time interval.

### **I have other problems not listed here** 

Feel free to contact us on our support forums. We will be glad to help you. When posting your question, please, give us as much information as you can, so we could offer you a solution soon.

