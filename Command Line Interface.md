[Homepage]: https://jreng-cls.github.io/Rogers-Jake-portfolio/
[Homepage][Homepage]
## Command Line Interface Project
In this project we learn various commands that help us when navigating through the terminal. In networking, the terminal is used for easy access connection to a router in order to configure a certain network.
## Linux Commands

<img width="506.5" height="540" alt="image" src="https://github.com/user-attachments/assets/d5c427e6-b645-45d5-bc8e-a4fbc88668b3" /> 
<img width="506.5" height="540" alt="image" src="https://github.com/user-attachments/assets/7de2dea4-388c-46a1-9033-0372884c66b6" />

In these two images you can see the terminal in Virtual Machines. We  used this application to simulate what a terminal is used for. We started with the most basic commands 

pwd(Print Working Directory)- This command allows the user to find where they are in the computer. The output for this command is your root directory followed by the folders or other directories you are in such as home/user/Documents/Essays

cd(Common Directory)- This command is used to navigate through directories and folders. There are a few different forms of this command that can be used:

cd ~/

cd .. 

cd ../..

ls(List)- This command lists all files and folders in your current directory

mkdir(Make Directory)- This command makes a new directory in your current directory

touch- This command creates new files

cat- This command displays all the contents of a selected file

echo- This command repeats whatever you type into but it can also add content to files ex. Adding "Test 1" to a googledoc.txt file- echo "Test 1" > googledoc.txt

nano- This command is used to edit files

## House Activity 




In order to fix this problem my teacher and I had to run the sudo nano /etc/systemd/resolved.conf command to open up the nano control. Following that we navigated to the DNS server and removed the # from the name and set it = to 8.8.8.8. Finnaly we restarted the system by running the sudo systemctl restart systemd-resolved
