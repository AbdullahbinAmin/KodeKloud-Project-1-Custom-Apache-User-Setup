# KodeKloud-Project-1-Custom-Apache-User-Setup
We need to create a special user named james on a server and give him a unique ID, along with a special home for him to live in.

#### Task-1: In response to heightened security concerns, the xFusionCorp Industries security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. Your task is to create a custom Apache user according to the outlined specifications:

a.	Create a user named james on App server 3 within the Stratos Datacenter.

b.	Assign a unique UID 1633 and designate the home directory as /var/www/james.

## Solution:

Our goal: We need to create a special user named james on a server and give him a unique ID, along with a special home for him to live in. Imagine you're playing a game where the "server" is a big house, and james is a new player who needs a special room. We're going to give james his own room in the house and a special badge (UID) that nobody else has.

Steps to create james:

Open the Server Terminal

•	First, we need to go into the "house" (the server) and start working.

•	You log into the server using SSH (a magic tool to connect to the server). If you're working on App Server 3 of Stratos Datacenter, you'd log in like this:

    ssh username@IP_Address_of_App_Server_3

Replace "username" and "IP_Address_of_App_Server_3" with the correct details.
3. Create the user named james
•	Now we are going to create a new player named james. To do that, we need to use a special command:

    sudo useradd -u 1633 -d /var/www/james james

o	sudo is like asking for permission from the server to do something important.
o	useradd is the command to add a new user.
o	-u 1633 is how we give james his special badge number (UID) – it's 1633!
o	-d /var/www/james is like giving james a special room in the house at this location.
o	james is the name of our new player.
3. Create james's Home Directory
•	Now that we've told the server where james's room is, we need to actually build the room. Let's make sure it exists:

    sudo mkdir -p /var/www/james

This command creates a folder for james to live in, just like creating a bedroom for him in the house.
4. Give james the keys to his room
•	We need to make sure only james has control over his room. This means setting up permissions:

    sudo chown james:james /var/www/james

This command gives james the ownership of his room, so only he can do things inside it.
5. Check if james is created
•	Let's check if james has been successfully added to the house:

    id james

This command will show james's information, including his badge number (UID 1633) and his room (home directory).
That’s it!
You’ve now created a special player named james who has his own room and badge in the server! He's ready to start playing the game (running the application) securely.
