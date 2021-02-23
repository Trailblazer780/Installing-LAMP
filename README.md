# Installing LAMP
This is a documentation of how to install LAMP Server. This documentation was made by Ethan Farrell.
# Table of Contents:
1. [Downloading Apache](#Downloading-Apache)
2. [Installing Apache](#Installing-Apache)
3. [Deploying a Website Using Apache](#Deploying-a-Website-Using-Apache)
4. [Diabling Directory Browsing](#Disabling-Directory-Browsing)
5. [Installing PHP for Apache](#Installing-PHP-for-Apache)
6. [Generating a Self Signed SSL Certificate](#SGenerating-a-Self-Signed-SSL-Certificate)


## Downloading Apache

The first step to take is to visit this website: https://httpd.apache.org/download.cgi and get the latest stable version of Apache web server. You then must click on the link that says Apache httpd for Microsoft Windows is available from a few third-party vendors. A screen shot is provided below as to where to click for this download.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%201%20Windows%20Downloads%20for%20Apache.PNG)

After clicking that link you can scroll down to the heading that says Downloading Apache for Windows and select a third-party vendor to download it from.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%202%20Third%20party%20vendor%20apache.PNG)

For this example, we will be using the Apache Lounge. This link will take you to a new website that you can download apache from. You will be given 2 options for windows download. One of them being for a 64-Bit operating system and the other for a 32-Bit operating system. Select whichever one applies to you.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%203%20Download%20apache.PNG)

## Installing Apache

Now that you have Apache downloaded it is in a zip file and you need to extract it. The best place to extract the file is directly in the C: drive of your computer to allow it to be easily accessible.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%204%20Extract%20Apache.PNG)

Now that you have Apache extracted and the files in the C: drive of your computer we can now start to run Apache. To do this we need to open a command prompt window inside of the bin folder that is inside of the Apache24 folder. The path to this should look as follows: C:/Apache24/bin. The easiest way to open a command prompt in that specific folder is to open a command prompt and type in the command: cd C:/Apache24/bin. After running that command your prompt will now be in that working directory. Note: The command prompt needs to be in administrative mode.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%205%20Opening%20command%20prompt.PNG)

The next step is to install Apache as a service and to do this we have to run a command prompt in the location that we have it opened it. To do this you must run this command in command prompt. The command is: `httpd.exe -k install`. The command will run, and a popup will come up asking if Apache HTTP Server can have access through the firewall of the computer. If this comes up, click on the “Allow access button.”

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%206%20Installing%20Apache%20as%20service.PNG)

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%207%20Allow%20access%20through%20firewall.PNG)

After that step you can now go into your services and see that Apache2_4 is now a service on the computer.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%208%20Apache%20in%20services.PNG)

You can now click the “Start the service” button and it will successfully start the Apache web server if there are no port conflicts on your machine.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%209%20Start%20Apache%20Service.PNG)

Now that you have the service running you can do a quick check to see if the server is running correctly. To do this all you need to do is go to your default web browser and type either: localhost or 127.0.0.1 and a page should come up that simply says  “It works.”

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2010%20It%20Works.PNG)

If this page appears for you that means that your Apache server is now up and running and ready to be used!

## Deploying a Website Using Apache

The first steps in deploying a website using Apache web server starts with changing some configurations on the httpd.conf file which is Apaches config file. This file is in the Apache24/conf folder. When you scroll through the file you will notice that a lot of the content is commented out. The change we need to make is to allow apache to use the httpd-vhosts.conf file. 

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2011%20Chaning%20config%20VHOSTS.PNG)

The above screen shot is the line of code that we need to uncomment so that it looks like this.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2012%20VHOSTS%20enables.PNG)

Now that we have allowed Apache to access that file, we can now move onto the next step of deploying a website using  Apache web server. Note the location of the httpd-vhosts.conf file because we will be accessing it and changing it in the next few steps.

Moving onto the next step is creating a directory for you to place the files that your website will contain. The default folder that Apache access’ when looking for websites to host is in the Apache/htdocs directory. Here in this directory, we will create two websites. To do this we just need to make two folders that are named appropriately (the websites url).

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2013%20website%20folders.PNG)

In this example we will use these two folders inside of the htdocs. After creating these folders, we now need to access the hosts file in the windows operating system so that we can access these websites when they are deployed on Apache. To do this we need to navigate to the hosts file which is located here: `C:\Windows\System32\drivers\etc.`Inside of this folder the hosts file exists.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2014%20windows%20hosts%20file.PNG)

The next step in the process is to open the hosts file with any text editor while in administrative mode. You will only be able to save your changes if your text editor has administrative permissions. The screenshot below contains what the hosts file will direct you to when entering in those URL’s in a browser. This now allows apache to access them as well.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2015%20Modifying%20hosts%20.PNG)

After the hosts file has been modified, we now need to put something in the two folders that were created in earlier steps. The default file that Apache will look for as the landing page for a website being hosted is index.html. So, you can simply drop a basic html file with the name of index into the folders. The html file can contain anything from a line of text to a full-blown webpage. For this example, our index.html will only contain one line of text.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2016%20basic%20html%20page.PNG)

For the next step we are going to making the websites live with whatever content that is inside of the folders. To do this we will be modifying the httpd-vhosts.conf file that was discussed earlier. This file can be accessed inside of the `C:/Apache24/conf/extra file`.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2017%20modifying%20vhosts.PNG)

