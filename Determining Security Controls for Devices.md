
# Table of Contents

- [Determining Security Controls for Devices](#determining-security-controls-for-devices)
- [Cybersecurity Basics for Devices](#cybersecurity-basics-for-devices)
- [Common Attacks](#common-attacks)
- [IP Addresses](#ip-addresses)
- [Terminal Testing](#terminal-testing)
- [Reflection](#reflection)

---

### Determining Security Controls for Devices

These projects and activities show the different ways that computers secure sensitive data and how computer users can maintain proper device securitization.

---


## Cybersecurity Basics for Devices

Most attacks upon networks are due to user error. Devices are access points into a network and once a hacker is inside they can reach all unsecure data within that network. It is important to keep devices secure especially in a proffesional enviorment where lost data can cost thousands.

In order to properly maintain device securitization, it is important to follow the **CIA Triad**:

- **Confidentiality:** Ensuring that sensitive data is only accessed by individuals with authorization
- **Integrity:** Ensuring that the information/data un-corrupted, accurate, and trustworthy. Ensure that your data hasn't been tampered with on purpose or by accident
- **Availability:** Making sure that information and systems are accessible to authorized users

---

### Common Device Weaknesses

- **Outdated applications or operating systems:** It is important to keep your OS or applications updated as the companies that make them are constantly updating and adding security measures to their product. When users don't update their systems it can lead to corrupted or destroyed data. This also leaves you vulnerable to hackers trying to access your information through your account on the OS or application. On Mac desktop you can check your version by entering `system_profiler SPSoftwareDataType` into the terminal.
- **Weak Passwords:** Weak or repeated passwords leave you vulnerable to hackers. It is helpful to use algorithms to generate passwords or in some cases the website may have a password generator for you that develops a strong password
- **Open Ports:** Open ports are a gateway for hackers to access networks. Closing unused ports is like locking your door so strangers can't come in.

**Well-known ports include:**

| Port  | Protocol/Service                        |
|-------|-----------------------------------------|
| 80    | HTTP (Hypertext Transfer Protocol)      |
| 443   | HTTPS (HTTP Secure)                     |
| 22    | SSH (Secure Shell Protocol)             |
| 25    | SMTP/TCP (Simple Mail Transfer Protocol)|
| 110   | POP3 (Post Office Protocol Version 3)   |
| 143   | IMAP (Internet Message Access Protocol) |
| 3389  | RDP (Remote Desktop Protocol)           |
| 53    | DNS (Domain Name System)                |

---


## Common Attacks

- **Phishing:** Mass email/large audience searching for clicks through emails that contain links to viruses, unsecure websites that steal information, etc. This can be prevented by confirming with the sender of the email, logging into the app or website from the email and seeing if that has a notification, or not clicking on any random links that appear in your inbox.
- **Spear Phishing:** Phishing specifically targeted at one person, company, business, etc., most commonly financial institutions. This includes the same preventative measures as phishing.
- **Pretexting:** Stories created to trick people into sending money. This can be prevented by only sending money to known numbers.
- **Tailgating:** Accessing someone else’s device by using them shortly after the owner is done in hopes that they left it open. This can be prevented by only granting access to individuals with authorization and logging out of devices when you finish your work.
- **Baiting:** Tricking people into giving hackers access to their computers through links or physically leaving USB drives out that can damage or destroy your device. This can be prevented by not using any unknown USB drives.

---


## IP Addresses

| IP Range               | What It Means                                                       | Example Seen in Class                                   |
|------------------------|---------------------------------------------------------------------|---------------------------------------------------------|
| 192.168.x.x            | Private IP (home/school networks) Assigned by router/DHCP           | Common on Wi-Fi networks.                               |
| 10.x.x.x               | Private IP (large organizations,  VMs often use this)               | Ubuntu VM in Shared/Bridged.                            |
| 172.16.x.x –172.31.x.x | Private IP (less common but valid)                                  | Could appear in some networks                           |
| 169.254.x.x            | Self-assigned IP (means the device didn’t get one from the router)  | Happens if Wi-Fi is on but the router is not responding |

Knowing these IP addresses is important when troubleshooting network issues.

---


## Terminal Testing

By running version commands in the terminal you can see the versions of all your applications. A partner and I looked at OpenSSL, Firefox, LibreOffice, Python, Apache HTTP Server, GIMP, Java, and OpenSSH. We noticed that many of these systems were not up to date. This could result in problems such as:

- Encrypted data could be leaked
- Web services might not be up to date
- Lost or damaged files
- Coding issues
- Limited user interface

---


### Reflection

These activities and projects explain how to be a responsible device user. It is important to keep your device up-to-date and secure. This is done both virtually on the device and physically. Users must know where their device is at all times and it should be secure. Applications need to be secured with strong passwords. Networks need to be secured through closed ports and firewalls. It is important to maintain company regulations about authorization in restricted areas.


