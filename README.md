# An Ubuntu user container
A base Ubuntu docker container with a user named _developer_.

This container uses `ubuntu:14.04`, and has a user and some pre-installed tools.
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
* nano
* tmux

## Usage
```
docker run -ti --rm peron/ubuntu-user
```

### GUI
If you want to test out applications that has a GUI, start the container using
```
docker run -ti --rm -e DISPLAY -e /tmp/.X11-unix:/tmp/.X11-unix:ro peron/ubuntu-user
```

## References
Source for GUI related stuff:
[Running GUI apps with Docker](http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker)

Bash files base on:
[jfrazelle/dotfiles](https://github.com/jfrazelle/dotfiles)
