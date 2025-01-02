<div style="border: 1px solid black; padding: 10px;">

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

# osTicket - Prerequisites and Installation

In this home lab, I will deploy and configure osTicket on an Azure Windows VM to demonstrate and refine both my administrative and user management skills.

## Environments and Technologies Used
* Microsoft Azure (Virtual Machines/Compute)
* Remote Desktop
* Internet Information Services (IIS)

## Operating Systems Used
* Windows 10 Pro, version 22H2

## Installation Steps
### 1. Create an Azure Virtual Machine (Windows 10, 4 vCPUs)
* Name: osticket-vm
* Username: jalal-lab-os
* Password: Password123!

### 2. Log into the VM with Remote Desktop

### 3. Download and Unzip osTicket Files
* Download the [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and unzip it on your desktop. The folder should be called “osTicket-Installation-Files”.

### 4. Install / Enable IIS with CGI Support
* Go to World Wide Web Services -> Application Development Features and ensure CGI is selected.
![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

### 5. Install PHP Manager for IIS
* From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi).

### 6. Install the Rewrite Module
* Install the Rewrite Module (rewrite_amd64_en-US.msi).
![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

### 7. Set Up PHP Folder
* Create the directory C:\PHP.
* Unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP.


### 8. Install Required Software
* From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe and MySQL 5.5.62 (mysql-5.5.62-win32.msi).

     ∘ Choose Typical Setup and launch the configuration wizard after installation.

     ∘ Configure with:

      ■ Username: root
      ■ Password: root


![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)



### 9. Register PHP with IIS

* Open IIS as an admin.
* Register PHP from within IIS: PHP Manager -> C:\PHP\php-cgi.exe.
* Reload IIS by stopping and starting the server.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 10. Install osTicket v1.15.8

* From the “osTicket-Installation-Files” folder, unzip osTicket-v1.15.8.zip and copy the upload folder to C:\inetpub\wwwroot.

* Rename the folder to osTicket (Ensure there are no spaces in the name).

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 11. Enable PHP Extensions

* Go back to IIS -> Sites -> Default -> osTicket.

* Open PHP Manager and enable the following extensions:

     ∘ php_imap.dll

     ∘ php_intl.dll

     ∘ php_opcache.dll

    Refresh the site in your browser.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 12. Rename ost-sampleconfig.php to ost-config.php

* Navigate to C:\inetpub\wwwroot\osTicket\include and rename ost-sampleconfig.php to ost-config.php.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 13. Set Permissions for ost-config.php

* Right-click on ost-config.php, disable inheritance, remove all permissions, and grant Everyone full control.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 14. Continue osTicket Setup in the Browser

* Access the setup page via http://localhost/osTicket/scp/login.php.
* Fill in the required details:

     ∘ Name Helpdesk

     ∘ Default email (receives emails from customers)

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 15. Set Up the MySQL Database

* Open HeidiSQL and create a session using the username and password: root/root.
* Create a new database called osTicket.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 16. Complete osTicket Setup

* In the browser, configure MySQL details:

      ■ MySQL Database: osTicket
      ■ MySQL Username: root
      ■ MySQL Password: root

* Click Install Now!.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)
![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 17. Access osTicket

* Once installed, access the help desk login page: http://localhost/osTicket/scp/login.php.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


* End User's osTicket URL: http://localhost/osTicket/.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)



**Takeaways and Key Skills Developed**  
---

In this project, I successfully installed and set up **osTicket** on an Azure Windows VM to practice both admin and user skills. I configured the VM with Windows 10, installed IIS, PHP, and MySQL to support osTicket, and learned how to install and configure essential dependencies like PHP Manager and the Rewrite Module. The process also involved setting up and configuring PHP extensions, managing permissions, and creating a MySQL database. This project improved my understanding of web-based application installation, PHP configuration, and database management while also helping me troubleshoot issues during installation and configuration. It also provided hands-on experience with Azure VM setup and managing Windows IIS servers.

</div>
