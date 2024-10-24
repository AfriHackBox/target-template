# Target Templates
Target templates for AfriHackBox content creators.

This is a collection of templates to assist with creating targets and challenges for the AfriHackBox platform.

## Getting started
So you are having a killer idea and are interested in contributing your own machine for our platform. Good for you :smiley:

Here is what you need to do:
1. Create a private github repository
2. Copy the machine template of your choice (eg `debian-machine/`) into your repository and rename it to match the name of your target
3. Update the `Dockerfile`, `variables.yml`, `README.md` and any other of the provided files based on your needs
4. Build and test your image locally to ensure it works
5. Join our discord server and notify the administrators to receive further instructions. If you are not on our Discord server, you can find an invite to join at https://app.afrihackbox.com

The administrators will request that you give their Github accounts access to your private repository. At which point we will review and suggest fixes or changes to your machine.

## General rules for contributed machines
Some general rules you need to follow when creating your target or challenge:
* No `VOLUME` and `PORTS` statements are allowed
* Target names must be alphanumeric, with no spaces or capital letters
* All targets and challenges must include a detailed solution writeup
* All external documentation for the target or challenge must be in markdown format
* You must have solved at least 5 of our existing machines (not counting SanityCheck) for your target/challenge to be accepted
* If you don't use our templates then you need to make sure that you include the `variables.yml` and `autoregister.yml` files and ensure that they run during build
* DO NOT modify the `autoregister.yml` file unless you are instructed explicitly by us


