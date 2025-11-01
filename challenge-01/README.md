# **CHALLENGE 01**  - As It Is

Currently, CS++ runs every service as a [Docker](https://www.docker.com/) container on a VM.
Docker is the leading Containerisation platform, and is also quite simple.
The majority of our services have Web UIs, which we need to serve to the internet.
To do this, we use [NGINX](https://www.nginx.com/), a high-performance web server.

## Goal
Your task is to run a sample Web Service and have it served by NGINX to the internet.
This goal is split into 4 sections:
1. Creating the VM
2. Running the container on the VM
3. Making the container available to Golem
4. Making Golem proxy to the container
5. Setting the DNS

## Notes
Each high-level goal has a heading on the rest of this file.
Some additional tips and possible issues are provided where possible, as well as best-practice hints.

If you get stuck, you can always ask for help!

Don't forget to write up your process as you go, as this will be submitted at the end of the challenge.
You can include additional notes where relevant, as well as where you got stuck and how you solved it.

## Services Needed:
- Proxmox
- Docker
- SSH
- VIM / Nano
- Certbot
- NGINX
- CloudFlare

# 1. Creating the VM
This was shown and practiced at Sysadmin training.
As a reminder, a VM Template exists on one of our hosts (Mallard, Pancakes, etc.).
You also need to SSH with the SSH Key you created and sent to me.
Don't forget the MOTD instructions!

This will be your VM for most of these challenges. Keep it around after you're finished this one. It should be a **FULL CLONE**

# 2. Running the Container on the VM
Any services we develop have a GitHub action to build the container and push it to the GitHub Container Registry. 
You will see the container needed for this challenge in the Packages section of this repo.

We store all the services we use in `/src`.

We use Docker Compose when running Docker containers as they're easily backed up and updated.

ALL CS++ Services we develop and host have an example `docker-compose.yaml` file in their repo. This sample site is no different.

*Most* CS++ services we develop and host have instructions on how to run them. This service does not, purely as a learning exercise.
Familiarise yourself with the [Docker Compose Intro](https://docs.docker.com/compose/intro/compose-application-model/) page for the commands you will need to use.

`docker ps -a` is your friend here.

# 3. Making the Container Available to Golem
This was mentioned off-hand at Sysadmin training, but all VMs from the main template have UFW (Uncomplicated Firewall) installed and enabled.

You need to open the port the service is running on.
Security best-practice is to only open the port to the IP of Golem. You can find that Proxmox or in Ubiquiti.
Or, you could open it to a range of IPs. But that's not required right now.

# 4. Making Golem Proxy to the Container
Assuming the service is running and available on the VM, you now need to make Golem proxy to it.

We store all NGINX config files in `/etc/nginx/sites-available`, with sub directories for each society, club, or purpose.
At the root of the `/etc/nginx/sites-available` directory are 2 templates, a redirect template and a reverse proxy template.

Choose the one you think is correct and add it to the CSPP directory. Expl
Make the edits, ideally setting the subdomain to `challenge-01.[yourname].cspp.ie`
Using symbolic links, link your new config file to `/etc/nginx/sites-enabled`.
Test the NGINX confiogs and then run certbot to generate a new certificate for your new subdomain.
You will need to look up how to do this.

# 5. Setting the DNS
We use CloudFlare for our DNS. You will need to log in (password in the Password Manager) and add your DNS entry here.

# Completion Criteria
Challenge 01 available at `challenge-01.[your name].cspp.ie`