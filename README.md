# osTicket Installation and Deployment

<br>

## Overview

This project documents the installation and deployment of the osTicket help desk ticketing system in a Microsoft Azure Windows virtual machine.

The environment was configured with IIS, PHP, and MySQL before deploying osTicket and connecting it to a local database. The installation was then verified and post-installation security cleanup was performed.

This is Part 1 of a three-part osTicket help desk project.

### Project Navigation

[Part 1: Installation](https://github.com/AGZ2789/osticket-installation) → [Part 2: Configuration](https://github.com/AGZ2789/osticket-configuration) → [Part 3: Ticket Lifecycle](https://github.com/AGZ2789/osticket-ticket-lifecycle)

<br>

## Environments and Technologies Used

- Microsoft Azure
- Windows 10
- Remote Desktop Protocol (RDP)
- Internet Information Services (IIS)
- PHP 7.3.8
- PHP Manager for IIS
- MySQL 5.5.62
- HeidiSQL
- osTicket v1.15.8

<br>

## Azure Virtual Machine Deployment

A Windows 10 virtual machine was deployed in Microsoft Azure to host the osTicket environment. The VM was configured with 4 vCPUs and accessed remotely using RDP.

<img width="609" height="912" alt="image" src="https://github.com/user-attachments/assets/3c3afda6-a226-43e4-8365-91fadfb7c9ce" />

<br><br>

## IIS and PHP Configuration

Internet Information Services (IIS) was enabled with CGI support to provide the web server required by osTicket.

<img width="1126" height="912" alt="image" src="https://github.com/user-attachments/assets/aed5dd87-dcd4-40fc-8b38-7212a8118d19" />

---

PHP 7.3.8 was installed and registered with IIS through PHP Manager using the PHP CGI executable.

---

<img width="1126" height="912" alt="image" src="https://github.com/user-attachments/assets/9c433eee-3031-48bd-b34d-2f64e59f0e41" />

<br><br>

## osTicket Deployment

The osTicket application files were extracted and deployed into the IIS web root at `C:\inetpub\wwwroot`.


<img width="669" height="912" alt="image" src="https://github.com/user-attachments/assets/61584c10-f504-4d2a-9de5-9d7f196df5e0" />

---

During the installer prerequisite check, additional PHP extensions were required or recommended. The necessary extensions, including IMAP, Intl, and OPcache, were enabled through PHP Manager.

---

<img width="1126" height="912" alt="image" src="https://github.com/user-attachments/assets/b47c9e2a-e270-4cb3-8107-489f35c455e2" />


<br><br>

## Database Configuration

MySQL was installed as the database server and HeidiSQL was used to connect to the server and create the database used by osTicket.

<img width="819" height="912" alt="image" src="https://github.com/user-attachments/assets/6a9898b2-002c-46f0-b1ce-9160f5762cab" />


<br><br>

## Installation Verification

After connecting osTicket to the MySQL database, the installation completed successfully and the help desk application was ready for post-installation configuration.


<img width="1288" height="827" alt="image" src="https://github.com/user-attachments/assets/38bfc6c8-cf8a-4727-bbd6-29fc540af3db" />


<br><br>

## Post-Installation Security Cleanup

After installation, the osTicket setup directory was removed and the permissions on `ost-config.php` were restricted to remove unnecessary write access.


<img width="1102" height="912" alt="image" src="https://github.com/user-attachments/assets/a1d0a04a-8274-4fcf-9120-53baa537d915" />


<br><br>

## Challenges and Troubleshooting

During the osTicket prerequisite check, several PHP extensions were not initially enabled. I used PHP Manager in IIS to enable the required extensions, including IMAP, Intl, and OPcache, before continuing the installation successfully.

<br>

## Key Takeaways

- Deployed a Windows virtual machine in Microsoft Azure
- Configured IIS and PHP to support a web-based application
- Deployed osTicket within the IIS web root
- Configured MySQL and created the osTicket database
- Resolved missing PHP-extension requirements
- Verified successful application installation
- Performed post-installation security cleanup
