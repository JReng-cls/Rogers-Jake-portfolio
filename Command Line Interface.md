
# Table of Contents

- [Command Line Interface Project](#command-line-interface-project)
- [Key Linux Commands](#key-linux-commands)
- [House Activity](#house-activity)
	- [Download Phase](#download-phase)
	- [Navigating the House](#navigating-the-house)


## Command Line Interface Project
In this project we learn various commands that help us when navigating through the terminal. In networking, the terminal is used for easy access connection to a router in order to configure a certain network.

## Tree Diagrams

	Root Directory

	└──HomeFolder 
	
 	├──Documents
	
 	├──Photos├── Essay.docx         
	
 	└──Music └── Gatsby.jpg

In Map the Maze part 1 we created tree diagrams to visualize directories in computers. My example directory shows the Root Directory which is always listed first. Next is typically user folders or home folders. Finnaly I created files and nested directories. 

## Key Linux Commands

<img width="500" height="540" alt="image" src="https://github.com/user-attachments/assets/d5c427e6-b645-45d5-bc8e-a4fbc88668b3" />
<img width="500" height="540" alt="image" src="https://github.com/user-attachments/assets/7de2dea4-388c-46a1-9033-0372884c66b6" />

| Command         | Description                                                                                  | Example Usage                        |
|-----------------|----------------------------------------------------------------------------------------------|--------------------------------------|
| `pwd`           | Print Working Directory – shows your current location in the filesystem.                     | `pwd`                                |
| `cd`            | Change Directory – navigate between folders.                                                 | `cd ~/DirectoryName`<br>`cd ..`      |
| `ls`            | List files and folders in the current directory.                                             | `ls`<br>`ls -a`                      |
| `mkdir`         | Make Directory – create a new folder.                                                        | `mkdir new_folder`                   |
| `touch`         | Create a new file.                                                                           | `touch file.txt`                     |
| `cat`           | Display the contents of a file.                                                              | `cat file.txt`                       |
| `echo`          | Print text or add content to a file.                                                         | `echo "Test 1" > file.txt`         |
| `nano`          | Edit files in the terminal.                                                                  | `nano file.txt`                      |

## House Activity 

This activity was created in a Github repository. The repository was called house and it contained other folders that were the different rooms in the house. Different rooms contained files, hidden files, etc that were all clues to completing the activity.

To begin this activity first we had to download the map of the house aka the Github repository. 

[
](https://mail.google.com/mail/u/0?ui=2&ik=bdca38649d&attid=0.1&permmsgid=msg-a:r-2373642107752033430&th=19933c44ab09d03c&view=fimg&fur=ip&permmsgid=msg-a:r-2373642107752033430&sz=s0-l75-ft&attbid=ANGjdJ9PAHXvjoUfEDnDxgLzL9NTUbnyUgvGKPj9efNvhIhSEDD7x42K6mO4vrzMuEWHtw6UYM6pInJ0kToRiw631TjK_ICFeznqBNA0SDioFe_w6GHWpWuu7PjyUB0&disp=emb&realattid=ii_mfe0485t0&zw)<img width="500" height="729" alt="image" src="https://github.com/user-attachments/assets/c1590441-a053-4a7a-9c99-3a59c3118630" /> [
](https://mail.google.com/mail/u/0?ui=2&ik=bdca38649d&attid=0.2&permmsgid=msg-a:r-2373642107752033430&th=19933c44ab09d03c&view=fimg&fur=ip&permmsgid=msg-a:r-2373642107752033430&sz=s0-l75-ft&attbid=ANGjdJ9G9iK6Q4KODYrDp7X9FjFO5ia8U4sgSNf6VTCwPSiajBWDXanbMwrIr3sqOl4EgLoCS1GpC2855hZcRu_mK6aBs0SZBQnG9zqwQnr68JspBafgqQoF9Gvdu78&disp=emb&realattid=ii_mfe04tuw1&zw)<img width="500" height="729" alt="image" src="https://github.com/user-attachments/assets/23c287e3-108e-4e30-9861-92046db84eee" />

### Download Phase

Following the insturctions provided by our teacher. First updating by running "sudo apt update." Next sudo apt install -y git in order to be able to use the git commands in the VM terminal. Then changing directories to Documents followed by cloning the repository in Documents. "cd ~/Documents ... clone https://github.com/thewangclass/CK-Building-Content-Knowledge-Workshop.git." Finnaly after moving to the new directory by using "cd CK-Building-Content-Knowledge-Workshop.git." and using "git pull" to make sure I had the most updated version. Originally when trying to install the github commands I recieved an error message. In order to fix this problem my teacher and I had to run the sudo nano /etc/systemd/resolved.conf command to open up the nano control. Following that we navigated to the DNS server and removed the # from the name and set it = to 8.8.8.8. Finnaly we restarted the system by running the sudo systemctl restart systemd-resolved.

### Navigating the House 

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/1a532206-5586-4d7b-ac0d-14643b4dbb0d" /> <img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/c8a915c3-bee3-48e0-bc25-f4f2b1c0114b" />



The first thing I had to do was rename the directories for the activity so that I could navigate easier. Task one was to enter the friends house. I did this by using "cd ~/Documents/House/Activity/house". I listed all the folders in one command in order to be efficient and not have to type out a seperate command line for each folder. The next task was to see what is around the house. Using the "ls" command I found directories labled "bedroom1, bedroom2, garage, kitchen, main_entrance". Next I had to enter the main_entrance so I used the "cd main_entrance" command. In order to find and read the instructions left by the friend I used the "ls" command followed by "cat instructions.txt". To move back to the house folder I used the "cd .." command to move one level backwards. Next I had to move to the kitchen by using the "cd kitchen" command. Using the "ls" command I found all the food and drink left around the house. Using the "rm" command I was able to remove items from the kitchen folder. By putting a / in between items when using the "rm" command such as "rm notes.txt/essays" you can remove multiple items in one command. Next I used the "ls -a" command to find the rotten bananas file. Using "rm" again, I was able to remove these files. Next I navigated to bedroom1 and then to bedroom2 by using the change directories command. When the lights went out, I used the "pwd" command to print my working directory to know where I am in the house. Next I went to the garage by using "cd garage". Using "rm" I removed trash from each box. Finnaly I left a note by using "touch note.txt" then "echo "Thank you for trusting me!" > note.txt".

## Reflection 

By using the commands in multiple different activities I was able to solidify my understanding of these commands. Using visual tools like tree diagrams or the finder in Virtual Machines helped me better understand how to navigate using the terminal. Basic commands like "cd" or "rm" can be strung together to effieciently navigate through your computers files. These commands lay the foundation for my learning of the terminal. 
