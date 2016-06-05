# An Ubuntu user container
A base Ubuntu docker container with a user named _developer_.

This container uses `ubuntu:latest`, and has a user and some pre-installed tools.
It's perfect for testing out stuff, if you just need a terminal.

This container can also be used as a base for other containers that need a user.

If you have a standard Ubuntu OS, the user in this container should have the
same UID and GID as your primary user. This makes it easy to use this container as
a base for containers that need a GUI.

## User
The username is **developer**, and belongs to a group **developer**.
It has a UID of 1000 and a GID of 1000, respectively, and the user has sudo rights.
Home directory is **/home/developer**, and the shell is **bash**.
I.e. your basic Ubuntu setup.

## Tools
Some tools are pre-installed:
* htop
* tmux

## Usage
```
docker run -ti --rm peron/ubuntu-user
```

