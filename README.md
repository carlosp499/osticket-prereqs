<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

-osTicket v1.15.8 (osTicket-v1.15.8.zip)

-PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

-Rewrite Module (rewrite_amd64_en-US.msi)

-PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)

-VC Redistributable (VC_redist.x86.exe)

-MySQL 5.5.62 (mysql-5.5.62-win32.msi)

<h2>Installation Steps</h2>

-First Step: Download the file osTicket-Installation-Files.zip provided here -> https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD

-Second step: We need to install/enable IIS (Internet Information Services) in Windows With CGI

- enter control panel on your homescreen -> go to programs and click on "unistall a program" -> Cick check box for IIS and click "+" -> World Wide Services

- go to application development features click "+" -> Check off "CGI"

<img width="645" height="542" alt="Screenshot 2025-08-14 171648" src="https://github.com/user-attachments/assets/05db53f6-f78f-4e29-a122-eac491e9f1a6" />

example of what it should look like
</p>
<p>
-Third step: go back to the "osTicket-installation-Files", after you get to the files you need to install required software: 

- PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

- Rewrite Module (rewrite_amd64_en-US.msi)

<img width="1123" height="620" alt="Capture" src="https://github.com/user-attachments/assets/e2c802d9-fb7c-42f8-9763-6a1a57e1770a" />

- This is waht the files will look like on your folder (shown circled in blue)

-Fourth Step: next you need to create a folder in the "C-Drive" and call it "PHP"

<img width="1114" height="606" alt="Capture2" src="https://github.com/user-attachments/assets/69f696c2-1f9a-48f5-aed2-48e42801eb27" />

- C:Drive is shown with star/ you will click on "home" and click on new folder and as shown call it "PHP"

-Fifth Step: Once you're in osTicket folder extract "php-7.3.8-nts-Win32-VC15-x86.zip" into "C\PHP" folder

<img width="616" height="454" alt="Capture3" src="https://github.com/user-attachments/assets/e8fd1233-2da7-4ccd-bc84-af1dc4bab152" />

- You will click on teh search bar and type " C:\PHP" it will extract on to the php folder

-Sixth Step: Afterwards install "VC Redist" (VC_redist.x86.exe)

<img width="1126" height="639" alt="Capture5" src="https://github.com/user-attachments/assets/58bfdc91-cca8-467e-b4e0-8758880cceb2" />

-file circled in blue

-Seventh Step: You Will install the "MYSQL"

-  Then run "mysql-5.5.62-win32.msi"

-  Next choose "typical set up"

-  After install you need to launch "Configuration wizard"

-  Make sure to use standard configuration

<img width="523" height="382" alt="Capture6" src="https://github.com/user-attachments/assets/8c6622cc-504e-4a72-ad0a-4e5a1dd460fc" />

-shown in blue bracket

-  Next set credentials: username: root, and password: root

-Eight step: you will configure "PHP" in "IIS"

-  Then you'll run IIS manager as an administrator

-  Then go to PHP manager

-  You will need to register new php version = browse to php folder inside get “php-cgi”, then click on "okay" 

<img width="1426" height="751" alt="Capture7" src="https://github.com/user-attachments/assets/4b3fa5b2-f896-447c-8077-96413ef4eca6" />

-  Then you need to reload IIS, go back to the begining right click on OsTicket-VM (STOP and START the server)
</p>
<br />

<p>

</p>
<p>

-Ninth step: You will install osTicket next

-  You need to Unzip osTicket v1.15.8 (osTicket-v1.15.8.zip).

-  Then Copy the upload folder into "C:\inetpub\wwwroot."

-  You will Rename "upload" to "osTicket".

<img width="1294" height="656" alt="Capture8" src="https://github.com/user-attachments/assets/59233ec3-08b4-4bf8-8f1d-bd77a468b7a0" />

-arrow in red shows where to drag folder

-  You will again Reload IIS (Stop and Start the server).

-  Next you need to open IIS - Default - OsTicket

-  Then Click *Browse :80 to verify the installation. (shown in red)

<img width="650" height="644" alt="Screenshot 2025-09-25 175302" src="https://github.com/user-attachments/assets/1da28691-8ea3-49a3-a5ac-e03d6f83ca10" />


<br />

<p>
<img width="649" height="651" alt="Screenshot 2025-09-25 175116" src="https://github.com/user-attachments/assets/2dc63204-c0b2-44e3-8696-18268a96d104" />


  example of how your OsTicket should look like 

  ----

</p>
<p>

-Step #10: You will need to enable the require PHP extensions

-  ISS -> Sites -> Default Sites -> OsTicket
-   next double click the "PHP Manager" icon
-   click on the "enble or dissable an extension" option
    - enable: php_imap.dll
    - enable: php_intl.dll
    - enable: php_opache.dll

<img width="996" height="395" alt="Capture10" src="https://github.com/user-attachments/assets/ec3ca444-382a-4c2f-a73e-ec4a853c9a74" />

-  next just refresh the broswser and double check that they were enabled 

-Step #11: You will configure OsTicket
- Rename "ost-sampleconfig.php" into "ost-config.php:"
- Now From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- Then To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
- Then you need to assign permissions to ost-config.php:
- Next right click, click on properties, then security, advanced, dissaable inheritance, then remove all.
- add-select principle-type everyone-check full control
- continue setting up Osticket in the browser.
- make your username: Ostktuser
- your password: password11
- add your email to receive emails of complaints

-Step #12: you will be setting up "MySQL Database"
- you will install and open "HeidiSQL" from the OsTicket folder
- create a new with your username: Root, username: Root
- connect to the session and then create a database named OsTicket.
- Once you  set up OsTicket on the browser
- set up MYSQL Databas: OsTicket
- MySQL Username: root
- MySQL Password: root
- Make sure you click "install now"

<img width="927" height="725" alt="Capture11" src="https://github.com/user-attachments/assets/c122a553-88b0-4095-861a-130dadbea9e3" />

-in the end this is how it shouuld look after you succesfully installed everything

-Step #13: Access OsTicket
- head to the loging page: http://localhost/osTicket/scp/login.php
- remeber Username:Ostktuser, and Password: Password11

<img width="1835" height="938" alt="Capture12" src="https://github.com/user-attachments/assets/d4b45b68-e94d-4491-98b9-6c5651c967af" />

-How the homescreen looks after you log on 


</p>
<br /># osticket-prereqs
