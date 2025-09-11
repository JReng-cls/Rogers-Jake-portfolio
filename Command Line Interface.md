
## Command Line Interface Project
In this project we learn various commands that help us when navigating through the terminal. In networking, the terminal is used for easy access connection to a router in order to configure a certain network.
## Linux Commands

<img width="500" height="540" alt="image" src="https://github.com/user-attachments/assets/d5c427e6-b645-45d5-bc8e-a4fbc88668b3" /> <img width="500" height="540" alt="image" src="https://github.com/user-attachments/assets/7de2dea4-388c-46a1-9033-0372884c66b6" />

In these two images you can see the terminal in Virtual Machines. We  used this application to simulate what a terminal is used for. We started with the most basic commands 

pwd(Print Working Directory)- This command allows the user to find where they are in the computer. The output for this command is your root directory followed by the folders or other directories you are in such as home/user/Documents/Essays

cd(Change Directory)- This command is used to navigate through directories and folders. There are a few different forms of this command that can be used:

cd ~/Directory Name- Takes you to Directory Name

cd .. - Takes you one level backwards in your current directory

cd ../..- Takes you two levels backwards in your current directory. Can be used to move more than two levels by adding additional "/.."

ls(List)- This command lists all files and folders in your current directory

ls -a- This version of list displays all of the hidden files within the folder

mkdir(Make Directory)- This command makes a new directory in your current directory

touch- This command creates new files

cat- This command displays all the contents of a selected file

echo- This command repeats whatever you type into but it can also add content to files ex. Adding "Test 1" to a googledoc.txt file- echo "Test 1" > googledoc.txt

nano- This command is used to edit files

## House Activity 

This activity was created in a Github repository. The repository was called house and it contained other folders that were the different rooms in the house. Different rooms contained files, hidden files, etc that were all clues to completing the activity.

To begin this activity first we had to download the map of the house aka the Github repository. 

[
](https://mail.google.com/mail/u/0?ui=2&ik=bdca38649d&attid=0.1&permmsgid=msg-a:r-2373642107752033430&th=19933c44ab09d03c&view=fimg&fur=ip&permmsgid=msg-a:r-2373642107752033430&sz=s0-l75-ft&attbid=ANGjdJ9PAHXvjoUfEDnDxgLzL9NTUbnyUgvGKPj9efNvhIhSEDD7x42K6mO4vrzMuEWHtw6UYM6pInJ0kToRiw631TjK_ICFeznqBNA0SDioFe_w6GHWpWuu7PjyUB0&disp=emb&realattid=ii_mfe0485t0&zw)<img width="500" height="729" alt="image" src="https://github.com/user-attachments/assets/c1590441-a053-4a7a-9c99-3a59c3118630" /> [
](https://mail.google.com/mail/u/0?ui=2&ik=bdca38649d&attid=0.2&permmsgid=msg-a:r-2373642107752033430&th=19933c44ab09d03c&view=fimg&fur=ip&permmsgid=msg-a:r-2373642107752033430&sz=s0-l75-ft&attbid=ANGjdJ9G9iK6Q4KODYrDp7X9FjFO5ia8U4sgSNf6VTCwPSiajBWDXanbMwrIr3sqOl4EgLoCS1GpC2855hZcRu_mK6aBs0SZBQnG9zqwQnr68JspBafgqQoF9Gvdu78&disp=emb&realattid=ii_mfe04tuw1&zw)<img width="500" height="729" alt="image" src="https://github.com/user-attachments/assets/23c287e3-108e-4e30-9861-92046db84eee" />

Following the insturctions provided by our teacher. First updating by running "sudo apt update." Next sudo apt install -y git in order to be able to use the git commands in the VM terminal. Then changing directories to Documents followed by cloning the repository in Documents. "cd ~/Documents ... clone https://github.com/thewangclass/CK-Building-Content-Knowledge-Workshop.git." Finnaly after moving to the new directory by using "cd CK-Building-Content-Knowledge-Workshop.git." and using "git pull" to make sure I had the most updated version. Originally when trying to install the github commands I recieved an error message. In order to fix this problem my teacher and I had to run the sudo nano /etc/systemd/resolved.conf command to open up the nano control. Following that we navigated to the DNS server and removed the # from the name and set it = to 8.8.8.8. Finnaly we restarted the system by running the sudo systemctl restart systemd-resolved.

After all that I could then begin the assignment. 

The first thing I had to do was rename the directories for the activity so that I could navigate easier. Task one was to enter the friends house. I did this by using "cd ~/Documents/House/Activity/house". I listed all the folders in one command in order to be efficient and not have to type out a seperate command line for each folder. The next task was to see what is around the house. Using the "ls" command I found directories labled "bedroom1, bedroom2, garage, kitchen, main_entrance". Next I had to enter the main_entrance so I used the "cd main_entrance" command. In order to find and read the instructions left by the friend I used the "ls" command followed by "cat instructions.txt". To move back to the house folder I used the "cd .." command to move one level backwards. Next I had to move to the kitchen by using the "cd kitchen" command. Using the "ls" command I found all the food and drink left around the house.
