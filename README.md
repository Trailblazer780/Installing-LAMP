# Installing LAMP
This is a documentation of how to install LAMP Server. This documentation was made by Ethan Farrell.
# Table of Contents:
1. [Downloading Apache](#Downloading-Apache)
2. [Installing Apache](#Installing-Apache)


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


