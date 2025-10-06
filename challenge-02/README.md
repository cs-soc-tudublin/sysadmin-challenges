# **CHALLENGE 02**  - Do It Yourself

Now you know how to run a container on a VM and make it routable, it's time to make your own container image and run it!

All of the source code you need for this challenge is in thte `src` directory here.
You can clone this repository to your VM so you can have it all locally.

## Goal
Your task is to create a dockerfile and docker compose file. Build the container image locally and run it
1. Create the Dockerfile
2. Build the Image
3. Create the Compose
4. Run and make routable
5. Size optimisations

## Services Used
- Proxmox
- Docker
- GitHub
- SSH
- VS Code
- VIM / Nano
- Certbot
- NGINX

## Notes
You will want to pull the challenge files onto your staging VM, and work on it through that.

# 1. Create the Dockerfile
Docker containers need a `Dockerfile` to build a container image.
Everything CS++ develops has its own Dockerfile. These can be used as inspiration.
Since you're hosting a simple WebApp, you will want a Dockerfile with NodeJS.
Don't worry about image size or contents. That will be done later.

# 2. Build the Image
Once you have your dockerfile, run the command to build your container image locally.

# 3. Create the Compose
`docker-compose.yaml` files are easy files which store all the configs on how to run that service. These can be backed up really easily, so CS++ use them. It can also be used to store extra info, like who the service owner is.

There's loads of resources online on how to write a Docker Compose file, and lots of CS++ ones on `Huey` to look at.

# 4. Run and Make Routable
This is identical to Challenge 1, go ahead and make this site publicly routable.

# 5. Size Optimisation
Container image sizes are very important on enterprise scales. Less so for a society, but where storage is a bottleneck, size optimisiation is VITAL.
Smaller images also tend to use less resources.

Some of the best optimisations include using a small base image and using `.dockerignore`, but there are many other ways to optimise size.
I was able to get this container as low as **XXX**Mb. This does not mean it is as small as it can get, as there are some optimisations that make it harder to use, but have a much smaller footprint

# 6. UH OH! Wrench in the Works!
To successfully complete this challenge, you need to have **BOTH** Challenge 1 *and* Challenge 2 running and routable.
To do this you'll need a Reverse Proxy on your Staging VM. At CS++ we tend to use Traefik for containers. You can see how we use it on `Huey`, and the Traefik Docs are really good too.

# Completion Criteria
Challenge 1 Site available: `challenge-01.[your name].cspp.ie`
Challenge 2 Site available: `challenge-02.[your name].cspp.ie`