When you first open the httpd-vhosts.conf file you will see two examples of how the configuration is set up to host a website. First, we will make both test websites accessible and being hosted by Apache locally. To do this we can copy the example and change the values in it to reflect our websites. The screen shot below will provide the basic configuration to get the website up.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2018%20vhosts%20basic%20config.PNG)

After you have made the modifications in the httpd-vhosts.conf file to reflect the website and files you would like to host, save the changes you have made to the configuration file. When this has been completed you must now restart the Apache server for the changes to take effect. You can do this by stopping and then starting the Apache2.4 in the services menu on your machine. Now to check to see if these changes have been made and the website is now live you need to go into your browser and type in the URL to the website that you named in the vhosts configuration file. If done correctly you will now see that the website is live. 

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2019%20Website%20live.PNG)

## Diabling Directory Browsing

Now wil disable directory borwsing on the websites that we just set-up. To do this you need to use the following code which will no longer allow directory browsing. The following code needs to be put inside of the `<VirtualHost *:80>` starting and end tag. The below screen shots will show where it needs to be applied. Note: This only disables directory browsing on the site that you apply it to, any other sites you make will have it enabled unless you put this inside of the tags. The code that you need is below 

`<Directory "${SRVROOT}/htdocs/testingsite1.tbd">
Options -Indexes +FollowSymLinks
AllowOverride None
Require all granted
</Directory>`

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2020%20Disable%20directory%20browsing.PNG)

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2021%20Disable%20directory%20browsing%20code.PNG)

## Installing PHP for Apache

The next step of deploying a nice web server is to install PHP to it. To do this we must first start off with the download here: https://windows.php.net/download#php-8.0. There are two different versions of PHP and they are named Thread Safe and Non-Thread Safe version. Apache uses the Thread Safe version so this is the version we need to download. Download the zip file of newest version of Thread Safe PHP (currently it is PHP 8.0.2).

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2022%20Apache.PNG)

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2023%20Thread%20safe%20download.PNG)

The next step after downloading the newest PHP is to extract it. We are going to want to extract it into the C: drive once again just like we did with Apache24. Create a folder named phpApache to extract it to in the C: drive. 

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2024%20Extracting%20PHP.PNG)

Once you have extracted the contents of the PHP zip file into the new directory we created in the C: drive we can now go forward and give Apache access to the version of PHP we have downloaded by modifying the httpd.conf file. We can find this configuration file in the `C:/Apache23/conf directory`. To do this we must load the PHP module and add the mime type for php extensions. Then finally we need to list where the php.ini file is located. The screenshot below will provide the code that needs to be added to the httpd.conf file to implement php to the web server. This is a one-time configuration change unless you are adding newer or older versions of php to your web server.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2025%20httpd%20php%20.PNG)

This code can be added anywhere in your httpd.conf file. Once this has been added you must save the changes you have made to the httpd.conf file and stop and start the Apache2.4 service for the change to take effect.

To check and see if you have correctly implemented php to your web server you must create a text document inside the website directory and name it phpinfo.php. Then put the following code into that document with your preferred text edition and save the changes made to the file. 

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2026%20php%20verify.PNG)

After this file has been created inside the website directory you can now verify that php is now running on your server. To do this you must access the php file you have just created inside that directory. If done correctly the webpage should come back looking like the screen shot below. 

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2027%20php%20working.PNG)

## Generating a Self Signed SSL Certificate

First, we are going to start off with setting up SSL on testingsite1.tbd. To do this we must generate and SSL certificate and key file to allow us to use SSL. The first step we need to do is to move the openssl.cnf file from `C:/Apache24/conf` to the `C:/Apache24/bin` folder. 

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2028%20SSL%20move.PNG)

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2029%20Moved%20SSL.PNG)

The next step in this process is generating the SSL self signed certificate. To do this we must open a command prompt and switch to the `C:/Apache/bin` directory.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2030%20SSL%20opening%20CMD.PNG)

Next, we need to run a command that will build some files that are going to be needed when generating the SSL certificate. The below screenshot will include the command that needs to be run. The pass phrase can be anything, and all the other information can be whatever you choose. It is important to set the common name to the website URL. After running this command, you will see that 2 files have been generated in your bin folder. One being a .csr file and the other being a .pem file. The command is: `openssl req -config openssl.cnf -new -out testingsite1.csr -keyout testingsite1.pem`.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2031%20Generating%20SSL%20files.PNG)

These are the two files generated.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2032%20SSL%20files%20generated.PNG)

After those two files have been generated, we now need to generate our key file. The below screenshot will have the command that needs to be run to do this. When it asks for the passphrase you enter in the password you set it as in the previous step. Note: This is a self signed certificate it is not a real certificate. The command is: `rsa -in testingsite1.pem -out testingsite1.key`.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2033%20Generating%20key%20file.PNG)

You will now see that the .key file has been generated in the bin folder.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2034%20key%20file%20generated.PNG)

The next step is going to be generating the signed certificate file. The command is: `openssl x509 -in testingsite1.csr -out testingsite1.crt -req -signkey testingsite1.key -days 3650`.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2035%20certificate%20generation.PNG)

After running this command, you will now see that a new file has been generated in the `C:/Apache24/bin` folder.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2036%20Security%20Certificate.PNG)

Next, we are going to move back the original openssl.cnf file to the /Apache24/conf directory and the 4 files that were generated doing the previous steps.

![alt text](https://github.com/Trailblazer780/Installing-LAMP/blob/main/Images/Capture%2037%20Move%20back%20files.PNG)



