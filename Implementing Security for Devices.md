# Implementing Security for Devices

---

## Password Algorithm Design Challenge

In this activity password algorithms were created for a user trying to secure a device or application. 

Chosen Algorithm: 
- Users birth month+Users birth day+ Users birth year
- Least favorite snack
- Random Symbol
- All even numbers from users phone number
- All odd numbers from users phone number added to
- Random lowercase letter
- Random uppercase letter
- Random uppercase letter
- Random symbol

  ex: 2040spinach#1833pOL&

This password algorithm would suffice for the creation of a unique secure password. The algorithm uses a mix or symbols, numbers, and letters as well as very lengthy. A user would need to have a password manager in order to use this algorthim as it is not easy to remember.

This information came from the Password Algortim Design Challenge

---

## Changing Ubuntu Password

In this activity the Ubuntu default password was changed to a more secure password created by the algorithm above. 

In order to accomplish this. Complete these steps:

- type "passwd"
- Enter the current password
- Enter new password
- Re-enter new password

If it was a success then the user should recieve a screen like this:

<img width="465" height="182" alt="image" src="https://github.com/user-attachments/assets/436b2519-d232-4459-a384-c7a22ad0cb23" />

Confirm the new password by running the command "sudo ls /root" then typing the new password

<img width="527" height="309" alt="image" src="https://github.com/user-attachments/assets/4e20ef2a-85ea-46ec-8934-fe7c68e61756" />

By entering 

"sudo adduser username & sudo usermod -aG sudo username"

The user can create a new user on the Ubuntu VM

This information came from the ChangingPassword_Ubuntu_Student Activity

---

## Enabling MFA in Ubuntu

In order to enable MFA in Ubuntu first the user must be logged into an account with admin privaleges

<img width="915" height="269" alt="image" src="https://github.com/user-attachments/assets/7cd6bb2e-beae-42ff-9db8-217741ca2983" />

Next update the VM by running "sudo apt update" then install the authenticator by running "sudo apt install libpam-google-authenticator -y" 

These commands update the VM's software packages and downloads the authenticator package

Next the "google-authenticator" command was entered

This generates a QR code that gives the user a secret key for the secondary authentication 

<img width="917" height="876" alt="image" src="https://github.com/user-attachments/assets/672c1985-06e6-476f-8701-1dcacfd7a9eb" />

Due to the fact that classroom Ipads do not have the app for the QR code the site "https://totp.danhersam.com/" was used in order to generate the code

Next in order to enable MFA and SSH for login the "sudo nano /etc/ssh/sshd_config" command was ran in order to edit the SSH server config

The following lines were changed:

-  KbdInteractiveAuthentication yes
-  UsePAM yes
-  PasswordAuthentication yes

Next save and exit and restart SSH by running "sudo systemctl restart ssh". Then open the SSH PAM config file by running "sudo nano /etc/pam.d/sshd". "auth required pam_google_authenticator.so" was added then it was saved. 

The MFA was tested by running "ssh username@localhost" 

This information came from the Enabling Multi-Factor Authentication (MFA) in Ubuntu activity

---

## Patching in Ubuntu

Patches are important because they secure the users data. When applications aren't updated regularly then hackers can use that to their advantage to steal information. Companies constantly roll out updates to better secure the users who use their app.

In ubuntu in order to see the list of upgradable packages enter "sudo apt list --upgradable"

<img width="606" height="65" alt="image" src="https://github.com/user-attachments/assets/bdd41173-c382-4516-af40-5df0f6de6d7b" />

<img width="913" height="877" alt="image" src="https://github.com/user-attachments/assets/1133fe6d-e743-48bb-8088-c76de4a0f6b3" />

In order to update these packages enter "sudo apt upgrade"

Ubuntu allows the user to better keep track of their updates by keeping a log file. In order to open it run "cat /var/log/apt/history.log"

By running "grep "2025-10" /var/log/apt/history.log" the user can view specific dates

<img width="920" height="545" alt="image" src="https://github.com/user-attachments/assets/e777865a-15e3-4818-b45a-05d3c11c1c0b" />

This image shows two different dates and the corresponding logs

By running "grep "nano" /var/log/apt/history.log" or "grep "firefox" /var/log/apt/history.log" the user can search for specific programs

<img width="439" height="105" alt="image" src="https://github.com/user-attachments/assets/2b0ed247-8014-4488-b76b-509b4c27fa35" />

<img width="452" height="47" alt="image" src="https://github.com/user-attachments/assets/9a31778f-2481-402e-9007-aafc7b709143" />

Or to search for a specific package "grep "google-authenticator" /var/log/apt/history.log"

<img width="904" height="56" alt="image" src="https://github.com/user-attachments/assets/9d14b3e8-2216-46a5-90ff-4bfb3b574c80" />

Due to the fact that ubuntu rotates logs the user must enter "tail -n 20 /var/log/apt/history.log" in order to find the most recent one 

<img width="912" height="306" alt="image" src="https://github.com/user-attachments/assets/51b175dd-f53b-461b-9ade-73a3b02eaeef" />

**Scenario** A hospital is using Ubuntu VM as their real computers and they do not update it

If the Ubuntu VM was never patched or updated then Zero day vulnerabilities could be created that hackers could exploit to get into the hospitals database and view private information. In order to prevent these exploits in the wild then the hospital should hire a Cisco certified support technician to change their ubuntu VM to automatically update so that there are no security vulnerabilities due to old software. These automatic updates ensure that all the hospitals software is updated.

The issue of patching can be solved by turning on automatic updates. In order to view the last automatic update in the Ubuntu VM the user must enter "ls -l /var/lib/apt/periodic/"

<img width="879" height="151" alt="image" src="https://github.com/user-attachments/assets/67f4fa8b-02cb-4fa0-bafa-85f05ac72c84" />

This inforation came from the Patching Ubuntu Activity

---

## NIST and OWASP

NIST (National Institute of Standards and Technology) and OWASP (Open Worldwide Security Project) are two companies that give guidelines on creating passwords for better device and application securitization. 

NIST’s main password ideas: 
• Length>complexity(The password needs to be greater in length rather than complex for a easier password to remember)
• Multi-Factor Authentication(This ensures that a hacker could not enter the users account by just gaining the password)
• Screen out bad passwords(This ensures that the hacker is not able to use the brute-force method of hacking)
OWASP’s main password ideas: 
• Authentication cheat sheet(This allows the user to easily find keys or codes)
• password storage cheat sheet(THis allows the user to easily find passwords)
• recognize credential stuffing(When a hacker tries to use known information about the user to gain access to their account)

This information came from the Implementing Security for Devices Student Notes

---

## Reflection

In order for a user to secure their device and applications they must be active constantly. To start a new account or user then the user must have a password algorithm to generate a strong password that is resistent to hacks. The password algorithm must create a password that is long in order to create more possible outcomes for a potential hacker to guess. It must also use a mix of symbols, numbers and letters. If the algorithm generates a password that is hard to remember then the user can use a password manager or email the password to themselves. After that the user must always update the device and its applications to ensure that hackers can't exploit out of date software. 
