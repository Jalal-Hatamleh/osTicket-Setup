![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

# Prerequisites and Installation Guide for osTicket

In this home lab, I will set up and configure osTicket on an Azure Windows VM to showcase and enhance my skills in both administration and user management.

## Technologies and Environments Involved
* **Microsoft Azure** (Virtual Machines/Compute)
* **Remote Desktop**
* **Internet Information Services (IIS)**

## Operating Systems in Use
* **Windows 10 Pro** (Version 22H2)

## Installation Process
### 1. Set up a Windows 10 Virtual Machine on Azure with 4 vCPUs
* **Name:** osticket-vm
* **Username:** jalal-lab-os
* **Password:** Password123!

### 2. Access the VM via Remote Desktop

### 3. Download and Extract osTicket Files
* Download the [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and extract it to your desktop. The extracted folder will be named “osTicket-Installation-Files”.

### 4. Install and Enable IIS with CGI in Windows
* Go to **'World Wide Web Services'** -> **'Application Development Features'** and check the box for **CGI**.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

### 5. Install PHP Manager for IIS
* From the “osTicket-Installation-Files” folder, install **PHP Manager for IIS** (PHPManagerForIIS_V1.5.0.msi).

### 6. Install the Rewrite Module
* Install the **Rewrite Module** (rewrite_amd64_en-US.msi).
![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

### 7. Set Up PHP Folder
* Create the directory **C:\PHP.**
* Unzip **PHP 7.3.8** (php-7.3.8-nts-Win32-VC15-x86.zip) into **C:\PHP.**


### 8. Install Required Software
* From the “osTicket-Installation-Files” folder, install **VC_redist.x86.exe** and **MySQL 5.5.62** (mysql-5.5.62-win32.msi).

     ∘ Choose **Typical Setup** and launch the configuration wizard after installation.

     ∘ Configure with:

      ■ Username: root
      ■ Password: root


![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)



### 9. Register PHP with IIS

* Open IIS as an admin.
* Register PHP from within IIS: **PHP Manager -> C:\PHP\php-cgi.exe.**
* Reload IIS by stopping and starting the server.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 10. Install osTicket v1.15.8

* In the “osTicket-Installation-Files” folder, extract **osTicket-v1.15.8.zip** and copy the **'upload'** folder to **C:\inetpub\wwwroot.**

* Rename the folder to **'osTicket'** (Ensure the name contains no spaces).

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 11. Enable PHP Extensions

* Go back to IIS -> **Sites** -> **Default** -> **osTicket**.

* Open **PHP Manager** and enable the following extensions:

     ∘ **php_imap.dll**

     ∘ **php_intl.dll**

     ∘ **php_opcache.dll**

    Refresh the site in your browser.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 12. Rename ost-sampleconfig.php to ost-config.php

* Navigate to **C:\inetpub\wwwroot\osTicket\include** and rename **ost-sampleconfig.php** to **ost-config.php.**

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 13. Set Permissions for ost-config.php

* Right-click on **ost-config.php**, disable inheritance, remove all permissions, and grant **Everyone** full control.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 14. Continue osTicket Setup in the Browser

* Access the setup page via http://localhost/osTicket/scp/login.php.
* Fill in the required details:

     ∘ **Name Helpdesk**

     ∘ **Default email** (receives emails from customers)

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 15. Set Up the MySQL Database

* Open **HeidiSQL** and create a session using the **username and password: root/root.**
* Create a new database named **'osTicket.'**

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 16. Complete osTicket Setup

* In the browser, configure MySQL details:

      ■ MySQL Database: osTicket
      ■ MySQL Username: root
      ■ MySQL Password: root

* Click **Install Now!.**

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)
![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


### 17. Access osTicket

* Once installed, access the help desk login page: http://localhost/osTicket/scp/login.php.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)


* End User's osTicket URL: http://localhost/osTicket/.

![Installation Screenshot](https://github.com/Jalal-Hatamleh/osTicket-Setup/blob/main/images/1.png?raw=true)



**Key Takeaways and Skills Acquired**  
---

In this project, I set up **osTicket** on an Azure Windows VM, which gave me the chance to practice my admin and user management skills. I worked with **Windows 10**, and installed **IIS**, **PHP**, and **MySQL** to make sure osTicket ran smoothly. Along the way, I also set up important tools like **PHP Manager** and the **Rewrite Module.** I had to configure **PHP extensions**, set permissions, and create a MySQL database. This project really helped me get a better grasp of how to install web applications, configure PHP, and manage databases. Plus, it gave me a solid understanding of troubleshooting during installations and handling **Azure VM** and **IIS server management**.
