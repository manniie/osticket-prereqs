<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This section outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
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

<h2>Installation Steps</h2>

<h3>Enabling IIS With CGI</h3>

![image](https://github.com/user-attachments/assets/2331c76c-cced-4990-a6af-fcdf737a2086)

<p>
Enabling Internet Information Services (IIS) with CGI allows for the machine to run a web server which is necessary for osTicket to function. 
</p>
<hr>
<h3>Installing PHP Manager</h3>

![image](https://github.com/user-attachments/assets/df6047ac-4c45-457e-8c07-51fe7087ff8a)

<p>
Installation of PHP Manager helps configure and manage PHP correctly for optimal performance and compatibility. 
  
</p>
<hr>
<h3>Installing Rewrite Module</h3>

![image](https://github.com/user-attachments/assets/41bf827b-5dc1-4666-81ec-1a4ecef20083)

<p>
Installation of Rewrite Module is required for the web server to make sure the URLs are easy to read and looks clean as well.
</p>
<hr>
<h3>Installing Microsoft Visual C++ Redistributables</h3>

![image](https://github.com/user-attachments/assets/62ffa7f0-fe11-4fa9-8641-620d30510cfa)

<p>
Installation of Microsoft Visual C++ Redistributables is required for osTicket to run smoothly and run any code that is written in C++.  
</p>
<hr>
<h3>Installing MySQL</h3>

![image](https://github.com/user-attachments/assets/7d0ab29c-3fb2-4efc-9081-b205d2427fe8)

<p>Installation of MySQL which is used to create a database which holds all the important data created by osTicket. Furthermore, it organizes the data, allows for quick searching, and allows for osTicket to create tickets.</p>
<hr>
<h3>Registering the PHP within IIS</h3>

![image](https://github.com/user-attachments/assets/b740df8b-579d-4d97-afff-8f5441f1dc4b)

<p>Registering the PHP allows for the IIS to know how to process and run the PHP code properly, in other words allow for the osTicket website to run on the machine.</p>
<hr>
<h3>Installing osTicket onto IIS</h3>

![image](https://github.com/user-attachments/assets/4787f247-6e30-47f4-a204-e32d7cedb556)

<p>Installing osTicket requires a web server which we used IIS for this example. Using IIS allows for everything to be managed in one place.</p>
<hr>
<h3>Enabling PHP Extensions for osTicket</h3>

![image](https://github.com/user-attachments/assets/0c16c139-d134-4441-863f-f0907a8824c0)

<p>Enabling php_imap, php_intl, and php_opcache which are not enabled by default. IMAP [Internet Message Access Protocol] is used to get emails from your support inbox like GMail so customer queries can be turned into support tickets automatically. INTL [Internationalization] provides support for different languages and cultures for users that may access your site, OPcache is simply for improving performance and caching compiled PHP code.</p>
<hr>
<h3>Installing HeidiSQL</h3>

![image](https://github.com/user-attachments/assets/8315ed50-aee5-4bf8-bdc1-cda8bef49b0f)

<p>HeidiSQL is a tool for managing MySQL which is the database that osTicket uses.</p>
