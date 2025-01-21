![image](https://github.com/user-attachments/assets/4c9bd56b-aa6d-4d88-a8a8-d95c994e0e5c)<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Enabling Internet Information Services (IIS) with CGI
- PHP Manager
- Rewrite Module
- Microsoft Visual C++ Redistributables
- MySQL
- HeidiSQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>

<p>1). The first step to installing osTicket is creating a virtual machine (vm) by going to https://portal.azure.com/. Your virtual machine is going to need Windows 10 Pro, version 22H2, and a virtual machine with at least two VCPUS and 16 GBS of memory for an optimal experience whilst using the virtual machine. </p>

<br> 

<p>2). The second step is to connect to the virtual machine through the public ip address that the vm is assigned. You will connect to the vm through the remote desktop connection app. </p>

![image](https://github.com/user-attachments/assets/7b15e6d0-7986-4339-954b-c74461cb806b)

![image](https://github.com/user-attachments/assets/6a800e64-51a8-4ed5-b002-341277c2f5ed)

<hr>
<h3>Enabling IIS With CGI</h3>

<p>3). Once you are connected to the virtual machine you want to extract the installation files onto your desktop for ease of access. Then go to the control panel. From the control panel, open programs and select "Turn Windows Features On and Off". </p>

![image](https://github.com/user-attachments/assets/c304f75d-e39b-4c16-9a9a-52736b8fcf13)

![image](https://github.com/user-attachments/assets/9b26c19b-ce5f-4d6d-a1fe-d8504141e890)

<p>4). You want to select IIS and ensure that CGI and Common HTTP Features are selected so all of these features will be installed onto the virtual machine. </p>
<p><i>- World Wide Web Services -> Application Development Features -> [X] CGI [X] Common HTTP Features</p></i>

![image](https://github.com/user-attachments/assets/24f2e0e5-e9f0-4d5d-b52e-5ea896b8a60d)

![image](https://github.com/user-attachments/assets/04a28e2b-8c0a-4b38-93d2-e33317185d66)

<p><i>Important Note </i>- Ensure that all Common HTTP Features are checked.</p>

<p>To make sure that IIS is installed / enabled. Go to a browser of your choice. Search for 127.0.0.1 and something similiar should load when you google this IP.</p>

![image](https://github.com/user-attachments/assets/93434f2b-8f73-4f37-b3e0-8510c44ee5f5)

<hr>
<h3>Installing PHP Manager</h3>

<p>5). Now that IIS is enabled, from the installation files folder you will want to run the PHP Manager installer (PHPManagerForIIS_V1.5.0.msi). Go through the install wizard and complete the installation process. </p>

![image](https://github.com/user-attachments/assets/df6047ac-4c45-457e-8c07-51fe7087ff8a)

<hr>
<h3>Installing Rewrite Module</h3>

<p>6). Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi). Go through the install wizard and complete the installation process. </p>

![image](https://github.com/user-attachments/assets/41bf827b-5dc1-4666-81ec-1a4ecef20083)

<hr>
<h3>Installing Microsoft Visual C++ Redistributables</h3>

<p>7). The step is to install Microsoft Visual C++ Redistributables (VC_redist.x86.exe) which can be found in the installation files folder. Go through the install wizard and complete the installation process. </p>

![image](https://github.com/user-attachments/assets/62ffa7f0-fe11-4fa9-8641-620d30510cfa)

<hr>
<h3>Creating The PHP Folder</h3>

<p>8). Next you want to create a folder titled "PHP" on the C drive of the virtual mahchine. </p>

<p>9). From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP</p>

<p><i>Important Npte </i>- If this appears, choose to “Keep” the file:</p>

![image](https://github.com/user-attachments/assets/8caacf1a-6f66-4e81-9d9d-d645a77550c2)

![image](https://github.com/user-attachments/assets/df3c7553-ae26-49ce-b987-bb4a1934a76f)

<hr>
<h3>Installing MySQL</h3>

<p>10). Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) Run the setup wizard: Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->

Make the new root password: Password1</p>

![image](https://github.com/user-attachments/assets/dfe24f4b-2574-4ad7-8da7-59429e3ad9af)

![image](https://github.com/user-attachments/assets/9f6e5fe1-cce6-4b32-9e9e-9e93acfbec22)

![image](https://github.com/user-attachments/assets/7d0ab29c-3fb2-4efc-9081-b205d2427fe8)

<hr>
<h3>Registering the PHP within IIS</h3>

<p>11). Now that all the necessary files are installed you want to launch IIS through the windows search bar. Make sure to open IIS as an administrator and it should look like this. </p>

![image](https://github.com/user-attachments/assets/db0ad21c-4bba-42f3-aa9e-840d38e27d3a)

<p>12.) We will now want to register PHP from within IIS. Click on PHP Manager</p>

![image](https://github.com/user-attachments/assets/93617907-95b9-4efd-b529-8addc4a34a58)

<p>Register new PHP version.</p>

![image](https://github.com/user-attachments/assets/af49a3a1-3a74-4c77-9bbd-dbaf44410a73)

<p>You will want to provide a path to the php executable file (php-cgi.exe)). Go to C Drive -> PHP -> click on php-cgi file.</p>

![image](https://github.com/user-attachments/assets/8247ce27-0556-4c49-a56f-338be273a07e)

<p>Once the path is set it is necessary for the IIS server to restart to run the new PHP file. To restart the server either press stop then start for a hard restart or the restart button.</p>

![image](https://github.com/user-attachments/assets/1c8878ac-cc3e-4bea-9075-7c814e3441fc)

<hr>
<h3>Installing osTicket onto IIS</h3>

<p>13.) Install osTicket v1.15.8 by running the installer from the installation files folder. Afterwards, extract and copy "upload" folder to c:\inetpub\wwwroot -Within c:\inetpub\root, Rename "upload" folder to "osTicket". The names are case sensitive. 

Restart the IIS server again once this step is completed.</p>

![image](https://github.com/user-attachments/assets/4787f247-6e30-47f4-a204-e32d7cedb556)

<p>On IIS go to sites -> Default -> osTicket -On the right, click “Browse *:80”</p>

![image](https://github.com/user-attachments/assets/cd9981ac-fe87-4f64-8f9b-cc315c9740f2)

<hr>
<h3>Enabling PHP Extensions for osTicket</h3>

<p>Enable php_imap, php_intl, and php_opcache which are not enabled by default. IMAP [Internet Message Access Protocol] is used to get emails from your support inbox like GMail so customer queries can be turned into support tickets automatically. INTL [Internationalization] provides support for different languages and cultures for users that may access your site, OPcache is simply for improving performance and caching compiled PHP code.</p>

![image](https://github.com/user-attachments/assets/28788a88-6726-4f3b-897b-73ee05072d95)

<p>14). To enable the extensions: Go back to IIS, sites -> Default -> osTicket -Double click PHP manager -Click "Enable or disable an extension"</p>

![image](https://github.com/user-attachments/assets/95621d50-3745-4532-96c2-480538137dd1)

![image](https://github.com/user-attachments/assets/1da44db2-274b-4fe3-a518-3ef1907c8830)

<p>We will want to enable three extensions from here.

1.) php_imap.dll

2.) php_intl.dll

3.) php_opcache.dll</p>

![image](https://github.com/user-attachments/assets/2317dc56-6c41-4318-80ec-1ef9d3cd174e)

<p>15). Once we have those extensions enabled in IIS, we are going to want to rename one of the files in our osTicket folder. Open file explorer and search for C;\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

We are going to rename the file "ost-sampleconfig.php" to "ost-config.php"

Now that we have renamed the files, right click on the file and go to properties. From there click security, click on advance, and disable the inheritance. We will select Remove all inherited permissions from this object.

Now we will add new permissions.

Click Add</p>

![image](https://github.com/user-attachments/assets/9fef83c8-e613-4382-a890-fe3bce0d2ca3)

<p>Select a principal</p>

![image](https://github.com/user-attachments/assets/705fe4b0-35ab-4f45-93be-53db68b73585)

<p>Type "Everyone" in the box.</p>

![image](https://github.com/user-attachments/assets/a1d465c4-5f62-41f5-9d92-dc78e7d6edd0)

<p>Make sure Full Control and all the other boxes are checked.</p>

![image](https://github.com/user-attachments/assets/94e3169d-fee0-4546-8003-8fe4c7c9bd41)

<p>Click Apply and Ok.</p>

![image](https://github.com/user-attachments/assets/5e42f07a-eaba-4198-8c02-2c8f325e9ad5)

<p>Once that is done we will continue to setup osTicket in the browser. Click Continue on the osTicket browser page. Fill out the page as required except the Database Settings at the bottom of the page.</p>

<hr>
<h3>Installing HeidiSQL</h3>

<p>16). Run the HeidiSQL installer from the installation files folder. </p>

![image](https://github.com/user-attachments/assets/8315ed50-aee5-4bf8-bdc1-cda8bef49b0f)

<p>When the program is installed we create a new session on HeidiSQL.</p>

![image](https://github.com/user-attachments/assets/24fa7a30-7651-4852-9f63-619ea448849c)

<p>We want to make sure the username is root and the password is Password1.</p>

![image](https://github.com/user-attachments/assets/653e1d3a-17f2-4a0f-bda4-488faeb4504b)

<p>Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database Settings in the browser the username will be root and the password will be Password1.

We will now create a new database within HeidiSQL. In Heidi right click on the left side where is says "Unnamed", select "create new", and then select "database". Name the new database osTicket. Once we have the new database setup go back to the osTicket browser and under MySQL Database type in osTicket.</p>

![image](https://github.com/user-attachments/assets/1d80bcd7-c185-4a50-82b1-46cb25302bc2)

<hr>
<p>We then will want to set the permissions back to "Read" only in the ost-config.php file.</p>

![image](https://github.com/user-attachments/assets/fe09b480-4003-4a86-8a96-1cc74a779611)

![image](https://github.com/user-attachments/assets/e8567d17-03b0-42fa-b834-adfd0aa17192)

<hr>
<h3>osTicket Successfully Installed</h3>

<p>The last step after that is to login to osTicket on the browser.</p>

![image](https://github.com/user-attachments/assets/a6af7eb7-8430-45be-840c-f6bccca2c3c6)

![image](https://github.com/user-attachments/assets/8b162868-f61a-4a1d-aeb8-b901649eade8)

<p>Congratulations! You have now successfully installed and setup osTicket!</p>
<hr>
