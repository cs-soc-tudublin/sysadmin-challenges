# **CHALLENGE 03**  - Kick Your Feet Up

You now know how to build your own container from scratch. Now, let's make it easy to automate updates!

This is the first time you will need to create your own repo! Do that on your personal account just for cleanliness.

## Goal
Your task is to set up a simple CI/CD pipeline with GitHub actions and with `Watchtower`.
1. Create the GitHub Action
2. Set up the container on the VM
3. Set up Watchtower
4. Testing your pipeline

# 1. Create the GitHub Action
GitHub has it's own 'Container Registry' where built container images can be hosted publicly or privately.
You can use GitHub Actions to automate building a container image and pushing it to the GitHub Container Registry (GHCR)

We do this in CS++ for everything we develop in-house. Most likely, the premade action does everything you need!

Create a new repo, put your work from Challenge 2 in it and get started on GitHub Actions!

# 2. Set Up the Container on the VM
Identical to Challenges 1 & 2. Using the docker compose, make it publicly routable too!

Remember, you're using the GHCR link, not building in the VM!!!!!

# 3.Set up Watchtower
Watchtower is a cool Docker container that sees the containers running on the system and checks their upstream repository to see if a newer version exists.

We have it running on `Huey`, you can use its compose as your inspiration.

# 4. Testing Your Pipeline
Assuming you have everything set up correctly. Make a change to your code on the Repo and wait a few minutes for it to be built & pulled to your container.

If all goes well, it should update when you visit the URL!