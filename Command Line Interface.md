## Command Line Interface Project

In this project we learn various commands that help us when navigating through the terminal. In networking, the terminal is used for easy access connection to a router in order to configure a certain network.


# Table of Contents

- [Tree Diagrams](#tree-diagrams)
- [Key Linux Commands](#key-linux-commands)
- [House Activity](#house-activity)
	- [Download Phase](#download-phase)
	- [Navigating the House](#navigating-the-house)
- [Reflection](#reflection)


---


## Tree Diagrams

	Root Directory

	└──HomeFolder 
	├──Documents
	├──Photos├── Essay.docx         
	└──Music └── Gatsby.jpg

In Map the Maze part 1 we created tree diagrams to visualize directories in computers. My example directory shows the Root Directory which is always listed first. Next is typically user folders or home folders. Finnaly I created files and nested directories. 

---


## Key Linux Commands

| Command         | Description                                                                                  | Example Usage                        |
|-----------------|----------------------------------------------------------------------------------------------|--------------------------------------|
| `pwd`           | Print Working Directory – shows your current location in the filesystem.                     | `pwd`                                |
| `cd`            | Change Directory – navigate between folders.                                                 | `cd ~/DirectoryName`<br>`cd ..`      |
| `ls`            | List files and folders in the current directory.                                             | `ls`<br>`ls -a`                      |
| `mkdir`         | Make Directory – create a new folder.                                                        | `mkdir new_folder`                   |
| `touch`         | Create a new file.                                                                           | `touch file.txt`                     |
| `cat`           | Display the contents of a file.                                                              | `cat file.txt`                       |
| `echo`          | Print text or add content to a file.                                                         | `echo "Test 1" > file.txt`           |
| `nano`          | Edit files in the terminal.                                                                  | `nano file.txt`                      |

<div align="center">
	<img width="400" alt="image" src="https://github.com/user-attachments/assets/d5c427e6-b645-45d5-bc8e-a4fbc88668b3" />
	<img width="400" alt="image" src="https://github.com/user-attachments/assets/7de2dea4-388c-46a1-9033-0372884c66b6" />
</div>

These images provide multiple examples of these commands being used.

---

## House Activity

This activity was created in a Github repository. The repository was called house and it contained other folders that were the different rooms in the house. Different rooms contained files, hidden files, etc that were all clues to completing the activity.

To begin this activity first we had to download the map of the house aka the Github repository.

<div align="center">
	<img width="350" alt="image" src="https://github.com/user-attachments/assets/c1590441-a053-4a7a-9c99-3a59c3118630" />
	<img width="350" alt="image" src="https://github.com/user-attachments/assets/23c287e3-108e-4e30-9861-92046db84eee" />
</div>


### Download Phase

Following the insturctions provided by our teacher. First updating by running "sudo apt update." Next sudo apt install -y git in order to be able to use the git commands in the VM terminal. Then changing directories to Documents followed by cloning the repository in Documents. "cd ~/Documents ... clone https://github.com/thewangclass/CK-Building-Content-Knowledge-Workshop.git." Finnaly after moving to the new directory by using "cd CK-Building-Content-Knowledge-Workshop.git." and using "git pull" to make sure I had the most updated version. Originally when trying to install the github commands I recieved an error message. In order to fix this problem my teacher and I had to run the sudo nano /etc/systemd/resolved.conf command to open up the nano control. Following that we navigated to the DNS server and removed the # from the name and set it = to 8.8.8.8. Finnaly we restarted the system by running the sudo systemctl restart systemd-resolved.


### Navigating the House

<div align="center">
	<img width="350" alt="image" src="https://github.com/user-attachments/assets/1a532206-5586-4d7b-ac0d-14643b4dbb0d" />
	<img width="350" alt="image" src="https://github.com/user-attachments/assets/c8a915c3-bee3-48e0-bc25-f4f2b1c0114b" />
</div>




The first thing I had to do was rename the directories for the activity so that I could navigate easier. Task one was to enter the friends house. I did this by using "cd ~/Documents/House/Activity/house". I listed all the folders in one command in order to be efficient and not have to type out a seperate command line for each folder. The next task was to see what is around the house. Using the "ls" command I found directories labled "bedroom1, bedroom2, garage, kitchen, main_entrance". Next I had to enter the main_entrance so I used the "cd main_entrance" command. In order to find and read the instructions left by the friend I used the "ls" command followed by "cat instructions.txt". To move back to the house folder I used the "cd .." command to move one level backwards. Next I had to move to the kitchen by using the "cd kitchen" command. Using the "ls" command I found all the food and drink left around the house. Using the "rm" command I was able to remove items from the kitchen folder. By putting a / in between items when using the "rm" command such as "rm notes.txt/essays" you can remove multiple items in one command. Next I used the "ls -a" command to find the rotten bananas file. Using "rm" again, I was able to remove these files. Next I navigated to bedroom1 and then to bedroom2 by using the change directories command. When the lights went out, I used the "pwd" command to print my working directory to know where I am in the house. Next I went to the garage by using "cd garage". Using "rm" I removed trash from each box. Finnaly I left a note by using "touch note.txt" then "echo "Thank you for trusting me!" > note.txt".

---

## Trouble Shooting Network Issues

In this activity we took out knowledge of the command line interface, on a Mac and VM, and used it to fix basic network issues on computers. Problems like these could be that your computer isn't connecting to wifi or can't look up a website.

Our class broke down the four steps to identifying the problem

1. Check whether your device is connected to the internet either by wifi or ethernet
2. Verify that you device has an ip address by going into the terminal and running ifconfig on a mac or ip addr on Ubuntu
3. Test whether your device can reach the internet at all by going into the terminal and pinging a common website like 8.8.8.8(google.com)
4. Test whether your device can reach the internet by website name, this could reveal problems with your DNS

These four steps should help when trying to identrify a networking issue.

| Term                         | Definition                                                                                                   | 
|------------------------------|--------------------------------------------------------------------------------------------------------------|
| `Wi-Fi/Ethernet`             | Signal carrier- connects your device to the internet .                                                       |
| `Network Adapter/Interface`  | The hardware that lets your computer communicate with the internet ex. NIC (Network Interface Card).         |
| `IP Address`                 | Identifiable address for devices within a network ex. 192.168.1.25 Private IPs : 10… , 192…, 172..,          |
| `Defualt Gateway(Router)`    | The device that connects your local network to the internet                                                  |
| `DNS(Domain Name System)`    | Converts the IP address of websites into a user-readable format.                                             |
| `Ping`                       | Tests connection between two devices within in a network Use: ping -c 4 8.8.8.8                              |
| `NAT/Shared networking(UTM)` | Pools all the IP addresses of devices within a network to create one IP address that identifies the network. |
| `Bridged Networking(UTM)`    | Acts like a completely separate computer Gets its own IP address from the router.                            |

Knowing these terms is imperative to success when troubleshooting networks using the command line interface


## Reflection

By using the commands in multiple different activities I was able to solidify my understanding of these commands. Using visual tools like tree diagrams or the finder in Virtual Machines helped me better understand how to navigate using the terminal. Basic commands like "cd" or "rm" can be strung together to effieciently navigate through your computers files. These commands lay the foundation for my learning of the terminal.
